# BTHWallet
RESTful API

## Ethereum
工具：httpie 
`apt-get install httpie`
### Balance 
`http get http://127.0.0.1:8080/ETH（测试网换成BTCTEST）/balance/0x2028aa76c84802cd61ab3bec4f142ca33743068b ` <br>
**正常响应 json：** <br> 
```
    {  
        "balance": "1575119465000126000",  
        "message": "",  （为空）  
        "txcount": "0xaf1"   
    }   
 ```
**异常响应 json：** <br>  
```
    {  
        "balance": "-1",   
        "message": "format error", （或者其他错误信息）  
        "txcount": "-1"   
    }  
 ```
### Push rawtx
同比特币 <br>  

## Bitcoin

### Unspent
`http get http://127.0.0.1:8080/BTC(测试网换成BTCTEST)/unspent/1Hz96kJKF2HLPGY15JWLB5m9qGNxvt8tHJ`  <br>  
**正常响应 json:** <br>  
```
    {
        "message": "",   
        "uTXO": [  
            {   
                "confirmations": 94,  
                "output_no": 0,   
                "txId": "dd67f8edce5c907784212c9813e414fa6b8c4bc188b1023116fa868371905ce2",  
                "value": "12.57566486"   
            } 
        ]  
    }  
  ```

**异常响应 json:** <br>  
```
    {   
        "error": "400 Bad Request", (或者其他错误信息)  
        "uTXO": null   
    } 
```
### Push rawtx
`http post http://127.0.0.1:8080/BTCTEST（主网改为BTC）/pushtx  rawtx="hextx"` <br> 
**正常响应 json:** <br>  
```
   {
        "message": "", 
        "txid": "7ac190df8bee2ca7c55848179f10d279d3fd344b631654a4c3b7db6f56de3c98" 
    }
```
**异常响应 json:**
```
    {  
        "message": "400 Bad Request", (或者其他错误信息)
        "txid": "" 
    }
```    






