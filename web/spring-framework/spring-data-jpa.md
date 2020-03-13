# Spring data JPA

## Clean database after each test case run

Adopted from [How to clear database in Spring Boot tests?](https://brightinventions.pl/blog/clear-database-in-spring-boot-tests/)

DatabaseCleaner.java

```java
package com.genie.api.junit.rule.support;

import java.sql.Connection;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.ArrayList;
import java.util.Collections;
import java.util.HashSet;
import java.util.List;
import java.util.Set;

import javax.sql.DataSource;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.beans.factory.annotation.Autowired;

public class DatabaseCleaner {

    private static Logger LOG = LoggerFactory.getLogger(DatabaseCleaner.class);

    @Autowired
    private DataSource dataSource;

    private List<String> tablesForClearing = null;

    private Set<String> tablesToExclude = new HashSet<String>();

    public void excludeTables(String... tableNames) {
        Collections.addAll(tablesToExclude, tableNames);
    }

    public void reset() {
        if (notPrepared()) {
            prepare();
        }
        executeReset();
    }

    private boolean notPrepared() {
        return tablesForClearing == null;
    }

    private void prepare() {
        try (var conn = dataSource.getConnection()) {
            var metaData = conn.getMetaData();
            var tableRefs = metaData.getTables(conn.getCatalog(), null, null, new String[] { "TABLE" });
            List<String> tablesForClearingTemp = new ArrayList<>();
            while (tableRefs.next()) {
                var tableName = tableRefs.getString("TABLE_NAME");
                if (tablesToExclude.contains(tableName)) {
                    continue;
                }
                tablesForClearingTemp.add(tableName);
            }
            tablesForClearing = tablesForClearingTemp;
            LOG.info("Prepared clean db command: {}", tablesForClearing);
        } catch (SQLException e) {
            LOG.error("Failed to prepare table names.", e);
        }
    }

    private void executeReset() {
        try (var conn = dataSource.getConnection()) {
            var reset = buildClearStatement(conn);
            reset.executeBatch();
        } catch (SQLException e) {
            LOG.error("Failed to remove rows.", e);
        }
    }

    private Statement buildClearStatement(Connection conn) throws SQLException {
        var reset = conn.createStatement();
        reset.addBatch("SET FOREIGN_KEY_CHECKS = 0");
        tablesForClearing.forEach(table -> {
            try {
                reset.addBatch(String.format("DELETE FROM %s", table));
            } catch (SQLException e) {
                LOG.error("Failed to add delete command.", e);
            }
        });
        reset.addBatch("SET FOREIGN_KEY_CHECKS = 1");
        return reset;
    }

}
```

DatabaseCleanerRule.java

```java
package com.genie.api.junit.rule;

import org.junit.rules.ExternalResource;
import org.springframework.beans.factory.annotation.Autowired;

import com.genie.api.junit.rule.support.DatabaseCleaner;

public class DatabaseCleanerRule extends ExternalResource {

    @Autowired
    DatabaseCleaner databaseCleaner;

    @Override
    public void after() {
        databaseCleaner.reset();
    }
}
```

## Practices

1. Use `@Table(name="{project_name}_{table_name}")` to get rid of potential name clash with reserved words.

## References

1. [Spring Boot + Spring data JPA + PostgreSQL](https://www.mkyong.com/spring-boot/spring-boot-spring-data-jpa-postgresql/)
2. [Spring Boot Hibernate Syntax Error in SQL Statement](https://stackoverflow.com/questions/27987068/spring-boot-hibernate-syntax-error-in-sql-statement)
3. [Should my tests be @Transactional?](https://www.marcobehler.com/2014/06/25/should-my-tests-be-transactional)
4. [How Does Spring @Transactional Really Work?](https://dzone.com/articles/how-does-spring-transactional)
5. [Spring repository not always throwing DataIntegrityViolationException](https://stackoverflow.com/questions/43707774/spring-repository-not-always-throwing-dataintegrityviolationexception)
6. [How to clear database in Spring Boot tests?](https://brightinventions.pl/blog/clear-database-in-spring-boot-tests/)

