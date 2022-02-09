# apache-access-logstash-pipeline
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
