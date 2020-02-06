# Tx APIs
<!---
//uatnet.usdp.io/decoded_tx?hash=_&prove=_
----[goh sendiri-html] 
-->

### DecodeTx
Return readable Transaction Data using tx hash value.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| hash | string | false | true    | transaction Hash to retrive |
| prove | bool | false | false    | include a proof of the transaction inclusion in the block in the result (default: false). |


#### Return Type
```
type ResultDecodeTx struct {
    Results *state.Responses
}
```

#### Example
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
