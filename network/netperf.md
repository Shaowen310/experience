# Netperf

## Design basics

Netperf is designed around the basic client-server model. There are two executables - netperf and netserver. Only netperf program is required to be executed to conduct a test, while the netserver program will be invoked by the other system's inetd.

**Control connection**: This connection is first established when netperf is executed, and it will be used to pass test configuration information and results to and from the remote system. Regardless of the type of test being run, the control connection will be a TCP connection using BSD sockets.

**Measurement connection**: Once the control connection is up and the configuration information has been pased. a seprate connection will be opened for the measurement itself using the APIs and protocols appropriate for the test.

Netperf places no traffic on the control connection while a test is in progress. Certain TCP operation, such as SO\_KEEPALIVE, if set as your system's default, may put packets out on the control connection.

## Measure bulk data transfer performance

```text
netperf -H {remotehost} -t {TEST_TYPE} -l {TEST_LENGTH} -- [test_type_specified_options...]
```

### Test types

| Type | Description |
| :--- | :--- |
| TCP\_STREAM | TCP stream |
| UDP\_STREAM | UDP stream |

See the manual for other test types.

### Test length

Set the test length to value **seconds** when value is &gt; 0 and to -value **bytes** when value is &lt; 0 \|

### Common test type specified options

| Option | Description |
| :--- | :--- |
| -m value | set the local send size to value **bytes**. Default: local socket buffer size. |
| -M value | behaves like -m, setting the receive size for the remote system. |

## References

1. [Netperf homepage](https://hewlettpackard.github.io/netperf/)
2. [Test the network performance of a physical connection](https://www.alibabacloud.com/help/doc-detail/58625.htm)

