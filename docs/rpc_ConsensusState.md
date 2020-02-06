# Query APIs

### Query ConsensusState
ConsensusState returns a concise summary of the consensus state. This is just a snapshot of consensus state, and it will not persist.

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
curl 'localhost:26657/consensus_state'
```

The above command returns JSON structured like this:
```
{
  "jsonrpc": "2.0",
  "id": "",
  "result": {
    "round_state": {
      "height/round/step": "3227/0/1",
      "start_time": "2019-10-10T03:31:57.438164Z",
      "proposal_block_hash": "",
      "locked_block_hash": "",
      "valid_block_hash": "",
      "height_vote_set": [
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
      ]
    }
  }
}
```
