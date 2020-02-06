# Query APIs

<!---
//uatnet.usdp.io/is_whitelisted?address=_
----[goh sendiri-html] 
-->

### IsWhitelisted
Returns status of whitelisted.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| address | string | false | true  | Bech32 OperatorAddress of account |


#### Return Type
```
type ResultIsWhitelisted struct {
    Results boolean
}
```


#### Example

Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "is_whitelisted",
    "params": ["mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p"],
    "id": 0,
    "jsonrpc": "2.0"
}
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": true
}
```

