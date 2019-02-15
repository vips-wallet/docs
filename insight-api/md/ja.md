FORMAT: 1A
HOST: https://insight.vipstarco.in/api

# VIPSTARCOIN insight-api

insight APIドキュメント

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.en)

## Author

- 海野山猿 (Yamazaru Umino)
- ましろ (white)

## Original

See [GitHub repository](https://github.com/vips-wallet/docs/).

# Data Structures

## UTXO(object)

+ `address`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス
+ `txid`: 40fa77f84fb2646420f93ede05fe400a3b6fdb14df05a00d107de2eb5c7c7d84 (string, required) - TXID
+ `vout`: 0 (number, required) - VOUTインデックス
+ `scriptPubKey`: 76a9140c97b859de459789c2df463ff28160d1508f555e88ac (string, required) - scriptPubKey
+ `amount`: 217 (number, required) - 額
+ `satoshis`: 21700000000 (number, required) - 額(1e-8VIPS単位)
+ `isCoinBase`: false (boolean, required) - CoinBaseトランザクションフラグ
+ `isStake`: false (boolean, required) - Stakeトランザクションフラグ
+ `height`: 383487 (number, required) - ブロック高
+ `confirmations`: 46563 (number, required) - 検証数

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

## UTXO取得 [GET /addr/{addr}/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (application/json)
  + Attributes (array[UTXO], fixed-type)

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

## 検証済み残高取得 [GET /addr/{addr}/balance]

指定アドレスの検証済み残高を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (text/plain)
  + Body
    1000002402448250000

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

## 総受取額取得 [GET /addr/{addr}/totalReceived]

指定アドレスの総受取額を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (text/plain)
  + Body
    1000002402448250000

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

## 総送金額取得 [GET /addr/{addr}/totalSent]

指定アドレスの総送金額を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (text/plain)
  + Body
    0

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

## 未検証残高取得 [GET /addr/{addr}/unconfirmedBalance]

指定アドレスの未検証残高を取得する。

+ Parameters
  + `addr`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス

+ Response 200 (text/plain)
  + Body
    0

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

# Group addresses

カンマ区切りリストのVIPSTARCOINアドレスを指定し、複数アドレスの情報を一括で取得する。

## 検証済み残高取得 [GET /addrs/{addrs}/balance]

指定アドレスの検証済み残高を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

+ Response 200 (application/json)
  + Body
    {
      "unconfirmedBalance": 0,
      "balance": 1000002402448250000,
      "immature": 0
    }

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Invalid Argument: First argument is required, please include address data. Documentation: http://bitcore.io/guide/address.html. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Input string too short. Code:1

## UTXO取得 GETリクエスト版 [GET /addrs/{addrs}/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

+ Response 200 (application/json)
  + Attributes (array[UTXO], fixed-type)

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Invalid Argument: First argument is required, please include address data. Documentation: http://bitcore.io/guide/address.html. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Input string too short. Code:1

## UTXO取得 POSTリクエスト版 [POST /addrs/utxo]

指定アドレスのUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

+ Response 200 (application/json)
  + Attributes (array[UTXO], fixed-type)

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Invalid Argument: First argument is required, please include address data. Documentation: http://bitcore.io/guide/address.html. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Input string too short. Code:1

## 検証済みUTXO取得 [GET /addrs/{addrs}/unspent]

指定アドレスの検証済みUTXOを取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)

+ Response 200 (application/json)
  + Attributes (array[UTXO], fixed-type)

## トランザクション履歴取得 GETリクエスト版 [GET /addrs/{addrs}/txs]

指定アドレスのトランザクション履歴を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)
  + `from`: 0 (int, optional) - 開始オフセット
  + `to`: 10 (int, optional) - 終了オフセット

+ Response 200 (application/json)
  + Body
    {
      "totalItems": 14,
      "from": 0,
      "to": 10,
      "items": [
            {
                  "txid": "40fa77f84fb2646420f93ede05fe400a3b6fdb14df05a00d107de2eb5c7c7d84",
                  "version": 2,
                  "locktime": 0,
                  "vin": [
                        {
                              "txid": "3ed5e732f1833a0aa5557f66e49d5b1bfdcc7a55b86fdfa8c6ccc1e520820057",
                              "vout": 2,
                              "sequence": 4294967295,
                              "n": 0,
                              "scriptSig": {
                                    "hex": "48304502210099fe3b07bb4d14d7c7a627c710dfe29a8790ff44c09a6abbcab521608da3d0c00220677e1179ecb169f739ce5a215652b356c6a2ca5f2c6a3194580812521a49fdc6012102365eac74f0c8f0ca51937c812c254696d4635645e00ce09b5ad62619c5ae37cf",
                                    "asm": "304502210099fe3b07bb4d14d7c7a627c710dfe29a8790ff44c09a6abbcab521608da3d0c00220677e1179ecb169f739ce5a215652b356c6a2ca5f2c6a3194580812521a49fdc6[ALL] 02365eac74f0c8f0ca51937c812c254696d4635645e00ce09b5ad62619c5ae37cf"
                              },
                              "addr": "VMcBix9enCR17BZYWXa2G9PTuSY5UXiAGv",
                              "valueSat": 779499335500,
                              "value": 7794.993355,
                              "doubleSpentTxID": null
                        }
                  ],
                  "vout": [
                        {
                              "value": "217.00000000",
                              "n": 0,
                              "scriptPubKey": {
                                    "hex": "76a9140c97b859de459789c2df463ff28160d1508f555e88ac",
                                    "asm": "OP_DUP OP_HASH160 0c97b859de459789c2df463ff28160d1508f555e OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": null,
                              "spentIndex": null,
                              "spentHeight": null
                        },
                        {
                              "value": "7577.99234250",
                              "n": 1,
                              "scriptPubKey": {
                                    "hex": "76a91478164c6d742c4210d68c35e415e285f91d066e2a88ac",
                                    "asm": "OP_DUP OP_HASH160 78164c6d742c4210d68c35e415e285f91d066e2a OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VMcBix9enCR17BZYWXa2G9PTuSY5UXiAGv"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": "a11ab2ed050ee307f78fdb18f4c59d9e8446ec709542edd47ff71f7456ab2ba4",
                              "spentIndex": 0,
                              "spentHeight": 384960
                        }
                  ],
                  "blockhash": "00000000006b1fffe29da5212256a6aad43ac1f7725f68c1f6e469231047b24d",
                  "blockheight": 383487,
                  "confirmations": 46582,
                  "time": 1546433167,
                  "blocktime": 1546433167,
                  "valueOut": 7794.9923425,
                  "size": 226,
                  "valueIn": 7794.993355,
                  "fees": 0.0010125
            },
            ...
            {
                  "txid": "3e4ee042564fc45a265cab2b155251894a87bdd4f4e365fde8154fb9155e8439",
                  "version": 2,
                  "locktime": 365783,
                  "vin": [
                        {
                              "txid": "d383b477949c312510dd5819a7d439c4dc560bc6fcce3720ba390709dd776455",
                              "vout": 0,
                              "sequence": 4294967294,
                              "n": 0,
                              "scriptSig": {
                                    "hex": "473044022050e9157f70417d93fc411f0b87a014302d2e05c0abacf6bcc1b4fd4b051d6bee02201d9e9dd07c3582574f8c3fd61ecccd069a1af184833096129c9ec2079e883aa0012103f9c1c5eb9f2361aa76c340df325cc99d6aacc0ce032b7046b9591ecc684759d6",
                                    "asm": "3044022050e9157f70417d93fc411f0b87a014302d2e05c0abacf6bcc1b4fd4b051d6bee02201d9e9dd07c3582574f8c3fd61ecccd069a1af184833096129c9ec2079e883aa0[ALL] 03f9c1c5eb9f2361aa76c340df325cc99d6aacc0ce032b7046b9591ecc684759d6"
                              },
                              "addr": "VG8WDjEq71TxnZEsp3poJhHUMn8uPmKW2u",
                              "valueSat": 1481896742400,
                              "value": 14818.967424,
                              "doubleSpentTxID": null
                        }
                  ],
                  "vout": [
                        {
                              "value": "4545.00000000",
                              "n": 0,
                              "scriptPubKey": {
                                    "hex": "76a9140c97b859de459789c2df463ff28160d1508f555e88ac",
                                    "asm": "OP_DUP OP_HASH160 0c97b859de459789c2df463ff28160d1508f555e OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": null,
                              "spentIndex": null,
                              "spentHeight": null
                        },
                        {
                              "value": "10273.96652000",
                              "n": 1,
                              "scriptPubKey": {
                                    "hex": "76a91449ba421c7e92808599432f5ed3e88515f6949b3088ac",
                                    "asm": "OP_DUP OP_HASH160 49ba421c7e92808599432f5ed3e88515f6949b30 OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VHP4P4Ap8n2rGPqAbaVfNwMq1BsURfjRCX"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": "2adbb2d50447652c16f90a87eef9d0ec8b0f395fbd282171a33eed14099adddc",
                              "spentIndex": 0,
                              "spentHeight": 365786
                        }
                  ],
                  "blockhash": "dfbbbff4ddafa6f5c6645ae1270d034c5b1eedaed6455cff88c3376a16776be3",
                  "blockheight": 365785,
                  "confirmations": 64284,
                  "time": 1545348240,
                  "blocktime": 1545348240,
                  "valueOut": 14818.96652,
                  "size": 225,
                  "valueIn": 14818.967424,
                  "fees": 0.000904
            }
      ]
    }

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Invalid Argument: First argument is required, please include address data. Documentation: http://bitcore.io/guide/address.html. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Input string too short. Code:1

## トランザクション履歴取得 POSTリクエスト版 [POST /addrs/txs]

指定アドレスのトランザクション履歴を取得する。

+ Parameters
  + `addrs`: VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g (string, required) - VIPSTARCOINアドレス(カンマ区切りリスト)
  + `from`: 0 (int, optional) - 開始オフセット
  + `to`: 10 (int, optional) - 終了オフセット

+ Response 200 (application/json)
  + Body
    {
      "totalItems": 14,
      "from": 0,
      "to": 10,
      "items": [
            {
                  "txid": "40fa77f84fb2646420f93ede05fe400a3b6fdb14df05a00d107de2eb5c7c7d84",
                  "version": 2,
                  "locktime": 0,
                  "vin": [
                        {
                              "txid": "3ed5e732f1833a0aa5557f66e49d5b1bfdcc7a55b86fdfa8c6ccc1e520820057",
                              "vout": 2,
                              "sequence": 4294967295,
                              "n": 0,
                              "scriptSig": {
                                    "hex": "48304502210099fe3b07bb4d14d7c7a627c710dfe29a8790ff44c09a6abbcab521608da3d0c00220677e1179ecb169f739ce5a215652b356c6a2ca5f2c6a3194580812521a49fdc6012102365eac74f0c8f0ca51937c812c254696d4635645e00ce09b5ad62619c5ae37cf",
                                    "asm": "304502210099fe3b07bb4d14d7c7a627c710dfe29a8790ff44c09a6abbcab521608da3d0c00220677e1179ecb169f739ce5a215652b356c6a2ca5f2c6a3194580812521a49fdc6[ALL] 02365eac74f0c8f0ca51937c812c254696d4635645e00ce09b5ad62619c5ae37cf"
                              },
                              "addr": "VMcBix9enCR17BZYWXa2G9PTuSY5UXiAGv",
                              "valueSat": 779499335500,
                              "value": 7794.993355,
                              "doubleSpentTxID": null
                        }
                  ],
                  "vout": [
                        {
                              "value": "217.00000000",
                              "n": 0,
                              "scriptPubKey": {
                                    "hex": "76a9140c97b859de459789c2df463ff28160d1508f555e88ac",
                                    "asm": "OP_DUP OP_HASH160 0c97b859de459789c2df463ff28160d1508f555e OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": null,
                              "spentIndex": null,
                              "spentHeight": null
                        },
                        {
                              "value": "7577.99234250",
                              "n": 1,
                              "scriptPubKey": {
                                    "hex": "76a91478164c6d742c4210d68c35e415e285f91d066e2a88ac",
                                    "asm": "OP_DUP OP_HASH160 78164c6d742c4210d68c35e415e285f91d066e2a OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VMcBix9enCR17BZYWXa2G9PTuSY5UXiAGv"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": "a11ab2ed050ee307f78fdb18f4c59d9e8446ec709542edd47ff71f7456ab2ba4",
                              "spentIndex": 0,
                              "spentHeight": 384960
                        }
                  ],
                  "blockhash": "00000000006b1fffe29da5212256a6aad43ac1f7725f68c1f6e469231047b24d",
                  "blockheight": 383487,
                  "confirmations": 46582,
                  "time": 1546433167,
                  "blocktime": 1546433167,
                  "valueOut": 7794.9923425,
                  "size": 226,
                  "valueIn": 7794.993355,
                  "fees": 0.0010125
            },
            ...
            {
                  "txid": "3e4ee042564fc45a265cab2b155251894a87bdd4f4e365fde8154fb9155e8439",
                  "version": 2,
                  "locktime": 365783,
                  "vin": [
                        {
                              "txid": "d383b477949c312510dd5819a7d439c4dc560bc6fcce3720ba390709dd776455",
                              "vout": 0,
                              "sequence": 4294967294,
                              "n": 0,
                              "scriptSig": {
                                    "hex": "473044022050e9157f70417d93fc411f0b87a014302d2e05c0abacf6bcc1b4fd4b051d6bee02201d9e9dd07c3582574f8c3fd61ecccd069a1af184833096129c9ec2079e883aa0012103f9c1c5eb9f2361aa76c340df325cc99d6aacc0ce032b7046b9591ecc684759d6",
                                    "asm": "3044022050e9157f70417d93fc411f0b87a014302d2e05c0abacf6bcc1b4fd4b051d6bee02201d9e9dd07c3582574f8c3fd61ecccd069a1af184833096129c9ec2079e883aa0[ALL] 03f9c1c5eb9f2361aa76c340df325cc99d6aacc0ce032b7046b9591ecc684759d6"
                              },
                              "addr": "VG8WDjEq71TxnZEsp3poJhHUMn8uPmKW2u",
                              "valueSat": 1481896742400,
                              "value": 14818.967424,
                              "doubleSpentTxID": null
                        }
                  ],
                  "vout": [
                        {
                              "value": "4545.00000000",
                              "n": 0,
                              "scriptPubKey": {
                                    "hex": "76a9140c97b859de459789c2df463ff28160d1508f555e88ac",
                                    "asm": "OP_DUP OP_HASH160 0c97b859de459789c2df463ff28160d1508f555e OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": null,
                              "spentIndex": null,
                              "spentHeight": null
                        },
                        {
                              "value": "10273.96652000",
                              "n": 1,
                              "scriptPubKey": {
                                    "hex": "76a91449ba421c7e92808599432f5ed3e88515f6949b3088ac",
                                    "asm": "OP_DUP OP_HASH160 49ba421c7e92808599432f5ed3e88515f6949b30 OP_EQUALVERIFY OP_CHECKSIG",
                                    "addresses": [
                                          "VHP4P4Ap8n2rGPqAbaVfNwMq1BsURfjRCX"
                                    ],
                                    "type": "pubkeyhash"
                              },
                              "spentTxId": "2adbb2d50447652c16f90a87eef9d0ec8b0f395fbd282171a33eed14099adddc",
                              "spentIndex": 0,
                              "spentHeight": 365786
                        }
                  ],
                  "blockhash": "dfbbbff4ddafa6f5c6645ae1270d034c5b1eedaed6455cff88c3376a16776be3",
                  "blockheight": 365785,
                  "confirmations": 64284,
                  "time": 1545348240,
                  "blocktime": 1545348240,
                  "valueOut": 14818.96652,
                  "size": 225,
                  "valueIn": 14818.967424,
                  "fees": 0.000904
            }
      ]
    }

+ Response 400 (text/plain)
  + Body
    Invalid address: Checksum mismatch. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Non-base58 character. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Invalid Argument: First argument is required, please include address data. Documentation: http://bitcore.io/guide/address.html. Code:1

+ Response 400 (text/plain)
  + Body
    Invalid address: Input string too short. Code:1

# Group blocks

## 一覧取得 [GET /blocks]

VIPSTARCOINブロックチェーン上のブロックを一覧取得する。

+ Parameters
  + `blockDate`: 2019-01-01 (string, optional) - 取得対象日
  + `startTimestamp`: 1549198096 (number, optional) - 取得対象時間（指定以前のtimeのブロックのみ取得）
  + `limit`: 100 (number, optional) - 取得上限

+ Response 200 (application/json)
  + Body
    {
      "blocks": [
            {
                  "height": 428613,
                  "size": 620,
                  "hash": "9c6180cb590954c62a6d18e1927d5ccda50de980835a9ccbe38b6d24a77c7c45",
                  "time": 1549198096,
                  "txlength": 2,
                  "poolInfo": {},
                  "isMainChain": true,
                  "minedBy": "VQscHQUVDXpN7fNTbxVTYAsKGr5a8xSswQ"
            },
            {
                  "height": 428612,
                  "size": 621,
                  "hash": "d4d7de84927d729cd5a0b06f5c888c19b8502b16e279624a82401775414df5e5",
                  "time": 1549198064,
                  "txlength": 2,
                  "poolInfo": {},
                  "isMainChain": true,
                  "minedBy": "VVjp1SKo74GLjyNaDjEkUGHmcjqNgDJsPv"
            },
            ...
            {
                  "height": 428415,
                  "size": 366,
                  "hash": "00000000003b1709151a9e6521cb7cdf0149bec6629c8f8800a4013522ca632e",
                  "time": 1549185953,
                  "txlength": 1,
                  "poolInfo": {},
                  "isMainChain": true,
                  "minedBy": "VPn9k5AjugJNdzFP2W71C6AhT19oLnnCd7"
            },
            {
                  "height": 428414,
                  "size": 620,
                  "hash": "2c26183b1843e681a9ff026136004da26f8d5cfba2b2f53ca9078604ba026b31",
                  "time": 1549185872,
                  "txlength": 2,
                  "poolInfo": {},
                  "isMainChain": true,
                  "minedBy": "VWTeUyCZsePENeFSMz7ydfY9HNevKiCChD"
            }
      ],
      "length": 200,
      "pagination": {
            "next": "2019-02-04",
            "prev": "2019-02-02",
            "currentTs": 1549238399,
            "current": "2019-02-03",
            "isToday": true,
            "more": true,
            "moreTs": 1549185872
      }
    }

## 指定ブロック情報取得 [GET /block/{blockHash}]

ブロックハッシュを指定して指定ブロックの情報を取得する。

+ Parameters
  + `blockHash`: 0000d068e1d30f79fb64446137106be9c6ee69a6a722295c131506b1ee09b77c (string, required) - ブロックハッシュ

+ Response 200 (application/json)
  + Body
    {
      "hash": "0000d068e1d30f79fb64446137106be9c6ee69a6a722295c131506b1ee09b77c",
      "size": 344,
      "height": 0,
      "version": 1,
      "merkleroot": "3821b1e4634626248389576cae0c9310c365a46ace444a6e0bfb9e1f421bb625",
      "tx": [
            "3821b1e4634626248389576cae0c9310c365a46ace444a6e0bfb9e1f421bb625"
      ],
      "time": 1522223204,
      "nonce": 135269,
      "bits": "1f00ffff",
      "difficulty": 0.1525,
      "chainwork": "0000000000000000000000000000000000000000000000000000000000010001",
      "confirmations": 428581,
      "previousblockhash": null,
      "nextblockhash": "0000e0e7e28aef099b64e3fc81d8b9e7992e2adc56e2e573f8c025ce634db4e4",
      "reward": 1,
      "isMainChain": true,
      "poolInfo": {}
    }

+ Response 404 (text/plain)
  + Body
    Not Found

## 指定ブロック生データ取得 [GET /rawblock/{blockHash}]

ブロックハッシュを指定して指定ブロックの生データを取得する。

+ Parameters
  + `blockHash`: 0000d068e1d30f79fb64446137106be9c6ee69a6a722295c131506b1ee09b77c (string, required) - ブロックハッシュ

+ Response 200 (application/json)
  + Body
    {
      "rawblock": "01000000000000000000000000000000000000000000000000000000000000000000000025b61b421f9efb0b6e4a44ce6aa465c310930cae6c57898324264663e4b121386448bb5affff001f65100200e965ffd002cd6ad0e2dc402b8044de833e06b23127ea8c3d80aec9141077149556e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b4210000000000000000000000000000000000000000000000000000000000000000ffffffff000101000000010000000000000000000000000000000000000000000000000000000000000000ffffffff230004bf91221d01041a766970207175616c697479206f6e2074686520776f726c642121ffffffff0100e1f505000000004341766970207175616c697479206f6e2074686520776f726c642121766970207175616c697479206f6e2074686520776f726c642121766970207175616c697479206fac00000000"
    }

+ Response 404 (text/plain)
  + Body
    Not Found

## ブロック高指定 [GET /block-index/{height}]

ブロック高を指定してブロックハッシュを取得する。

+ Parameters
  + `height`: 0 (number, required) - ブロック高

+ Response 200 (application/json)
  + Body
    {
      "blockHash": "0000d068e1d30f79fb64446137106be9c6ee69a6a722295c131506b1ee09b77c"
    }

+ Response 400 (text/plain)
  + Body
    JSON value is not an integer as expected. Code:-1

+ Response 400 (text/plain)
  + Body
    Block height out of range. Code:-8

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

## コントラクト実行結果取得 [GET /txs/{txid}/receipt]

コントラクトの実行結果を取得する。

+ Parameters
  + `txid`: 1348ddd1861dc5acd7692072917dcf4ff2e5ebe79faf67f5d4a6bd3e491c3137 (string, required) - TXID

+ Response 200 (application/json)
  + Body
    [
      {
        "blockHash": "119168c29c8c2d4e81954ea863f1917c7636928f64967a82f621719c302b42ae",
        "blockNumber": 322237,
        "transactionHash": "1348ddd1861dc5acd7692072917dcf4ff2e5ebe79faf67f5d4a6bd3e491c3137",
        "transactionIndex": 2,
        "from": "a556166a2ec6bd6c027b350c06cb480d84b2317a",
        "to": "6f580ef5ef7f6677deb9345c0f1ae971effc05ef",
        "cumulativeGasUsed": 21931,
        "gasUsed": 21931,
        "contractAddress": "6f580ef5ef7f6677deb9345c0f1ae971effc05ef",
        "excepted": "None",
        "log": [
          {
            "address": "6f580ef5ef7f6677deb9345c0f1ae971effc05ef",
            "topics": [
              "ddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
              "000000000000000000000000a556166a2ec6bd6c027b350c06cb480d84b2317a",
              "000000000000000000000000c6acdb01adbef1aef4525cfa8e71dc0d662858e6"
            ],
            "data": "000000000000000000000000000000000000000000000000000000004994f9a0"
          }
        ]
      }
    ]

## トランザクション送信 [POST /tx/send]

署名済みトランザクションをVIPSTARCOINネットワークに送信する。

+ Parameters
  + `rawtx`: (string, required) - 署名済みトランザクションデータ

+ Response 200 (application/json)
  + Body
    {
      "txid": "9ca7a019a59240fbbffe73a458182a6d2877395e1f04ece02ed4ce2f416e7dbf"
    }

## 生トランザクション取得 [GET /rawtx/{txid}]

指定TXIDの生トランザクションデータを取得する。

+ Parameters
  + `txid`: 96e8bb7312b45b65171b7ea0c8999ca9f91ef947863e9b31089f38ea07f667a7 (string, required) - TXID

+ Response 200 (application/json)
  + Body
    {
      "rawtx": "02000000081f639f2f750cf9df8b3efa4318b2cf0da52aa0e15e6e5d30bf67f231b0800da3000000006b483045022100eeadd4e72225d1a3841e4ee11708e90166d123e270ef0215a5c8df7b2869fa3702200934bb47e7581f1b8428542a2b170cfec08170eddf56aca2b3b80c66f218d32e012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffff0e4fb8e66505832ee3f1ee7ab5ea9c9e302f30616e0c1d51457fe5f7e43bea64010000006b483045022100b75923272521a4cd431ba7678d0ff402f134f9f4d0f2c0ebeffd303d89c079610220371089176f28451fde52fdccf63711809515801889fa6b613a312b3cef6b762f012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffffa2be881db7495b01350baf43d3fde931d4e993a0557abc40a7443dd8200a37ad010000006a47304402202647efa573e6bb67d85c6d1ee57f0d3740e69ccfe6235061080653a51f24f923022070a079349782946b3809de6effb84a52870337d075e9191ec3e5195abf602b51012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffff5230e948e6e2dbe404f68874ec153fccbe7ee820e498659e956171a8fee991be000000006a47304402207e485a295ffb78778d634b3dc4916ceb98c3dbfadb4c24c465faaab8fb561cfe02207b651173d1a38a6eaedc783420751490b4842555986d18c824bc643433d16cab012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffffd592e2c3d04d3c2d2a07b1e21bf1a91e50c26050fb171157ce1217dee6c49f32000000006b483045022100a1a13329e77317208385f2047eda9659c0567a2d66ee9d2489978a533e111daa022022d4a22bb8ef860b937c953748884e289e11f74f783faf55d6ee436bd2c600ce012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffff6ff33b63a3659cf0d92cbc1dd8f3e39300b1b4b76871559c5bd61e07187dcec0010000006a47304402206a36035d5364db8d34a29d1e7b503dd5e00d0a254ee0b30fadfe2e97b201db3a0220651ecc91d9c41122097fa01985400cb51e8726ec93978abd8555a333e13b4637012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffffe48e01586befae88a8d9f7bf2dae664c267038d75269fa64c776343df2900fc5010000006b483045022100ca0ec9f74e12ca20e402f81f1b5ece6891c48a3a46bdf69948e09b9be378e29002202729e7fc48f22c347e96ba911ee1121dde2fd8d028057cb9c7275525bc56dfcf012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffff261093fb73e0dc8ec6bc1e5737609ebab7d24f7b191a2e2980260aec53d24c21010000006a47304402203b1edef3b65c8a18ecd26df9f25b25931c369030db8fa01e6502ede6508bb4e9022058e57d9ccdd56559b1e79e07c4ed30f6bf878a663e06deaf0d7e257302122769012103069114b4f300ed8836a5ff75054a4a3a2bc21e0b51ea4d1f41f7e61f51472dadfeffffff020000b2d3595bf0061976a9140c97b859de459789c2df463ff28160d1508f555e88ac204c7adfe40d47001976a91431486f453b5c9202d1259d368a947375223da4b788acdf0d0500"
    }


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
                  "\_id": "5c4c71e5cb90174a434eab55",
                  "tx_hash": "1e5ce58f5498cf6746b68856e5d8898a0a2afa057c17c5da7e1316be2fad38c5",
                  "vout_idx": 1,
                  "\_\_v": 0,
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
  + Body
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
                  "\_id": "5c4c71e5cb90174a434eab55",
                  "tx_hash": "1e5ce58f5498cf6746b68856e5d8898a0a2afa057c17c5da7e1316be2fad38c5",
                  "vout_idx": 1,
                  "\_\_v": 0,
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
  + Body
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
  + Body
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
  + Body
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
  + Body
    Not Found

# Group tokens

## トークン一覧取得 [GET /tokens]

全トークン一覧を取得する。

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
  + Body
    5000000000000000000000

+ Response 404 (text/plain)
  + Body
    Not Found

## トランザクション履歴取得 [GET /tokens/{contractBaseAddress}/transactions]

コントラクトベースアドレスを指定してトークンのトランザクション履歴を取得する。

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
  + Body
    10000000000000000000000

+ Response 200 (application/json)
  + Body
    {
      "total_supply": "10000000000000000000000"
    }

+ Response 404 (text/plain)
  + Body
    Not Found

# Group messages
## 署名検証 GETリクエスト版 [GET /messages/verify?{address,signature,message}]

署名文字列の検証を行う。

+ Parameters
  + `address`: VUmino3VbniKFyCzgYwpt8ZWfWumLGzSX4 (string, required) - 署名を行ったVIPSTARCOINアドレス
  + `signature`: HNQZQEKK/YpQ9GwFoBkVI++76liDOchb5i0H6PrpV9sYKgZ6hdP6HkiKuNsSjhu4hV6Z2Rs4AH7MUN9vfmAIswg= (string, required) - 署名シグネチャ
  + `message`: Hello, VIPSTARCOIN! (string, required) - 署名対象メッセージ

+ Response 200 (application/json)
  + Body
    {
      "result": true
    }

+ Response 400 (text/html)
  + Body
    Missing parameters (expected "address", "signature" and "message"). Code:1

+ Response 400 (text/html)
  + Body
    Unexpected error: Address has mismatched network type.. Code:1

## 署名検証 POSTリクエスト版 [POST /messages/verify]

署名文字列の検証を行う。

+ Parameters
  + `address`: VUmino3VbniKFyCzgYwpt8ZWfWumLGzSX4 (string, required) - 署名を行ったVIPSTARCOINアドレス
  + `signature`: HNQZQEKK/YpQ9GwFoBkVI++76liDOchb5i0H6PrpV9sYKgZ6hdP6HkiKuNsSjhu4hV6Z2Rs4AH7MUN9vfmAIswg= (string, required) - 署名シグネチャ
  + `message`: Hello, VIPSTARCOIN! (string, required) - 署名対象メッセージ

+ Response 200 (application/json)
  + Body
    {
      "result": true
    }

+ Response 400 (text/html)
  + Body
    Missing parameters (expected "address", "signature" and "message"). Code:1

+ Response 400 (text/html)
  + Body
    Unexpected error: Address has mismatched network type.. Code:1

# Group statistics
## 総供給枚数取得 [GET /supply]

VIPSTARCOINの総供給枚数(TotalSupply)を取得する。

+ Response 200 (application/json)
  + Body
    {
      "supply":61950116894
    }

## 総供給枚数取得 [GET /statistics/total-supply]

VIPSTARCOINの総供給枚数(TotalSupply)を取得する。（/supplyと同じ処理）

+ Response 200 (application/json)
  + Body
    {
      "supply":61950116894
    }

## 供給枚数取得 [GET /statistics/circulating-supply]

VIPSTARCOINの供給枚数(CirculatingsSupply)を取得する。（現状では正常動作しない）

+ Parameters
  + `format`: object (string, optional) - JSON形式で取得する場合指定

+ Response 200 (text/plain)
  + Body
    89688404

+ Response 200 (application/json)
  + Body
    {
      "circulatingSupply":"89688408"
    }

## 供給枚数分析 [GET /statistics/supply]

VIPSTARCOINの供給枚数を日別にカウントして取得する。（現状では正常動作しない）

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "sum": "101688416"
      },
      {
            "date": "2019-02-01",
            "sum": "101685788"
      },
      {
            "date": "2019-01-31",
            "sum": "101680144"
      },
      ...
      {
            "date": "2018-03-31",
            "sum": "99985096"
      },
      {
            "date": "2018-03-29",
            "sum": "99984072"
      }
    ]

## トランザクション手数料分析 [GET /statistics/fees]

VIPSTARCOINブロックチェーン上のトランザクション手数料を日別にカウントして取得する。

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "fee": 464317941507.42126
      },
      {
            "date": "2019-02-01",
            "fee": 464564183528.6038
      },
      {
            "date": "2019-01-31",
            "fee": 466191300825.99146
      },
      ...
      {
            "date": "2018-03-31",
            "fee": 390625
      },
      {
            "date": "2018-03-29",
            "fee": 28389394.89194499
      }
    ]

## トランザクション数分析 [GET /statistics/transactions]

VIPSTARCOINブロックチェーン上のトランザクション数とブロック生成数を日別にカウントして取得する。

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "transaction_count": 1133,
            "block_count": 671
      },
      {
            "date": "2019-02-01",
            "transaction_count": 2306,
            "block_count": 1411
      },
      {
            "date": "2019-01-31",
            "transaction_count": 2428,
            "block_count": 1402
      },
      ...
      {
            "date": "2018-03-31",
            "transaction_count": 257,
            "block_count": 256
      },
      {
            "date": "2018-03-29",
            "transaction_count": 1052,
            "block_count": 1018
      }
    ]

## トランザクション出力分析 [GET /statistics/outputs]

VIPSTARCOINブロックチェーン上のトランザクション出力数を日別にカウントして取得する。

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "sum": "2000903490630521"
      },
      {
            "date": "2019-02-01",
            "sum": "25951494563013299"
      },
      {
            "date": "2019-01-31",
            "sum": "21564938050008385"
      },
      ...
      {
            "date": "2018-03-31",
            "sum": 0
      },
      {
            "date": "2018-03-29",
            "sum": "5999999999999515200"
      }
    ]

## 採掘難易度分析 [GET /statistics/difficulty]

VIPSTARCOINブロックチェーン上の採掘難易度（difficulty）を日別にカウントして取得する。

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "sum": 5114256448.4982195
      },
      {
            "date": "2019-02-01",
            "sum": 5401415466.794309
      },
      {
            "date": "2019-01-31",
            "sum": 5616631498.414961
      },
      ...
      {
            "date": "2018-03-31",
            "sum": 1
      },
      {
            "date": "2018-03-29",
            "sum": 1
      }
    ]

## ステーク分析 [GET /statistics/stake]

VIPSTARCOINブロックチェーン上のステーク（POS）分析を行う。

+ Parameters
  + `days`: 14 (number, optional) - 取得対象期間

+ Response 200 (application/json)
  + Body
    [
      {
            "date": "2019-02-02",
            "sum": 0.0017837406054202751
      },
      {
            "date": "2019-02-01",
            "sum": 0.003418836160388861
      },
      {
            "date": "2019-01-31",
            "sum": 0.003408926490358748
      },
      ...
      {
            "date": "2018-03-31",
            "sum": 5.2156158053e-10
      },
      {
            "date": "2018-03-29",
            "sum": 1.46037242549e-8
      }
    ]

## 統計情報取得 [GET /statistics/total]

直近24時間の統計情報を取得する。

+ Response 200 (application/json)
  + Body
    {
      "n_blocks_mined": 1411,
      "time_between_blocks": 61.16241134751773,
      "mined_currency_amount": 652650000000000,
      "transaction_fees": 652650096655930,
      "number_of_transactions": 2332,
      "outputs_volume": 7503681048132527,
      "difficulty": 5229219358.241021,
      "stake": 0.0034038704616443914
    }

## 残高分布取得 [GET /statistics/balance-intervals]

VIPSTARCOIN残高の分布を取得する。

+ Response 200 (application/json)
  + Body
    [
      {
            "max": 0.001,
            "min": 0,
            "count": 2,
            "sum": 0.002
      },
      {
            "max": 0.01,
            "min": 0.001,
            "count": 220,
            "sum": 1.28513606
      },
      {
            "max": 0.1,
            "min": 0.01,
            "count": 678,
            "sum": 40.11070923
      },
      {
            "max": 1,
            "min": 0.1,
            "count": 1151,
            "sum": 675.22379719
      },
      {
            "max": 10,
            "min": 1,
            "count": 1466,
            "sum": 6473.46071993
      },
      {
            "max": 100,
            "min": 10,
            "count": 1213,
            "sum": 73025.40814118
      },
      {
            "max": 1000,
            "min": 100,
            "count": 1854,
            "sum": 764792.89309746
      },
      {
            "max": 10000,
            "min": 1000,
            "count": 1271,
            "sum": 5266601.61765487
      },
      {
            "max": 100000,
            "min": 10000,
            "count": 927,
            "sum": 42717368.72275975
      },
      {
            "max": 1000000,
            "min": 100000,
            "count": 789,
            "sum": 288681335.63153094
      },
      {
            "max": 10000000,
            "min": 1000000,
            "count": 512,
            "sum": 1606668379.7476463
      },
      {
            "max": 100000000,
            "min": 10000000,
            "count": 207,
            "sum": 5918342215.27928
      },
      {
            "max": 1000000000,
            "min": 100000000,
            "count": 26,
            "sum": 7584284352.087332
      },
      {
            "max": 10000000000,
            "min": 1000000000,
            "count": 15,
            "sum": 36513493397.53818
      },
      {
            "max": 100000000000,
            "min": 10000000000,
            "count": 1,
            "sum": 10000024024.4825
      }
    ]

## USD建残高分布取得 [GET /statistics/richer-than]

USD建でVIPSTARCOIN残高の分布を取得する。

+ Response 200 (application/json)
  + Body
    [
      {
            "amount_usd": 1,
            "count_addresses": 2291
      },
      {
            "amount_usd": 100,
            "count_addresses": 600
      },
      {
            "amount_usd": 1000,
            "count_addresses": 170
      },
      {
            "amount_usd": 10000,
            "count_addresses": 34
      },
      {
            "amount_usd": 100000,
            "count_addresses": 5
      },
      {
            "amount_usd": 1000000,
            "count_addresses": 0
      },
      {
            "amount_usd": 10000000,
            "count_addresses": 0
      }
    ]

## リッチリスト取得 [GET /statistics/richest-addresses-list]

VIPSTARCOINのリッチリストを取得する。

+ Response 200 (application/json)
  + Body
    [
      {
            "address": "VBoonburnwwwwwwwwwwwwwwwwwwwsL3j5g",
            "blocks_mined": 0,
            "balance": 10000024024.4825
      },
      ...
    ]

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
