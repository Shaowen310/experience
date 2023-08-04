# Task Schedulers

## Linux

Crontab

### Basic commands

List all scheduled tasks

```
crontab -l
```

Edit schedule

```
crontab -e
```

Edit schedule which requires root permission

```
sudo crontab -e
```

### Schedule

Example

```
* * * * * /bin/bash -c "/path/to/script.sh"
```

The stars represent different date parts in the following order:

* minute (from 0 to 59)
* hour (from 0 to 23)
* day of month (from 1 to 31)
* month (from 1 to 12)
* day of week (from 0 to 6) (0=Sunday)

Star means any

Triggers when hitting any integer within a range, eg. `1-5`

Triggers when hitting any integer in a set, eg. `10,20,30`

Triggers when hitting any integer mod x == 0, eg. `*/10`

Special words

* **@reboot** Run once, at startup
* **@yearly/@annually** Run once per year "0 0 1 1 \*"
* **@monthly** Run once per month "0 0 1  "
* **@weekly** Run once per week "0 0   0"
* **@daily/@midnight** Run once per day "0 0   \*"
* **@hourly** Run once per hour "0    "

## Windows

Search (`⊞ Win`+`S` since Win 8.1) "schduler"

`⊞ Win`+`R`, open `taskschd.msc`

### Schedule Powershell scripts

Actions: Start a program

Settings:

Program/scripts: powershell.exe

Add arguments: -ExecutionPolicy Bypass&#x20;

## References

1. [Schedule Tasks on Linux Using Crontab](http://kvz.io/blog/2007/07/29/schedule-tasks-on-linux-using-crontab/)
2. [Run Powershell Scripts from Task Scheduler](https://community.spiceworks.com/how\_to/17736-run-powershell-scripts-from-task-scheduler)
