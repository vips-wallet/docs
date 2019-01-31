FORMAT: 1A
HOST: https://insight.vipstarco.in/api

# VIPSTARCOIN insight-api

insight APIドキュメント

# Group address

## アドレス情報 [GET /addr/{addr}]

指定アドレスの情報を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Body
    {
      "addrStr":"VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
      "balance":10000024024.4825,
      "balanceSat":1000002402448250000,
      "totalReceived":10000024024.4825,
      "totalReceivedSat":1000002402448250000,
      "totalSent":0,
      "totalSentSat":0,
      "unconfirmedBalance":0,
      "unconfirmedBalanceSat":0,
      "unconfirmedTxApperances":0,
      "txApperances":14,
      "transactions":[
        "40fa77f84fb2646420f93ede05fe400a3b6fdb14df05a00d107de2eb5c7c7d84",
        "671f2613ae0bde8cd8fe63c4d671a3d3a75358d0481bf2993712ca1917846f61",
        "d13db7decc81827c2ef2e8fdd544edd64e74e3907c160c7977a20d6bae302764",
        "377e60abca917875951f4beaea3618f5516ff1e4cf3a12a88edff7bce0b6a6f6",
        "3ed5e732f1833a0aa5557f66e49d5b1bfdcc7a55b86fdfa8c6ccc1e520820057",
        "47f31ef2caf38e8baffae79403fb11e73b4ed452cafe7e4bb5b8d7cd52c0fd2b",
        "c94ebad6ae139de7856ab37caa7c3aa7289f3e52ac27c779aaa97760fac4250d",
        "10fbbf0bf6bf018508ae1f23f96aa709a6f7cb5308b8ce74ad9bd4300bf72b20",
        "bee93e9c1f454cc1ff458d9fab7b1fa6c60295dc7d4878807a9b9e3b300cbc63",
        "3e4ee042564fc45a265cab2b155251894a87bdd4f4e365fde8154fb9155e8439",
        "d94945af5c27b2075c378004f9a15a16e14f69d3181b610d06a78a6f4a440088",
        "ff5f24123dbf18eea329bba4a29ea37b52753063c01550df142c1c2599c18a12",
        "29ce468caa3ac1ed7caed580f6f732861db456e6158c71137aa644625ebed9e0",
        "96e8bb7312b45b65171b7ea0c8999ca9f91ef947863e9b31089f38ea07f667a7"
      ]
    }

## 残高取得 [GET /addr/{addr}/balance]

指定アドレスの検証済み残高を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

## 未検証残高取得 [GET /addr/{addr}/unconfirmedBalance]

指定アドレスの未検証残高を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

## UTXO取得 [GET /addr/{addr}/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

## 総受取額取得 [GET /addr/{addr}/totalReceived]

指定アドレスの総受取額を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

## 総送金額取得 [GET /addr/{addr}/totalSent]

指定アドレスの総送金額を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

カンマ区切りリストのVIPSTARCOINアドレスを指定し、複数アドレスの情報を一括で取得する。

## トランザクション履歴取得 [POST /addrs/txs]

指定アドレスのトランザクション履歴を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)
  + `from`: 0 (int, optional) - 開始オフセット
  + `to`: 10 (int, optional) - 終了オフセット

## UTXO取得 [POST /addrs/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

## 検証済み残高取得 [GET /addrs/{addrs}/balance]

指定アドレスの検証済み残高を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

## トランザクション履歴取得 [GET /addrs/{addrs}/txs]

指定アドレスのトランザクション履歴を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

## 検証済みUTXO取得 [GET /addrs/{addrs}/unspent]

指定アドレスの検証済みUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

## UTXO取得 [GET /addrs/{addrs}/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

# Group blocks

## 一覧取得 [GET /blocks]

+ Parameters
  + `blockDate`: (string, optional)
  + `startTimestamp`: (number, optional)
  + `limit`: (number, optional)

## 指定ブロック情報取得 [GET /block/{blockHash}]

+ Parameters
  + `blockHash`: (string, required)

## 指定ブロック生データ取得 [GET /rawblock/{blockHash}]

+ Parameters
  + `blockHash`: (string, required)

## ブロック高指定 [GET /block-index/{height}]

+ Parameters
  + `height`: (number, required)

# Group transaction

トランザクション情報の取得・送信を行う。

## 指定トランザクション情報取得 [GET /tx/{txid}]

+ Parameters
  + `txid`: c3bb9785e6994e8f965a664a475dc09cf525406eed0e6f64bad65269f66cf5b8 (string, required) - TXID

+ Response 200 (application/json)
  + Body
    {
      "txid":"c3bb9785e6994e8f965a664a475dc09cf525406eed0e6f64bad65269f66cf5b8",
      "version":2,
      "locktime":0,
      "isqrc20Transfer":false,
      "vin":[
        {
          "coinbase":"510101",
          "sequence":4294967295,
          "n":0
        }
      ],
      "vout":[
        {
          "value":"10000000000.00000000",
          "n":0,
          "scriptPubKey":{
            "hex":"21028d616e785c4cd7b20866a1cbbf84b4cb172b9609a295ce52e3b37e0396cd6e1aac",
            "asm":"028d616e785c4cd7b20866a1cbbf84b4cb172b9609a295ce52e3b37e0396cd6e1a OP_CHECKSIG",
            "addresses":[
              "VD5tffByCTgKtQssUxuSuykcsTV6PFULfE"
            ],
            "type":"pubkeyhash"
          },
          "spentTxId":"bd8cc8c2af3648293b02dbcd359cfd556dc175db13721a60cd6feab8a950559a",
          "spentIndex":0,
          "spentHeight":506
        },
        {
          "value":"0.00000000",
          "n":1,
          "scriptPubKey":{
            "hex":"6a24aa21a9ede2f61c3f71d1defd3fa999dfa36953755c690689799962b48bebd836974e8cf9",
            "asm":"OP_RETURN aa21a9ede2f61c3f71d1defd3fa999dfa36953755c690689799962b48bebd836974e8cf9"
          },
          "spentTxId":null,
          "spentIndex":null,
          "spentHeight":null
        }
      ],
      "blockhash":"0000e0e7e28aef099b64e3fc81d8b9e7992e2adc56e2e573f8c025ce634db4e4",
      "blockheight":1,
      "confirmations":417217,
      "time":1522319429,
      "blocktime":1522319429,
      "isCoinBase":true,
      "valueOut":10000000000,
      "size":145
    }

## ？？？ [GET /txs/{txid}/receipt]
## ？？？ [POST /tx/send]
## ？？？ [GET /rawtx/{txid}]

# Group contracts

## コントラクトコール [GET /contracts/{contractaddress}/hash/{contracthash}/call]

コントラクトのコールメソッドを呼び出す。

+ Parameters
  + `contractaddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス
  + `contracthash`: 70a082310000000000000000000000000c97b859de459789c2df463ff28160d1508f555e (string, required) - コントラクトハッシュ
  + `from`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, optional) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Body
    {
      "address": "32033595a988dd71bbe3225a829789d36adf09dd",
      "executionResult": {
          "gasUsed": 23314,
          "excepted": "None",
          "newAddress": "32033595a988dd71bbe3225a829789d36adf09dd",
          "output": "0000000000000000000000000000000000000000000000000000000000000000",
          "codeDeposit": 0,
          "gasRefunded": 0,
          "depositSize": 0,
          "gasForDeposit": 0
      },
      "transactionReceipt": {
          "stateRoot": "c344f164427f2c0415990171278385d14f5692ce1b78a3447fc424fd642a692b",
          "gasUsed": 23314,
          "bloom": "00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
          "log": []
      }
    }

## コントラクト情報取得 [GET /contracts/{contractaddress}/info]

コントラクト情報を取得する。

+ Parameters
  + `contractaddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス

+ Response 200 (application/json)
  + Body
    {
      "address": "813cd81362ce245df1c50aac7e7769c852d60968",
      "balance": 0,
      "storage": {
          "221e97c0259b4601b584ba08f1fcfd89ccd5b46ec252ee4be9f524e9ea321e4d": {
              "a584c5417a94fbae21de424cdf6b8de70a2112b5b6dd50dde8782a55060e1c76": "00000000000000000000000000000000000000000000010f0cf064dd59200000"
          },
          "290decd9548b62a8d60345a988386fc84ba6bc95484008f6362f93160ef3e563": {
              "0000000000000000000000000000000000000000000000000000000000000000": "e382b5e383b3e38397e383ab0000000000000000000000000000000000000018"
          },
          "321106b295bc14696a530e170de2157229d823a1ba30b8dd747c952e15060464": {
              "529728361e2a076cafc260287e97c1cbaef495f36f15ce18ef01656ecef9f795": "00000000000000000000000000000000000000000000010f0cf064dd59200000"
          },
          "405787fa12a823e0f2b7631cc41b3ba8828b3321ca811111fa75cd3aa3bb5ace": {
              "0000000000000000000000000000000000000000000000000000000000000002": "0000000000000000000000000000000000000000000000000000000000000012"
          },
          "b10e2d527612073b26eecdfd717e6a320cf44b4afac2b0732d9fcbe2b7fa0cf6": {
              "0000000000000000000000000000000000000000000000000000000000000001": "53414d504c45000000000000000000000000000000000000000000000000000c"
          },
          "c2575a0e9e593c00f959f8c92f12db2869c3395a3b0502d05e2516446f71f85b": {
              "0000000000000000000000000000000000000000000000000000000000000003": "00000000000000000000000000000000000000000000021e19e0c9bab2400000"
          }
      },
      "code": "6080604052600436106100ba576000357c0100000000000000000000000000000000000000000000000000000000900463ffffffff16806306fdde03146100bf578063095ea7b31461014f57806318160ddd146101b457806323b872dd146101df578063313ce5671461026457806342966c681461029557806370a08231146102da57806379cc67901461033157806395d89b4114610396578063a9059cbb14610426578063cae9ca511461048b578063dd62ed3e14610536575b600080fd5b3480156100cb57600080fd5b506100d46105ad565b6040518080602001828103825283818151815260200191508051906020019080838360005b838110156101145780820151818401526020810190506100f9565b50505050905090810190601f1680156101415780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561015b57600080fd5b5061019a600480360381019080803573ffffffffffffffffffffffffffffffffffffffff1690602001909291908035906020019092919050505061064b565b604051808215151515815260200191505060405180910390f35b3480156101c057600080fd5b506101c961073d565b6040518082815260200191505060405180910390f35b3480156101eb57600080fd5b5061024a600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610743565b604051808215151515815260200191505060405180910390f35b34801561027057600080fd5b50610279610870565b604051808260ff1660ff16815260200191505060405180910390f35b3480156102a157600080fd5b506102c060048036038101908080359060200190929190505050610883565b604051808215151515815260200191505060405180910390f35b3480156102e657600080fd5b5061031b600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610987565b6040518082815260200191505060405180910390f35b34801561033d57600080fd5b5061037c600480360381019080803573ffffffffffffffffffffffffffffffffffffffff1690602001909291908035906020019092919050505061099f565b604051808215151515815260200191505060405180910390f35b3480156103a257600080fd5b506103ab610bb9565b6040518080602001828103825283818151815260200191508051906020019080838360005b838110156103eb5780820151818401526020810190506103d0565b50505050905090810190601f1680156104185780820380516001836020036101000a031916815260200191505b509250505060405180910390f35b34801561043257600080fd5b50610471600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190505050610c57565b604051808215151515815260200191505060405180910390f35b34801561049757600080fd5b5061051c600480360381019080803573ffffffffffffffffffffffffffffffffffffffff16906020019092919080359060200190929190803590602001908201803590602001908080601f0160208091040260200160405190810160405280939291908181526020018383808284378201915050505050509192919290505050610c6e565b604051808215151515815260200191505060405180910390f35b34801561054257600080fd5b50610597600480360381019080803573ffffffffffffffffffffffffffffffffffffffff169060200190929190803573ffffffffffffffffffffffffffffffffffffffff169060200190929190505050610c7b565b6040518082815260200191505060405180910390f35b60008054600181600116156101000203166002900480601f0160208091040260200160405190810160405280929190818152602001828054600181600116156101000203166002900480156106435780601f1061061857610100808354040283529160200191610643565b820191906000526020600020905b81548152906001019060200180831161062657829003601f168201915b505050505081565b600081600560003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020819055508273ffffffffffffffffffffffffffffffffffffffff163373ffffffffffffffffffffffffffffffffffffffff167f8c5be1e5ebec7d5bd14f71427d1e84f3dd0314c0f7b2291e5b200ac8c7c3b925846040518082815260200191505060405180910390a36001905092915050565b60035481565b6000600560008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205482111515156107d057600080fd5b81600560008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008282540392505081905550610865848484610ca0565b600190509392505050565b600260009054906101000a900460ff1681565b600081600460003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054101515156108d357600080fd5b81600460003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008282540392505081905550816003600082825403925050819055503373ffffffffffffffffffffffffffffffffffffffff167fcc16f5dbb4873280815c1ee09dbd06736cffcc184412cf7a71a0fdb75d397ca5836040518082815260200191505060405180910390a260019050919050565b60046020528060005260406000206000915090505481565b600081600460008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054101515156109ef57600080fd5b600560008473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020548211151515610a7a57600080fd5b81600460008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000828254039250508190555081600560008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060003373ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002060008282540392505081905550816003600082825403925050819055508273ffffffffffffffffffffffffffffffffffffffff167fcc16f5dbb4873280815c1ee09dbd06736cffcc184412cf7a71a0fdb75d397ca5836040518082815260200191505060405180910390a26001905092915050565b60018054600181600116156101000203166002900480601f016020809104026020016040519081016040528092919081815260200182805460018160011615610100020316600290048015610c4f5780601f10610c2457610100808354040283529160200191610c4f565b820191906000526020600020905b815481529060010190602001808311610c3257829003601f168201915b505050505081565b6000610c64338484610ca0565b6001905092915050565b6000600190509392505050565b6005602052816000526040600020602052806000526040600020600091509150505481565b60008073ffffffffffffffffffffffffffffffffffffffff168373ffffffffffffffffffffffffffffffffffffffff1614151515610cdd57600080fd5b81600460008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205410151515610d2b57600080fd5b600460008473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205482600460008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020540110151515610dba57600080fd5b600460008473ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054600460008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205401905081600460008673ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000206000828254039250508190555081600460008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff168152602001908152602001600020600082825401925050819055508273ffffffffffffffffffffffffffffffffffffffff168473ffffffffffffffffffffffffffffffffffffffff167fddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef846040518082815260200191505060405180910390a380600460008573ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff16815260200190815260200160002054600460008773ffffffffffffffffffffffffffffffffffffffff1673ffffffffffffffffffffffffffffffffffffffff1681526020019081526020016000205401141515610fc757fe5b505050505600a165627a7a7230582099d34112bd03ec7a90e6f88a38ea7b33e1bd98ca70d5b10be656970d6dd35fe30029"
    }

## VRC20トークン情報 [GET /contracts/{contractaddress}/get-erc20-info]

VRC20トークンのシンボル情報および小数点以下桁数を取得する。

+ Parameters
  + `contractaddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス

+ Response 200 (application/json)
  + Body
    {
      "symbol": "SAMPLE",
      "decimals": "18"
    }

# Group erc20

## 部分一致検索 [GET /erc20/search{?query}]

VRC20トークン情報をクエリ文字列で部分一致検索して取得する。

+ Parameters
  + `query`: sample (string, required) - クエリ文字列

+ Response 200 (application/json)
  + Body
    {
      "count": 1,
      "items": [
            {
                  "_id": "5c4c71e5cb90174a434eab55",
                  "tx_hash": "1e5ce58f5498cf6746b68856e5d8898a0a2afa057c17c5da7e1316be2fad38c5",
                  "vout_idx": 1,
                  "__v": 0,
                  "block_height": 417449,
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "contract_address_base": "VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq",
                  "created_at": "2019-01-26T14:42:45.062Z",
                  "decimals": "18",
                  "exception": false,
                  "name": "サンプル",
                  "symbol": "SAMPLE",
                  "total_supply": "10000000000000000000000",
                  "updated_at": "2019-01-26T14:42:45.062Z",
                  "version": ""
            }
      ]
    }
+ Response 422 (text/plain)
    Bad query

## アドレス指定検索 [GET /erc20/balances{?balanceAddress}]

VRC20トークンの保有状況をVIPSTARCOINアドレスおよびコントラクトアドレスを指定して取得する。

+ Parameters
  + `balanceAddress`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)
  + `contractAddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, optional) - コントラクトアドレス

+ Response 200 (application/json)
  + Body
    [
      {
            "amount": "5000000000000000000000",
            "address": "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
            "address_eth": "0x0c97b859de459789c2df463ff28160d1508f555e",
            "contract": {
                  "_id": "5c4c71e5cb90174a434eab55",
                  "tx_hash": "1e5ce58f5498cf6746b68856e5d8898a0a2afa057c17c5da7e1316be2fad38c5",
                  "vout_idx": 1,
                  "__v": 0,
                  "block_height": 417449,
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "contract_address_base": "VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq",
                  "created_at": "2019-01-26T14:42:45.062Z",
                  "decimals": "18",
                  "exception": false,
                  "name": "サンプル",
                  "symbol": "SAMPLE",
                  "total_supply": "10000000000000000000000",
                  "updated_at": "2019-01-26T14:42:45.062Z",
                  "version": ""
            }
      }
    ]

+ Response 404 (text/plain)
    Not Found

## トークン情報取得 [GET /erc20/{contractAddress}]

VRC20トークンの基本情報を取得する。

+ Parameters
  + `contractAddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス
  + `address`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, optional) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Body
    {
      "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
      "total_supply": "10000000000000000000000",
      "decimals": "18",
      "name": "サンプル",
      "symbol": "SAMPLE",
      "version": "",
      "transfers_count": 1,
      "holders_count": 2
    }

+ Response 404 (text/plain)
    Not Found

## 転送履歴取得 [GET /erc20/{contractAddress}/transfers]

VRC20トークンの転送履歴を取得する

+ Parameters
  + `contractAddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス
  + `offset`: 0 (number, optional) - オフセット
  + `limit`: 100 (number, optional) - 取得上限
  + `addresses`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, optional) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Body
    {
      "limit": 100,
      "offset": 0,
      "count": 1,
      "items": [
            {
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "tx_hash": "39d3bf55b8cd08c53fefd72f637afc147286d95d15217b280f57469271c4444d",
                  "tx_time": 1548514603,
                  "from": "VTCfvohXJVC3ikp2fX5n1arTsFSpCfmtnf",
                  "from_eth": "0xb5749d2f105a91593b956a121fcf94e59278d562",
                  "to": "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
                  "to_eth": "0x0c97b859de459789c2df463ff28160d1508f555e",
                  "value": "5000000000000000000000"
            }
      ]
}

+ Response 404 (text/plain)
    Not Found

## トークン残高一覧取得 [GET /erc20/{contractAddress}/balances]

VRC20トークンの残高一覧を取得する。

+ Parameters
  + `contractAddress`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス
  + `offset`: 0 (number, optional) - オフセット
  + `limit`: 100 (number, optional) - 取得上限
  + `addresses`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, optional) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Body
    {
      "limit": 100,
      "offset": 0,
      "count": 2,
      "items": [
            {
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "address": "VTCfvohXJVC3ikp2fX5n1arTsFSpCfmtnf",
                  "address_eth": "0xb5749d2f105a91593b956a121fcf94e59278d562",
                  "amount": "5000000000000000000000"
            },
            {
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "address": "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
                  "address_eth": "0x0c97b859de459789c2df463ff28160d1508f555e",
                  "amount": "5000000000000000000000"
            }
      ]
    }

+ Response 404 (text/plain)
    Not Found

# Group tokens

## トークン一覧取得 [GET /tokens]

全トークン一覧を取得します。

+ Response 200 (application/json)
  + Body
    {
      "count": 431,
      "items": [
            {
                  "count_holders": 81,
                  "tx_hash": "cf5b8269877ab1e9e8e196c499f2de2fb6b7c42a2801c27d779a48e55a8d284c",
                  "vout_idx": 1,
                  "updated_at": "2018-11-25T07:51:49.476Z",
                  "block_height": 4112,
                  "contract_address": "374f4ccf8577536906ff3fa66927aaa3d5a0e66b",
                  "contract_address_base": "VFhg61tNqsYNqHjx3x18jYPJ4MjJARCXPh",
                  "decimals": "2",
                  "name": "VIPSTARCOIN発行記念2018/4/7",
                  "symbol": "ヌクモリティ",
                  "total_supply": "10000",
                  "version": "",
                  "exception": false,
                  "created_at": "2018-11-25T07:51:49.476Z",
                  "description": null
            },
            ...
            {
                  "count_holders": 2,
                  "tx_hash": "1e5ce58f5498cf6746b68856e5d8898a0a2afa057c17c5da7e1316be2fad38c5",
                  "vout_idx": 1,
                  "updated_at": "2019-01-26T14:42:45.062Z",
                  "block_height": 417449,
                  "contract_address": "813cd81362ce245df1c50aac7e7769c852d60968",
                  "contract_address_base": "VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq",
                  "decimals": "18",
                  "name": "サンプル",
                  "symbol": "SAMPLE",
                  "total_supply": "10000000000000000000000",
                  "version": "",
                  "exception": false,
                  "created_at": "2019-01-26T14:42:45.062Z",
                  "description": null
            }
      ]
    }

## トークン残高取得 [GET /tokens/{contractBaseAddress}/addresses/{accountAddress}/balance]

指定アドレスの指定コントラクトベースアドレスのトークン残高を取得する。

+ Parameters
  + `contractBaseAddress`: VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq (string, required) - コントラクトベースアドレス
  + `accountAddress`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (text/plain)
    5000000000000000000000

+ Response 404 (text/plain)
    Not Found

## トランザクション履歴取得 [GET /tokens/{contractBaseAddress}/transactions]

コントラクトベースアドレスを指定してトークンのトランザクション履歴を取得します。

+ Parameters
  + `contractBaseAddress`: VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq (string, required) - コントラクトベースアドレス
  + `offset`: 0 (number, optional) - オフセット
  + `limit`: 100 (number, optional) - 取得上限
  + `from_block`: 1 (number, optional) - 開始ブロック
  + `to_block`: 500000 (number, optional) - 終了ブロック
  + `from_date_time`: 2019-01-01T00:00:00.000Z (date, optional) - 開始日時
  + `to_date_time`: 2019-12-31T00:00:00.000Z (date, optional) - 終了日時
  + `addresses`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, optional) - VIPSTARCOINアドレス(カンマ区切りリスト)

+ Response 200 (application/json)
  + Body
    {
      "limit": 100,
      "offset": 0,
      "addresses": [],
      "from_block": null,
      "to_block": null,
      "from_date_time": null,
      "to_date_time": null,
      "count": 1,
      "items": [
            {
                  "contract_address_base": "VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq",
                  "block_height": 417459,
                  "tx_hash": "39d3bf55b8cd08c53fefd72f637afc147286d95d15217b280f57469271c4444d",
                  "from": "VTCfvohXJVC3ikp2fX5n1arTsFSpCfmtnf",
                  "to": "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
                  "value": "5000000000000000000000",
                  "block_date_time": "2019-01-26T14:56:43.000Z"
            }
      ]
    }

## トークン総発行数取得 [GET /tokens/{contractBaseAddress}/total-supply]

指定コントラクトベースアドレスのトークンの総発行数を取得する。

+ Parameters
  + `contractBaseAddress`: VNSZysD5evHML3Brt833UoQUmn5Hr5tRPq (string, required) - コントラクトベースアドレス
  + `format`: object (string, optional) - JSON形式で取得する場合指定

+ Response 200 (text/plain)
    10000000000000000000000

+ Response 200 (application/json)
  + Body
    {
      "total_supply": "10000000000000000000000"
    }

+ Response 404 (text/plain)
    Not Found

# Group messages
## ？？？ [GET /messages/verify]
## ？？？ [POST /messages/verify]

# Group statistics
## ？？？ [GET /supply]
## ？？？ [GET /statistics/total-supply]
## ？？？ [GET /statistics/circulating-supply]
## ？？？ [GET /statistics/supply]
## ？？？ [GET /statistics/fees]
## ？？？ [GET /statistics/transactions]
## ？？？ [GET /statistics/outputs]
## ？？？ [GET /statistics/difficulty]
## ？？？ [GET /statistics/stake]
## ？？？ [GET /statistics/total]
## ？？？ [GET /statistics/balance-intervals]
## ？？？ [GET /statistics/richer-than]
## ？？？ [GET /statistics/richest-addresses-list]

# Group utils

## トランザクション手数料計算 [GET /utils/estimatefee]

指定ブロック内に含めるためのトランザクション手数料を計算する。

+ Parameters
  + `nbBlocks`: 2 (number, optional) - 指定ブロック（カンマ区切りリスト）

+ Response 200 (application/json)
  + Body
    {
      "2":-1
    }

## 最小トランザクション手数料計算 [GET /utils/minestimatefee]

最小トランザクション手数料を計算する。

+ Parameters
  + `nbBlocks`: 6 (number, optional) - 指定ブロック

+ Response 200 (application/json)
  + Body
    {
      "fee_per_kb":0.00001
    }

## 市場情報取得 [GET /markets/info]

CMC(https://api.coinmarketcap.com/v1/ticker/vipstar-coin/)よりVIPSTARCOINの市場情報を取得する。

+ Response 200 (application/json)
  + Body
    {
      "price_usd": "0.0000603270",
      "price_btc": "0.00000002",
      "market_cap_usd": "2070760.0",
      "available_supply": "34325587621.0"
    }

## ビットコイン価格取得 [GET /currency]

bitstamp(https://www.bitstamp.net/api/ticker/)よりビットコイン価格を取得する。

+ Response 200 (application/json)
  + Body
    {
      "status": 200,
      "data": {
            "bitstamp": 3417.2
      }
    }

# Group status

## ステータス取得 [GET /status]

VIPSTARCOINブロックチェーンのステータスを取得する。（表示オプション：getDifficulty|getLastBlockHash|getBestBlockHash|getMiningInfo|getStakingInfo|getInfo）

+ Parameters
  + `q`: getInfo (string, optional) - 表示オプション

+ Response 200 (application/json)
  + Body
    {
      "info": {
            "version": 1000200,
            "protocolversion": 70003,
            "walletversion": 130000,
            "balance": 0,
            "blocks": 423096,
            "timeoffset": 0,
            "connections": 8,
            "proxy": "",
            "difficulty": {
                  "proof-of-work": 527.3764050697074,
                  "proof-of-stake": 5014263757.141127
            },
            "testnet": false,
            "keypoololdest": 1543123084,
            "keypoolsize": 100,
            "paytxfee": 0,
            "relayfee": 0.004,
            "errors": "",
            "network": "livenet",
            "reward": 950000000000
      }
    }

## 同期状況取得 [GET /sync]

VIPSTARCOINブロックチェーンとの同期状況を取得する。

+ Response 200 (application/json)
  + Body
    {
      "status": "finished",
      "blockChainHeight": 423099,
      "syncPercentage": 100,
      "height": 423099,
      "error": null,
      "type": "vipstarcoincore node"
    }

## ピア取得 [GET /peer]

VIPSTARCOIN insight-apiのピアを取得する。（ローカルホスト固定）

+ Response 200 (application/json)
  + Body
    {
      "connected": true,
      "host": "127.0.0.1",
      "port": null
    }

## バージョン取得 [GET /version]

VIPSTARCOIN insight-apiのバージョンを取得する。

+ Response 200 (application/json)
  + Body
    {
      "version":"0.0.23"
    }

## DgpInfo取得 [GET /dgpinfo]

最大ブロックサイズ、最低ガス価格、ブロックガスリミットを取得する。

+ Response 200 (application/json)
  + Body
    {
      "maxblocksize": 2000000,
      "mingasprice": 40,
      "blockgaslimit": 40000000
    }
