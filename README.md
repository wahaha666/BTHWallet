# BTHWallet
RESTful API

## Ethreum 

### Balance 
http get http://127.0.0.1:8080/ETH（测试网换成BTCTEST）/balance/0x2028aa76c84802cd61ab3bec4f142ca33743068b  <br>  
**正常响应 json：** <br>  
    `{ <br>  
        "balance": "1575119465000126000", "1."+space <br>  
        "message": "",  （为空） <br>  
        "txcount": "0xaf1" <br>  
    }` <br>  
**异常响应 json：** <br>  
    `{ <br>  
        "balance": "-1",  <br>  
        "message": "format error", （或者其他错误信息） <br>  
        "txcount": "-1" <br>  
    }` <br>  
### Push rawtx
同比特币 <br>  

## Bitcoin

### Unspent
http get http://127.0.0.1:8080/BTC(测试网换成BTCTEST)/unspend/1Hz96kJKF2HLPGY15JWLB5m9qGNxvt8tHJ  <br>  
**正常响应 json:** <br>  
    `{<br>  
        "message": "",  <br>  
        "uTXO": [ <br>  
            { <br>  
                "confirmations": 94,  <br>  
                "output_no": 0,  <br>  
                "txId": "dd67f8edce5c907784212c9813e414fa6b8c4bc188b1023116fa868371905ce2", <br>  
                "value": "12.57566486" <br>  
            } <br>  
        ] <br>  
    }` <br>  

**异常响应 json:** <br>  
    `{ <br>  
        "error": "400 Bad Request", (或者其他错误信息) <br>  
        "uTXO": null <br>  
    }` <br>  

### Push rawtx
http post http://127.0.0.1:8080/BTCTEST（主网改为BTC）/pushtx  rawtx="hextx" <br>  
**正常响应 json:** <br>  
    `{ <br>  
        "message": "",  <br>  
        "txid": "7ac190df8bee2ca7c55848179f10d279d3fd344b631654a4c3b7db6f56de3c98" <br>  
    }` <br>  

**异常响应 json:**
    `{ <br>  
        "message": "400 Bad Request", (或者其他错误信息) <br>  
        "txid": "" <br>  
    }` <br>  






