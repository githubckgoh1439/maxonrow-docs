# Query APIs

### Query DumpConsensusState
DumpConsensusState dumps consensus state. This is just a snapshot of consensus state, and it will not persist.

#### Return Type
Return round states
```
type ResultConsensusState struct {
    RoundState json.RawMessage `
}
```

#### Example

Run the command:
```
curl 'http://localhost:26657/dump_consensus_state'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "round_state": {
      "height": "3331",
      "round": "0",
      "step": 1,
      "start_time": "2019-10-10T03:40:45.881035Z",
      "commit_time": "2019-10-10T03:40:40.881035Z",
      "validators": {
        "validators": [
          {
            "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
            "pub_key": {
              "type": "tendermint/PubKeyEd25519",
              "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
            },
            "voting_power": "100",
            "proposer_priority": "0"
          }
        ],
        "proposer": {
          "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
          "pub_key": {
            "type": "tendermint/PubKeyEd25519",
            "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
          },
          "voting_power": "100",
          "proposer_priority": "0"
        }
      },
      "proposal": null,
      "proposal_block": null,
      "proposal_block_parts": null,
      "locked_round": "-1",
      "locked_block": null,
      "locked_block_parts": null,
      "valid_round": "-1",
      "valid_block": null,
      "valid_block_parts": null,
      "votes": [
        {
          "round": "0",
          "prevotes": [
            "nil-Vote"
          ],
          "prevotes_bit_array": "BA{1:_} 0/100 = 0.00",
          "precommits": [
            "nil-Vote"
          ],
          "precommits_bit_array": "BA{1:_} 0/100 = 0.00"
        }
      ],
      "commit_round": "-1",
      "last_commit": {
        "votes": [
          "Vote{0:CE9CA702BE31 3330/00/2(Precommit) 55C9AD369D14 72D33688A200 @ 2019-10-10T03:40:40.862611Z}"
        ],
        "votes_bit_array": "BA{1:x} 100/100 = 1.00",
        "peer_maj_23s": {}
      },
      "last_validators": {
        "validators": [
          {
            "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
            "pub_key": {
              "type": "tendermint/PubKeyEd25519",
              "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
            },
            "voting_power": "100",
            "proposer_priority": "0"
          }
        ],
        "proposer": {
          "address": "CE9CA702BE3125D62B062BB925A552882CBC08CA",
          "pub_key": {
            "type": "tendermint/PubKeyEd25519",
            "value": "l6Zl8owP5UHMm8Cx3wCHqFdeJMSrz7KgSs9YSQW3c88="
          },
          "voting_power": "100",
          "proposer_priority": "0"
        }
      },
      "triggered_timeout_precommit": false
    },
    "peers": []
  }
}
```

