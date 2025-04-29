# nginx config

```
# minimal log sending to graylog
log_format graylog escape=json '{ "time": "$time_iso8601", '
        '"remote_addr": "$remote_addr", '
        '"method": "$request_method", '
        '"uri": "$request_uri", '
        '"response_status": $status, '
        '"request": "$request", '
        '"host": "$host", '
        '"bytes": $body_bytes_sent, '
        '"referer": "$http_referer", '
        '"agent": "$http_user_agent", '
        '"nginx_access": true }';
```

the logging rule :
```
access_log syslog:server=$IP:$PORT graylog;
```
change $IP and $PORT