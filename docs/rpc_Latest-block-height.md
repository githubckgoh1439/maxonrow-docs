# Query APIs

<!---
//uatnet.usdp.io/latest_block_height?
----[goh sendiri-html] 
-->

### Query LatestBlockHeight
Get latest block height. 

#### Return Type
```
type ResultLatestBlockHeight struct {
    Results  int64
}
```


#### Example

Run the command:
```
curl 'http://localhost:26657/latest_block_height'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": "2366"
}
```

