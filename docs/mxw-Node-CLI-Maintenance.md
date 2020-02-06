# Maintenance Module


### How to use
Maintenance Consist of Msgs:   

```
maintenance-submitProposal  
- This is the msg type used to create a proposal from maintainers.  

maintenance-castAction 
- This is the msg type used for maintainers to cast “approve” or “reject” on certain proposal.  
```

### submit-proposal 
submit-proposal is used to submit proposal 
```
Usage :
mxwcli tx maintenance submit-proposal [proposal name] --fee-collector [address that wish to be set as fee collector] --fee-collector-module [fee collector for module] --proposal-type [proposal type] --title [proposal title] --from [maintainers] --chain-id [chain’s id] --fees 0cin --gas 0 --action [action] --description [proposal description] --node [remote node you wish to connect to]  

Example :

mxwcli tx maintenance submit-proposal add-token-feeCollector --fee-collector mxw1g797vyveqvn4dqr70cw9y56n2wurxt9ze2n7xf --fee-collector-module token --proposal-type fee --title Add-token-feeCollector --from acc-18 --chain-id uatnet --fees 0cin --gas 0 --action add --description "add token fee collector" --node https://uatnet.usdp.io:443  


Available proposal type: 

token 
1. Able to set authorised address 
2. Able to set issuer address 
3. Able to set provider address 

kyc 
1. Able to set authorised address 
2. Able to set issuer address 
3. Able to set provider address 

nameservice 
1. Able to set authorised address 
2. Able to set issuer address 
3. Able to set provider address 

fee 
1. Able to set authorised address 
2. Able to set token/ nameservice collector address 

validator 
1. Whitelist validator address 

nonfungible 
1. Able to set authorised address 
2. Able to set issuer address 
3. Able to set provider address 
```

### Cast-action 
Cast-action is used to Approve/ reject proposal
```
Usage :
Mxwcli tx maintenance cast-action [proposal id] --action [approve/reject] --fees 0cin --from [maintainers] --gas 0 --chain-id [chain’s id] --node [remote node you wish to connect to]

Example :

mxwcli tx maintenance cast-action 1 --action approve --fees 0cin --from acc-19 --gas 0 --chain-id uatnet --node https://uatnet.usdp.io:443  
```


