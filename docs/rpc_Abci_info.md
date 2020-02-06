# Query APIs

### Query ABCIInfo
Get some info about the application.

#### Return Type
```
type ResponseInfo struct {
    Data                 string
    Version              string
    AppVersion           uint64
    LastBlockHeight      int64
    LastBlockAppHash     []byte
}
```

#### Example
Run the command:
```
curl 'localhost:26657/abci_info'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "response": {
      "data": "maxonrow-go",
      "last_block_height": "2674",
      "last_block_app_hash": "f4pzDKuVaGzWk1hCCJseLteuE/PiDhNncSD+JqTpGw4="
    }
  }
}
```

