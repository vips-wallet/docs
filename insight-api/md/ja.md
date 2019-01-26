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

## ？？？ [POST /addrs]

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
## ？？？ [GET /tx/{txid}]
## ？？？ [GET /txs]
## ？？？ [GET /txs/{txid}/receipt]
## ？？？ [POST /tx/send]
## ？？？ [GET /rawtx/{txid}]

# Group contracts
## ？？？ [GET /contracts/{contractaddress}/hash/{contracthash}/call]
## ？？？ [GET /contracts/{contractaddress}/info]
## ？？？ [GET /contracts/{contractaddress}/get-erc20-info]

# Group erc20
## ？？？ [GET /erc20/search]
## ？？？ [GET /erc20/balances]

## ？？？ [GET /erc20/{contractAddress}]
## ？？？ [GET /erc20/{contractAddress}/transfers]
## ？？？ [GET /erc20/{contractAddress}/balances]

# Group tokens

## ？？？ [GET /tokens]
## ？？？ [GET /tokens/{contractBaseAddress}/addresses/{accountAddress}/balance]
## ？？？ [GET /tokens/{contractBaseAddress}/transactions]
## ？？？ [GET /tokens/{contractBaseAddress}/total-supply]

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
## ？？？ [GET /utils/estimatefee]
## ？？？ [GET /utils/minestimatefee]
## ？？？ [GET /markets/info]
## ？？？ [GET /currency]
## ？？？ [GET /status]
## ？？？ [GET /sync]
## ？？？ [GET /peer]

## バージョン取得 [GET /version]

+ Response 200 (application/json)
  + Body
    {
      "version":"0.0.23"
    }

## ？？？ [GET /dgpinfo]
