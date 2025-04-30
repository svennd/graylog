Truenas scale

under System Settings -> Syslog 

Level: notice
server
transport
check : Include Audit Logs


This parse rule will parse the JSON dump of SMB audit :
```
{
  "TNAUDIT": {
    "aid": "29960*******fadf2b296",
    "vers": {
      "major": 0,
      "minor": 1
    },
    "addr": "$IPV4",
    "user": "$USER$",
    "sess": null,
    "time": "2025-04-30 09:05:03.170257Z",
    "svc": "SMB",
    "svc_data": "{\"vers\": {\"major\": 0, \"minor\": 1}, \"service\": null, \"session_id\": null, \"tcon_id\": null}",
    "event": "AUTHENTICATION",
        *****
    "success": true
  }
}
```
