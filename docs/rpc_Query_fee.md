# Query APIs

<!---
//uatnet.usdp.io/query_fee?tx=_
----[goh sendiri] 
-->


### Query Fee
Get the Fee Setting of a particular Tx.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| hash | []byte | nil | true    | transaction Hash to retrive |


#### Return Type
```
type ResultQueryFee struct {
    Results *state.Responses
}
```


#### Example
Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "query_fee",
    "params": ["eyJ0eXBlIjoiY29zbW9zLXNkay9TdGRUeCIsInZhbHVlIjp7ImZlZSI6eyJhbW91bnQiOlt7ImFtb3VudCI6IjUwMDAwMDAwMDAwMDAwMDAwIiwiZGVub20iOiJjaW4ifV0sImdhcyI6IjAifSwibWVtbyI6InRlc3RpbmcgdHJhbnNmZXIgd2l0aCAxMWNpbiwgZnJvbSBhY2MtOSB0byBhY2MtOCIsIm1zZyI6W3sidHlwZSI6Im14dy9tc2dTZW5kIiwidmFsdWUiOnsiYW1vdW50IjpbeyJhbW91bnQiOiIxMSIsImRlbm9tIjoiY2luIn1dLCJmcm9tX2FkZHJlc3MiOiJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJ0b19hZGRyZXNzIjoibXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRlIn19XSwic2lnbmF0dXJlcyI6W3sicHViX2tleSI6eyJ0eXBlIjoidGVuZGVybWludC9QdWJLZXlTZWNwMjU2azEiLCJ2YWx1ZSI6IkE1SWE4RUFvTllZbFhVNXk0aHV6c3czRm1FSXZLZ3pxd2lDOXhqZjFWekRYIn0sInNpZ25hdHVyZSI6IjFIZHZodkFNTkJGVlpYbTRMam1DMkJFeTQxSC9HQnFjUHJsbnZFRTVYT1VRZVNVTXJuZkd1NkhmeGhqOHNlKzNlZUZaTXVQSFZaZzFEdm9iV3pBRTRnPT0ifV19fQ=="],
    "id": 0,
    "jsonrpc": "2.0"
}
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": {
    "amount": [
      {
        "denom": "cin",
        "amount": "10000000000000000"
      }
    ],
    "gas": "0"
  }
}
```
