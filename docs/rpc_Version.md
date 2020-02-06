# Query APIs

<!---
//uatnet.usdp.io/version?
----[goh sendiri-html] 
-->

### Query Version
Get the version of maxonrow running locally to compare against expected.


#### Return Type
```
type ResultVersion struct {
    Results *state.Responses
}
```


#### Example
Run the command:
```
curl 'http://localhost:26657/version'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "tendermintversion": "0.32.2",
    "maxonrowversion": "0.6.3",
    "cosmosversion": ""
  }
}
```

