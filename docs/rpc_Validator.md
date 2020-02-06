# Query APIs
<!---
//uatnet.usdp.io/validator?address=_
----[goh sendiri-html] 
-- [https://cosmos.network/rpc/#/ICS21/get_staking_validators__validatorAddr_]
-->


### Query Validator
Query the information from a single validator

#### Parameters
| Name | Type | Default | Required | Description                 |
| ---- | ---- | ------- | -------- | --------------------------- |
| address | string | false | true    | Bech32 OperatorAddress of validator |


#### Return Type
```
type ResultValidator struct {
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
    "method": "validator",
    "params": ["mxwvaloper1urazz6vuldjp09gtzft0nw2kuv25l079fh99g4"],
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
    "operator_address":"mxwvaloper1urazz6vuldjp09gtzft0nw2kuv25l079fh99g4",
    "consensus_pubkey":"mxwvalconspub1zcjduepqj7nxtu5vplj5rnymczca7qy84pt4ufxy408m9gz2eavyjpdhw08s8gcu3p",
    "jailed":false,
    "status":2,
    "tokens":"100000000000000000000",
    "delegator_shares":"100000000000000000000.000000000000000000",
    "description":{ 
        "moniker":"local",
        "identity":"",
        "website":"",
        "security_contact":"",
        "details":""
    },
    "unbonding_height":"0",
    "unbonding_time":"1970-01-01T00:00:00Z",
    "commission":{ 
        "commission_rates":{ 
            "rate":"0.100000000000000000",
            "max_rate":"0.200000000000000000",
            "max_change_rate":"0.010000000000000000"
        },
        "update_time":"2019-10-09T03:35:53.661582Z"
    },
    "min_self_delegation":"1"
    }"
}
```

