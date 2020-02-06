# Query APIs

### Query GenesisFile
Get genesis file.

#### Return Type
Return round states
```
// Genesis file
type ResultGenesis struct {
    Genesis *types.GenesisDoc
}
// GenesisDoc defines the initial conditions for a tendermint blockchain, in particular its validator set.
type GenesisDoc struct {
    GenesisTime     time.Time
    ChainID         string
    ConsensusParams *ConsensusParams
    Validators      []GenesisValidator
    AppHash         cmn.HexBytes
    AppState        json.RawMessage
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/genesis'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "genesis": {
      "genesis_time": "2019-10-09T03:35:53.661582Z",
      "chain_id": "maxonrow-chain",
      "consensus_params": {
        "block": {
          "max_bytes": "22020096",
          "max_gas": "-1",
          "time_iota_ms": "1000"
        },
        "evidence": {
          "max_age": "100000"
        },
        "validator": {
          "pub_key_types": [
            "ed25519"
          ]
        }
      },
      "app_hash": "",
      "app_state": {
        "auth": {
          "params": {
            "max_memo_characters": "256",
            "tx_sig_limit": "7",
            "tx_size_cost_per_byte": "0",
            "sig_verify_cost_ed25519": "0",
            "sig_verify_cost_secp256k1": "0"
          }
        },
        "accounts": [
          {
            "address": "mxw1urazz6vuldjp09gtzft0nw2kuv25l0793c6m9w",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1u7wn0ewe53csak2xl5nxaj45gangy3a4wq7xy7",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1xl7awvx7e7yjm256hx676vcqavx5c232rrtqpx",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1fkw4vdzgqd4jsvrt0whqjp6kr7mlt0rzl89lkv",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1vhz42dpefjhfrufurh2wwkpdt0837s5hxamt0u",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw146xepk070h8h2znggp8rdffn3ym3fda5gfjwxm",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw17tx5936pw0xfcqe4g76wxefwdl3j4rpdygt5wf",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1vulu4lra8nd2aswz60xkj5uxnp9kw0fuq3e65g",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1rnwy4utedvl7p2x49squm2a3a0d6gne4pe8h5w",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1kvc7pvyu65sg0hgqc6tnu0rd40g5qwayrwtqnh",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1vtqkfs7trns8jepp3mu8skqkcga90ky2zp7v7p",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1rq9txn872hchzdau2c44t464fqdvn3ad4drkp8",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1wc6dp6qrp48x3hjy6049l3f8phtkr9hqd2z5wh",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw19dgfsqpqnatfv298zna6wnlauv07kcvw386vew",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1smcavtfea3mpsplsual2jyx3jcps8vjv8yh43v",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1uzhu2au5r5gaafx6uj2hw87af44udw3wuehvvy",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw1v36a5t98pgywy59vhmwkr527u330uweqvxcj3p",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          },
          {
            "address": "mxw16g5gj7slym5a3amnyajycc9zw8yqmd74agludz",
            "coins": [
              {
                "denom": "cin",
                "amount": "1000000000000000000000"
              }
            ],
            "public_key": null,
            "account_number": "0",
            "sequence": "0"
          }
        ],
        "bank": {
          "send_enabled": true
        },
        "staking": {
          "params": {
            "unbonding_time": "1814400000000000",
            "max_validators": 100,
            "max_entries": 7,
            "bond_denom": "cin"
          },
          "last_total_power": "0",
          "last_validator_powers": null,
          "validators": null,
          "delegations": null,
          "unbonding_delegations": null,
          "redelegations": null,
          "exported": false
        },
        "distribution": {
          "fee_pool": {
            "community_pool": null
          },
          "community_tax": "0.000000000000000000",
          "base_proposer_reward": "0.000000000000000000",
          "bonus_proposer_reward": "0.000000000000000000",
          "withdraw_addr_enabled": true,
          "delegator_withdraw_infos": null,
          "previous_proposer": "",
          "outstanding_rewards": null,
          "validator_accumulated_commissions": null,
          "validator_historical_rewards": null,
          "validator_current_rewards": null,
          "delegator_starting_infos": null,
          "validator_slash_events": null
        },
        "kyc": {
          "authorised_addresses": [
            "mxw1urazz6vuldjp09gtzft0nw2kuv25l0793c6m9w",
            "mxw1u7wn0ewe53csak2xl5nxaj45gangy3a4wq7xy7",
            "mxw1xl7awvx7e7yjm256hx676vcqavx5c232rrtqpx",
            "mxw1fkw4vdzgqd4jsvrt0whqjp6kr7mlt0rzl89lkv",
            "mxw1vhz42dpefjhfrufurh2wwkpdt0837s5hxamt0u",
            "mxw146xepk070h8h2znggp8rdffn3ym3fda5gfjwxm",
            "mxw17tx5936pw0xfcqe4g76wxefwdl3j4rpdygt5wf",
            "mxw1aglwdehkrgan9p86ea8kl75lkag2h0xtwj2d4e",
            "mxw1xs5946fk53jnsxd2axjtkjmw6ks3h4ducs5a7p",
            "mxw1vulu4lra8nd2aswz60xkj5uxnp9kw0fuq3e65g",
            "mxw1rnwy4utedvl7p2x49squm2a3a0d6gne4pe8h5w",
            "mxw1kvc7pvyu65sg0hgqc6tnu0rd40g5qwayrwtqnh",
            "mxw1vtqkfs7trns8jepp3mu8skqkcga90ky2zp7v7p",
            "mxw1rq9txn872hchzdau2c44t464fqdvn3ad4drkp8",
            "mxw1wc6dp6qrp48x3hjy6049l3f8phtkr9hqd2z5wh",
            "mxw19dgfsqpqnatfv298zna6wnlauv07kcvw386vew",
            "mxw1smcavtfea3mpsplsual2jyx3jcps8vjv8yh43v",
            "mxw1uzhu2au5r5gaafx6uj2hw87af44udw3wuehvvy",
            "mxw1v36a5t98pgywy59vhmwkr527u330uweqvxcj3p",
            "mxw16g5gj7slym5a3amnyajycc9zw8yqmd74agludz"
          ],
          "issuer_addresses": null,
          "provider_addresses": null,
          "whitelisted_addresses": null
        },
        "token": {
          "authorised_addresses": null,
          "issuer_addresses": null,
          "provider_addresses": null
        },
        "nameservice": {
          "authorised_addresses": null,
          "issuer_addresses": null,
          "provider_addresses": null,
          "genesis_alias_owners": null
        },
        "fee": {
          "fee_settings": [
            {
              "name": "default",
              "min": [
                {
                  "denom": "cin",
                  "amount": "10000000000000000"
                }
              ],
              "max": [
                {
                  "denom": "cin",
                  "amount": "1000000000000000000000000"
                }
              ],
              "percentage": "0.05"
            }
          ],
          "authorised_addresses": [
            "mxw1urazz6vuldjp09gtzft0nw2kuv25l0793c6m9w"
          ],
          "multiplier": "1",
          "assigned_fee": [
            {
              "name": "zero",
              "msg_type": "kyc-whitelist"
            },
            {
              "name": "zero",
              "msg_type": "kyc-whitelist"
            },
            {
              "name": "zero",
              "msg_type": "kyc-revokeWhitelist"
            },
            {
              "name": "zero",
              "msg_type": "fee-createFeeSetting"
            },
            {
              "name": "zero",
              "msg_type": "fee-createTxFeeSetting"
            },
            {
              "name": "zero",
              "msg_type": "fee-createMultiplier"
            },
            {
              "name": "zero",
              "msg_type": "fee-createAccFeeSetting"
            }
          ]
        },
        "maintenance": {
          "maintainers": null,
          "starting_proposal_id": "1",
          "validator_set": [
            "mxwvalconspub1zcjduepqj7nxtu5vplj5rnymczca7qy84pt4ufxy408m9gz2eavyjpdhw08s8gcu3p"
          ]
        },
        "gentxs": [
          {
            "type": "cosmos-sdk/StdTx",
            "value": {
              "msg": [
                {
                  "type": "cosmos-sdk/MsgCreateValidator",
                  "value": {
                    "description": {
                      "moniker": "gohck.local",
                      "identity": "",
                      "website": "",
                      "security_contact": "",
                      "details": ""
                    },
                    "commission": {
                      "rate": "0.100000000000000000",
                      "max_rate": "0.200000000000000000",
                      "max_change_rate": "0.010000000000000000"
                    },
                    "min_self_delegation": "1",
                    "delegator_address": "mxw1urazz6vuldjp09gtzft0nw2kuv25l0793c6m9w",
                    "validator_address": "mxwvaloper1urazz6vuldjp09gtzft0nw2kuv25l079fh99g4",
                    "pubkey": "mxwvalconspub1zcjduepqj7nxtu5vplj5rnymczca7qy84pt4ufxy408m9gz2eavyjpdhw08s8gcu3p",
                    "value": {
                      "denom": "cin",
                      "amount": "100000000000000000000"
                    }
                  }
                }
              ],
              "fee": {
                "amount": [
                  {
                    "denom": "cin",
                    "amount": "0"
                  }
                ],
                "gas": "0"
              },
              "signatures": [
                {
                  "pub_key": {
                    "type": "tendermint/PubKeySecp256k1",
                    "value": "AqlVNA8KELZX2GgQ7dTCFIcmrDtZgBb1ajKrT9/AQ7Re"
                  },
                  "signature": "MA4EcO21wFbSzWy1LFSZyXiFNf+7nIEWcy6oHIEQiSUDfGZvlZQLFqxQyigVCaZXAlHaYwoZQPkdH60tqmMXqQ=="
                }
              ],
              "memo": "13d45324d870a0bcb93affb09ea58a774338aafd@192.168.20.42:26656"
            }
          }
        ]
      }
    }
  }
}
```
