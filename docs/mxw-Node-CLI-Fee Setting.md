# Fee Setting Module


### How to use
Fee Settings Consist of Msgs:   

```
fee-updateFeeSetting 
- This is the message type used to create the system fee setting. Eg. “default”, “zero”, “transfer” and etc. 
- This message is used to edit the fee setting as well. 

fee-deleteFeeSetting 
- This is the message type used to delete the fee setting in cli. 

fee-assignFeeToMsg 
- This is the message type used to assign fee setting to message. 

fee-updateMultiplier 
- This is the message type used to create, update the system fee multiplier. 

fee-updateTokenMultiplier 
- This is the message type used to create, update the token fee multiplier. 

fee-assignFeeToToken 
- This is the message type used to assign fee setting to token by token action and token symbol. 

fee-assignFeeToAcc 
- This is the message type used to assign fee setting to account.

fee-deleteAccFeeSetting
- This is the message type used to delete an account of the fee setting.
```

### create-sysfee 
create-sysfee is used to create new fee setting
```
Usage :
mxwcli tx fee create-sysfee --name [fee name] --min [minimum amount] --max [maximum amount] --percentage [percentage] --gas 0 --fees 0cin --from [fee authorised address] --chain-id [chain’s id] --node [remote node you wish to connect to] 

Example :

mxwcli tx fee create-sysfee --name default --min 50000000000000000cin --max 10000000000000000000000000cin --percentage 0.005 --gas 0 --fees 0cin --from feeIssuer --chain-id uatnet --node https://uatnet.usdp.io:443 
```


### edit-sysfee 
edit-sysfee is used to update fee setting
```
Usage :
mxwcli tx fee edit-sysfee [fee name] --min [minimum amount] --max [maximum amount] --percentage [percentage] --gas 0 --fees 0cin --from [fee authorised address] --chain-id [chain’s id] --node [remote node you wish to connect to]  

Example :

mxwcli tx fee edit-sysfee default --min 50000000000000000cin --max 10000000000000000000000000cin --percentage 0.005 --gas 0 --fees 0cin --from feeIssuer --chain-id uatnet --node https://uatnet.usdp.io:443  
```

### delete-sysfee 
delete-sysfee is used to delete fee setting
```
Usage :
mxwcli tx fee delete-sysfee [fee name] --from [fee authorised address] --fees 0cin --gas0 --chain-id [chain’s id] --node [remote node you wish to connect to]  

Example :

mxwcli tx fee delete-sysfee default --from feeAuth --fees 0cin --gas 0 --chain-id uatnet --node https://uatnet.usdp.io:443  
```

### msg 
msg is used to assign a fee setting to a message type
```
Usage :
mxwcli tx fee msg [msg type] --name [fee name] --from [fee authorised address] --chain-id [chain’s id] --fees 0cin --gas 0 --node [remote node you wish to connect to]  

Example :

mxwcli tx fee msg fee-updateFeeSetting --name zero --from feeAuth --chain-id uatnet --fees 0cin --gas 0 --node https://uatnet.usdp.io:443  
```

### account 
account is used to assign a fee setting to an account
```
Usage :
mxwcli tx fee create-sysfee --name [fee name] --min [minimum amount] --max [maximum amount] --percentage [percentage] --gas 0 --fees 0cin --from [fee authorised address] --chain-id [chain’s id] --node [remote node you wish to connect to] 

Example :

mxwcli tx fee account mxw16f6dsgrxdk6cfpm9kyz9qdp7v0k2azlrkj95vu --name zero --from foundation --chain-id uatnet --gas 0 --fees 0cin --node https://uatnet.usdp.io:443 
```

### fee-multiplier 
create-sysfee is used to set/update fee multiplier. Multiplier not allow zero. 
```
Usage :
mxwcli tx fee fee-multiplier [multiplier you wish to set] --from [fee authorised address] --fees 0cin --gas 0 --chain-id [chain’s id] --node [remote node you wish to connect to]  

Example :

mxwcli tx fee fee-multiplier 1 --from feeAuth --fees 0cin --gas 0 --chain-id uatnet --node https://uatnet.usdp.io:443 
```

### token-fee-multiplier 
create-sysfee is used to Set/update token fee multiplier. 
```
Usage :
mxwcli tx fee token-fee-multiplier [multiplier you wish to set] --from [fee authorised address] --fees 0cin --gas 0 --chain-id [chain’s id] --node [remote node you wish to connect to]  

Example :

mxwcli tx fee token-fee-multiplier 1 --from feeAuth --fees 0cin --gas 0 --chain-id uatnet --node https://uatnet.usdp.io:443 
```

### token 
create-sysfee is used to Assign/update a fee setting to a token(fungible/ nonfungible) 
```
Usage :
mxwcli tx fee token [token symbol] [token action] --name [fee setting name] --from [fee authorised address] --gas 0 --fees 0cin --chain-id [chain’s id] --node [remote node you wish to connect to]  

Example :

mxwcli tx fee token MUL transfer --name default --from feeAuth --gas 0 --fees 0cin --chain-id uatnet --node https://uatnet.usdp.io:443  

Available token action: 
* transfer 
* mint 
* burn 
* transferOwnership 
* acceptOwnership 
```

### delete-acc-fee 
delete-acc-fee is used to delete an account of the fee setting. 
```
Usage :
mxwcli tx fee delete-acc-fee [account address] --from [fee authorised address] --fees 0cin --gas 0 --chain-id [chain’s id] --node [remote node you wish to connect to]  
  

Example :

mxwcli tx fee delete-acc-fee mxw16f6dsgrxdk6cfpm9kyz9qdp7v0k2azlrkj95vu --from feeAuth --gas 0 --fees 0cin --chain-id uatnet --node https://uatnet.usdp.io:443  

```