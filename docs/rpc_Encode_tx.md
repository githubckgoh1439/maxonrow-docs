# Tx APIs

<!---
//uatnet.usdp.io/encode_tx?json=_
----[goh sendiri] 
-->

### EncodeTx
Return encoded Transaction Data using tx hash value.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| hash | string | false | true    | transaction Hash to retrive |
| prove | bool | false | false    | include a proof of the transaction inclusion in the block in the result (default: false). |


#### Return Type
```
type ResultEncodeTx struct {
    Results string
}
```


#### Example

Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
```

```
{
    "method": "encode_tx",
    "params": ["eyJ0eXBlIjoiY29zbW9zLXNkay9TdGRUeCIsInZhbHVlIjp7ImZlZSI6eyJhbW91bnQiOlt7ImFtb3VudCI6IjUwMDAwMDAwMDAwMDAwMDAwIiwiZGVub20iOiJjaW4ifV0sImdhcyI6IjAifSwibWVtbyI6InRlc3RpbmcgdHJhbnNmZXIgd2l0aCAxMWNpbiwgZnJvbSBhY2MtOSB0byBhY2MtOCIsIm1zZyI6W3sidHlwZSI6Im14dy9tc2dTZW5kIiwidmFsdWUiOnsiYW1vdW50IjpbeyJhbW91bnQiOiIxMSIsImRlbm9tIjoiY2luIn1dLCJmcm9tX2FkZHJlc3MiOiJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJ0b19hZGRyZXNzIjoibXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRlIn19XSwic2lnbmF0dXJlcyI6W3sicHViX2tleSI6eyJ0eXBlIjoidGVuZGVybWludC9QdWJLZXlTZWNwMjU2azEiLCJ2YWx1ZSI6IkE1SWE4RUFvTllZbFhVNXk0aHV6c3czRm1FSXZLZ3pxd2lDOXhqZjFWekRYIn0sInNpZ25hdHVyZSI6IjFIZHZodkFNTkJGVlpYbTRMam1DMkJFeTQxSC9HQnFjUHJsbnZFRTVYT1VRZVNVTXJuZkd1NkhmeGhqOHNlKzNlZUZaTXVQSFZaZzFEdm9iV3pBRTRnPT0ifV19fQ=="],
    "id": 0,
    "jsonrpc": "2.0"
}
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "result": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"
}
```
