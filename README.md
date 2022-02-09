# apache-access-logstash-pipeline

[![CI](https://github.com/widhalmt/apache-access-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg?event=push)](https://github.com/widhalmt/apache-access-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

Logstash pipeline for apache access log

## Input and output ##

This pipeline has no input nor output. `.gitignore` includes `input.conf` and `output.conf` so you can use these files for your own input and output configuration.

Here are examples using a local Redis.

```
input {
  redis {
    host => "localhost"
    data_type => "list"
    key => "apache-access"
  }
}

output {
  redis {
    host => "localhost"
    data_type => "list"
    key => "forwarder"
  }
}
```
