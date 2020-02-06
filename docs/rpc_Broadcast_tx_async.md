# APIs

### BroadcastTxAsync
This method just return transaction hash right away and there is no return from CheckTx or DeliverTx.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| tx | Tx | nil | true  | The transaction info bytes in hex |



#### Return Type
CheckTx Result
```
type ResultBroadcastTx struct {
    Code uint32
    Data cmn.HexBytes
    Log  string
    Hash cmn.HexBytes
}
```

#### Example

Step-1. Query the account number and sequence of the TWO account-address 

Run the command with the JSON request body:
```
http://localhost:26657/
```

```
{
    "method": "account",
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
  "result": "
    { 
   "type":"cosmos-sdk/Account",
   "value":{ 
      "address":"mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
      "coins":[ 
         { 
            "denom":"cin",
            "amount":"1000000000000000000000"
         }
      ],
      "public_key":{ 
         "type":"tendermint/PubKeySecp256k1",
         "value":"A5Ia8EAoNYYlXU5y4huzsw3FmEIvKgzqwiC9xjf1VzDX"
      },
      "account_number":"8",
      "sequence":"0"
   }}"
}
```

Run the command with the JSON request body:
```
http://localhost:26657/
```

```
{
    "method": "account",
    "params": ["mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e"],
    "id": 0,
    "jsonrpc": "2.0"
}
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": 0,
  "result": "
    { 
   "type":"cosmos-sdk/Account",
   "value":{ 
      "address":"mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e",
      "coins":[ 
         { 
            "denom":"cin",
            "amount":"1000000000000000000000"
         }
      ],
      "public_key":{ 
         "type":"tendermint/PubKeySecp256k1",
         "value":"A9Nmqbf2cKAOs9hzGTRyS2Wd6uLBWrwkZ0S7q06N0/3i"
      },
      "account_number":"7",
      "sequence":"0"
   }}"
}
```


Step-2. Generate the transaction output as json format

```
mxwcli tx send mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e 11cin --fees 50000000000000000cin --gas 0 --memo "testing transfer with 11cin, from acc-9 to acc-8" --home ~/.mxw_20191009_local01 --chain-id=maxonrow-chain
```

```
{ 
   "chain_id":"maxonrow-chain",
   "account_number":"8",
   "sequence":"0",
   "fee":{ 
      "amount":[ 
         { 
            "denom":"cin",
            "amount":"50000000000000000"
         }
      ],
      "gas":"0"
   },
   "msgs":[ 
      { 
         "type":"mxw/msgSend",
         "value":{ 
            "from_address":"mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
            "to_address":"mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e",
            "amount":[ 
               { 
                  "denom":"cin",
                  "amount":"11"
               }
            ]
         }
      }
   ],
   "memo":"testing transfer with 11cin, from acc-9 to acc-8"
}
```

```
confirm transaction before signing and broadcasting [y/N]: y
Password to sign with 'acc-9':
```

```
height: 0
txhash: 79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9
code: 0
data: ""
rawlog: '[{"msg_index":0,"success":true,"log":""}]'
logs:
- msgindex: 0
  success: true
  log: ""
info: ""
gaswanted: 0
gasused: 0
events: []
codespace: ""
tx: null
timestamp: ""
```

Step-3. You could decode using the decode_tx, base on the value of txhash 

Run the command:
```
curl 'http://localhost:26657/decoded_tx?hash=0x79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9&prove=true'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "hash": "79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9",
    "height": "250",
    "index": 0,
    "tx_result": {
      "log": "[{\"msg_index\":0,\"success\":true,\"log\":\"{\\\"hash\\\":\\\"79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9\\\",\\\"nonce\\\":0}\"}]",
      "gasUsed": "78131",
      "events": [
        {
          "type": "message",
          "attributes": [
            {
              "key": "YWN0aW9u",
              "value": "c2VuZA=="
            }
          ]
        },
        {
          "type": "message",
          "attributes": [
            {
              "key": "RnJvbQ==",
              "value": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw"
            },
            {
              "key": "VG8=",
              "value": "bXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRl"
            },
            {
              "key": "QW1vdW50",
              "value": "MTE="
            }
          ]
        },
        {
          "type": "system",
          "attributes": [
            {
              "key": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw",
              "value": "eyJoYXNoIjoiMmNhZGNmYjBjMzM2NzY5ZDUwM2Q1NTdiMjZmY2YxZTkxODE5ZTdlNSIsInBhcmFtcyI6WyJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJteHcxYWdsd2RlaGtyZ2FuOXA4NmVhOGtsNzVsa2FnMmgweHR3ajJkNGUiLCIxMSJdfQ=="
            }
          ]
        }
      ]
    },
    "tx": "{\"type\":\"cosmos-sdk/StdTx\",\"value\":{\"fee\":{\"amount\":[{\"amount\":\"50000000000000000\",\"denom\":\"cin\"}],\"gas\":\"0\"},\"memo\":\"testing transfer with 11cin, from acc-9 to acc-8\",\"msg\":[{\"type\":\"mxw/msgSend\",\"value\":{\"amount\":[{\"amount\":\"11\",\"denom\":\"cin\"}],\"from_address\":\"mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p\",\"to_address\":\"mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e\"}}],\"signatures\":[{\"pub_key\":{\"type\":\"tendermint/PubKeySecp256k1\",\"value\":\"A5Ia8EAoNYYlXU5y4huzsw3FmEIvKgzqwiC9xjf1VzDX\"},\"signature\":\"1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4g==\"}]}}",
    "proof": {
      "RootHash": "C5FFE7245DDDB3B80637863EFD86AB1E35F790DA9A38C703F84FF6760F448860",
      "Data": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04",
      "Proof": {
        "total": "1",
        "index": "0",
        "leaf_hash": "xf/nJF3ds7gGN4Y+/YarHjX3kNqaOMcD+E/2dg9EiGA=",
        "aunts": []
      }
    }
  }
}
```

Step-4. You proceed below : 

4.1 Do the filtering by remove symbol of '\', base on the value of tx like below
```
{ 
   "type":"cosmos-sdk/StdTx",
   "value":{ 
      "fee":{ 
         "amount":[ 
            { 
               "amount":"50000000000000000",
               "denom":"cin"
            }
         ],
         "gas":"0"
      },
      "memo":"testing transfer with 11cin, from acc-9 to acc-8",
      "msg":[ 
         { 
            "type":"mxw/msgSend",
            "value":{ 
               "amount":[ 
                  { 
                     "amount":"11",
                     "denom":"cin"
                  }
               ],
               "from_address":"mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
               "to_address":"mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e"
            }
         }
      ],
      "signatures":[ 
         { 
            "pub_key":{ 
               "type":"tendermint/PubKeySecp256k1",
               "value":"A5Ia8EAoNYYlXU5y4huzsw3FmEIvKgzqwiC9xjf1VzDX"
            },
            "signature":"1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4g=="
         }
      ]
   }
}
```

4.2 Then convert the value into base-64 format
```
eyJ0eXBlIjoiY29zbW9zLXNkay9TdGRUeCIsInZhbHVlIjp7ImZlZSI6eyJhbW91bnQiOlt7ImFtb3VudCI6IjUwMDAwMDAwMDAwMDAwMDAwIiwiZGVub20iOiJjaW4ifV0sImdhcyI6IjAifSwibWVtbyI6InRlc3RpbmcgdHJhbnNmZXIgd2l0aCAxMWNpbiwgZnJvbSBhY2MtOSB0byBhY2MtOCIsIm1zZyI6W3sidHlwZSI6Im14dy9tc2dTZW5kIiwidmFsdWUiOnsiYW1vdW50IjpbeyJhbW91bnQiOiIxMSIsImRlbm9tIjoiY2luIn1dLCJmcm9tX2FkZHJlc3MiOiJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJ0b19hZGRyZXNzIjoibXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRlIn19XSwic2lnbmF0dXJlcyI6W3sicHViX2tleSI6eyJ0eXBlIjoidGVuZGVybWludC9QdWJLZXlTZWNwMjU2azEiLCJ2YWx1ZSI6IkE1SWE4RUFvTllZbFhVNXk0aHV6c3czRm1FSXZLZ3pxd2lDOXhqZjFWekRYIn0sInNpZ25hdHVyZSI6IjFIZHZodkFNTkJGVlpYbTRMam1DMkJFeTQxSC9HQnFjUHJsbnZFRTVYT1VRZVNVTXJuZkd1NkhmeGhqOHNlKzNlZUZaTXVQSFZaZzFEdm9iV3pBRTRnPT0ifV19fQ==
```

Step-5. You could encode using the encode_tx, base on the value of base-64 as above.

Run the command with the JSON request body:
```
http://localhost:26657/
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
  "id": 0,
  "result": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"
}
```

Step-6. You could submit the transaction using the BroadcastTxAsync, base on the result value.

Run the command with the JSON request body:
```
http://localhost:26657/
```

```
{
    "method": "broadcast_tx_async",
    "params": ["/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"],
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
    "code": 0,
    "data": "",
    "log": "",
    "hash": "79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9"
  }
}
```

Step-7. You can verify the current transaction using the Tx, base on the hash value.

Run the command:
```
curl 'http://localhost:26657/tx?hash=0x79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "hash": "79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9",
    "height": "250",
    "index": 0,
    "tx_result": {
      "log": "[{\"msg_index\":0,\"success\":true,\"log\":\"{\\\"hash\\\":\\\"79215E24FEB4016F1CB70049D771800B7F622749C4602B6BC328142DCDD493C9\\\",\\\"nonce\\\":0}\"}]",
      "gasUsed": "78131",
      "events": [
        {
          "type": "message",
          "attributes": [
            {
              "key": "YWN0aW9u",
              "value": "c2VuZA=="
            }
          ]
        },
        {
          "type": "message",
          "attributes": [
            {
              "key": "RnJvbQ==",
              "value": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw"
            },
            {
              "key": "VG8=",
              "value": "bXh3MWFnbHdkZWhrcmdhbjlwODZlYThrbDc1bGthZzJoMHh0d2oyZDRl"
            },
            {
              "key": "QW1vdW50",
              "value": "MTE="
            }
          ]
        },
        {
          "type": "system",
          "attributes": [
            {
              "key": "bXh3MXhzNTk0NmZrNTNqbnN4ZDJheGp0a2ptdzZrczNoNGR1Y3M1YTdw",
              "value": "eyJoYXNoIjoiMmNhZGNmYjBjMzM2NzY5ZDUwM2Q1NTdiMjZmY2YxZTkxODE5ZTdlNSIsInBhcmFtcyI6WyJteHcxeHM1OTQ2Zms1M2puc3hkMmF4anRram13NmtzM2g0ZHVjczVhN3AiLCJteHcxYWdsd2RlaGtyZ2FuOXA4NmVhOGtsNzVsa2FnMmgweHR3ajJkNGUiLCIxMSJdfQ=="
            }
          ]
        }
      ]
    },
    "tx": "/QEoKBapCj12B33fCjcKFDQoWuk2pGU4GarppLtLbtWhG9W8EhTqPubm9ho7MoT6z09v+p+3UKu8yxoJCgNjaW4SAjExEhoKGAoDY2luEhE1MDAwMDAwMDAwMDAwMDAwMBpqCibrWumHIQOSGvBAKDWGJV1OcuIbs7MNxZhCLyoM6sIgvcY39Vcw1xJA1HdvhvAMNBFVZXm4LjmC2BEy41H/GBqcPrlnvEE5XOUQeSUMrnfGu6Hfxhj8se+3eeFZMuPHVZg1DvobWzAE4iIwdGVzdGluZyB0cmFuc2ZlciB3aXRoIDExY2luLCBmcm9tIGFjYy05IHRvIGFjYy04"
  }
}
```

