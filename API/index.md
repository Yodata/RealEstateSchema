# RealEstateSchema: API

## API Standards

- [Linked Data Platform 1.0](https://www.w3.org/TR/ldp/)
- [Linked Data Notifications](https://www.w3.org/TR/ldn/)

## Getting messages
use HTTP GET [inboxurl] to read the next page of messages from an inbox.

```bash
$ curl -X GET \
    https://bob.example.com/inbox/ \
    -H 'x-api-key: your-api-key' 
```

RESPONSE
```text
{
  "id": "https://bob.example.com/inbox/",
  "contains": [
    {
      "id": "https://bob.example.com/inbox/12345", // the message id
      "type": "Notification",
      "instrument": "https://yodata.io/app/appname",  // message source
      "target": "https://bob.example.com/inbox/",
      "timestamp": 1525378691500,
      "object": {...}
    }
  ]
}
```

