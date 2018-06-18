
contract_instance (main file) is used for building ethereum contract functions in an easy way
ContractInstance class is a decorator for web3 contract functions

You can call sign-functions without signing them manually

**It is only functions-decorator.** 

**Note!** Call back function is not included 


Usage:

 ```
 contract = ContractInstance('contract_json_file', contract_address, eth, web3)
 ```

* Usage of constant function:  

  - Empty-params  
  
     ```python
     result = contract.getSmth();  
     print(result) => smth
     ```
 
  - Non empty-params  
 
     ```python
     result = contract.calcSum(1, 2);  
     print(result) => sum
     ```  
     
 * Usage of sing-function:  

    ```python
    result = contract.addData(data, private_key="your private key");   
    print(result) => transaction hash
    ```  
   
 **Private key is required for sing-functions**

If you want to specify a certain gas or your function is payable, add:  

```python
contract.addData(data, private_key="your private key", value=your value, gas=your gas);
```

**If you do not specify a tag, the default values are:** 
<div>
    &nbsp;&nbsp;&nbsp;&nbsp;Gas = 5x00000  
    &nbsp;&nbsp;&nbsp;&nbsp;Value = 0  
</div>
<br>

**The default network properties are:**  
<div class="footer">
    &nbsp;&nbsp;&nbsp;&nbsp;Chain id = 4 (Rinkeby)  
    &nbsp;&nbsp;&nbsp;&nbsp;Gas_price = 20gwei
</div>


---
1) If you want to change them at instance level, you could do:
```python
contract.set_network_parameters(yourChainId, yourGasPrice)
```

2) If you want to change them at global level (each contract instance to have than on init), you could go in config.py and change them there
