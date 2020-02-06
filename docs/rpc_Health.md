# Query APIs

### Query Health
Get node health. Returns empty result (200 OK) on success, no response - in case of an error.

#### Return Type
```
ResultHealth{}
```

#### Example
Run the command:
```
curl 'http://localhost:26657/health'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {}
}
```
