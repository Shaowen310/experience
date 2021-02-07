# Python Logger

## Sample Configuration

`loggingutil.py`

### Configure by code

```python
import logging
import sys
from logging.handlers import TimedRotatingFileHandler
FORMATTER = logging.Formatter("%(asctime)s — %(name)s — %(levelname)s — %(message)s")
LOG_FILE = "my_app.log"

def get_console_handler():
   console_handler = logging.StreamHandler(sys.stdout)
   console_handler.setFormatter(FORMATTER)
   return console_handler
def get_file_handler():
   file_handler = TimedRotatingFileHandler(LOG_FILE, when='midnight')
   file_handler.setFormatter(FORMATTER)
   return file_handler
def get_logger(logger_name):
   logger = logging.getLogger(logger_name)
   logger.setLevel(logging.DEBUG)
   logger.addHandler(get_console_handler())
   logger.addHandler(get_file_handler())
   logger.propagate = False
   return logger
```

### Configure by file

```python
import logging
import logging.config
import yaml

LOGGING_CONFIG_FILE = 'logging.yaml'

def init():
    with open(LOGGING_CONFIG_FILE) as f:
        data = yaml.load(f)
        logging.config.dictConfig(data)


def get_logger(logger_name):
    return logging.getLogger(logger_name)
```

#### Configuration file

`logging.yaml`

```yaml
version: 1
formatters:
  default:
    format: '%(asctime)s %(levelname)s %(name)s %(message)s'
handlers:
  console:
    class: logging.StreamHandler
    level: INFO
    formatter: default
    stream: ext://sys.stdout
  file:
    class: logging.FileHandler
    level: DEBUG
    formatter: default
    filename: app.log
loggers:
  logger_name:
    level: DEBUG
    handlers: [console, file]
    propagate: no

```

## References

1. [Toptal: In Depth Python Logging](https://www.toptal.com/python/in-depth-python-logging)

