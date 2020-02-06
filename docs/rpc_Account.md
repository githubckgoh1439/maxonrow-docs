# Query APIs
<!---
//uatnet.usdp.io/account?address=_
----[https://cosmos.network/rpc/#/ICS1/get_auth_accounts__address_] 
-->

### Query Account
Get the account information on blockchain.

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| address | string | false | true    | Bech32 OperatorAddress of account |

#### Return Type
```
type ResultAccount struct {
    Type  string
    Value *state.AccountInfoResponses
}
```

#### Example
Query the account number and sequence of the account-address

Run the command with the JSON request body:
```
curl 'http://localhost:26657/'
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

