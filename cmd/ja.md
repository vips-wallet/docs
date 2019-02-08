FORMAT: 1A
HOST: http://127.0.0.1:31916
# VIPSTARCOIN cmd_list
VIPSTARCOIN コマンドリスト
# Group Blockchain
## コールコントラクト [GET callcontract "address" "data" "address" "gasLimit"]
コントラクトを呼び出す
+ Parameters
  + `address`: 813cd81362ce245df1c50aac7e7769c852d60968 (string, required) - コントラクトアドレス
  + `data`: 06fdde03 (string, required) - 関数名ハッシュ、[const.js](https://github.com/vips-wallet/vipstarcoinjs-wallet-core/blob/master/src/const.js#L70)参照
  + `address`: 0c97b859de459789c2df463ff28160d1508f555e (string, optional) - gethexaddressでVアドレスを16進数化したもの
  + `gasLimit`: ??? (string, optional) - ガスの制限
+ Response 200 (application/json)
      + Body
      {
        "address": "(コントラクトアドレス)",
        "executionResult": {
          "gasUsed": (数字),
          "excepted": "None", ←（詳細不明）
          "newAddress": "（コントラクトアドレス）",
          "output": "（16進数の文字列）", ←（結果が返ってくる、ethabiというソフトで解析可能？）
          "codeDeposit": (数字),
          "gasRefunded": （数字）,
          "depositSize": （数字）,
          "gasForDeposit": （数字）
        },
        "transactionReceipt": {
          "stateRoot": "（詳細不明、16進数の文字列）",
          "gasUsed": (数字),
          "bloom": "(数字、検証時は0の羅列)",
          "log": [
          ]
        }
      }
      
#### 結果の詳細
```
{
  "address": "(コントラクトアドレス)",
  "executionResult": {
    "gasUsed": (数字),
    "excepted": "None", ←（詳細不明）
    "newAddress": "（コントラクトアドレス）",
    "output": "（16進数の文字列）", ←（結果が返ってくる、ethabiというソフトで解析可能？）
    "codeDeposit": (数字),
    "gasRefunded": （数字）,
    "depositSize": （数字）,
    "gasForDeposit": （数字）
  },
  "transactionReceipt": {
    "stateRoot": "（詳細不明、16進数の文字列）",
    "gasUsed": (数字),
    "bloom": "(数字、検証時は0の羅列)",
    "log": [
    ]
  }
}
```
---
### getaccountinfo "address"
指定したコントラクトアドレスの詳細を返す
#### 引数
`"address"`（必須） コントラクトアドレス
#### 結果の詳細
```
{
  "address": "（コントラクトアドレス）",
  "balance": 0,
  "storage": {
    "（16進数の文字列）": {
      "（16進数の文字列）": "（16進数の文字列）"
    },
...(こんな感じなのが続く　中身はトークンだったら基本情報、残高情報など)
    "（16進数の文字列）": {
      "（16進数の文字列）": "（16進数の文字列）"
    }
  },
  "code": "(bytecodeの中身)"
}
```
---
### getbestblockhash
最新のブロックハッシュを返す
#### 引数
（無し）
#### 結果の詳細
```
（最新のブロックハッシュ）
```
---
### getblock "blockhash" "verbose"
指定ブロックの情報を返す
#### 引数
`"blockhash"`（必須） 情報を取得したいブロックのハッシュ  
`"verbose"` （任意、true / false） 初期値:true falseを指定すると16進数の文字列を返す
#### 結果の詳細（verbose=true）
```
{
  "hash": "(当該ブロックのハッシュ)",
  "confirmations": （認証数）,
  "strippedsize": （witness dataを除いたブロックサイズ、数字）,
  "size": （ブロックサイズ、数字）,
  "weight": （BIP 141で定義されているブロックのweight、数字）,
  "height": （ブロック高、数字）,
  "version": （ブロックバージョン、数字）,
  "versionHex": （ブロックバージョン、16進数の文字列）,
  "merkleroot": （merkle root、詳細不明、16進数の文字列）,
  "hashStateRoot": （詳細不明、16進数の文字列）,
  "hashUTXORoot": （詳細不明、16進数の文字列）,
  "tx": [
    （txid、16進数の文字列）
  ],
  "time": （1970/01/01(GMT)からの経過時間（秒）、数字）,
  "mediantime": （1970/01/01(GMT)からの経過時間（秒）の中央値、数字）,
  "nonce": （ナンス、数字）,
  "bits": （bits、16進数の文字列）,
  "difficulty": （採掘難易度、数字）,
  "chainwork": （必要なハッシュの予想数、16進数の文字列）,
  "previousblockhash": （前のブロックのハッシュ、16進数の文字列）,
  "nextblockhash": （次のブロックのハッシュ（最新ブロックの場合はありません）、16進数の文字列）,
  "flags": （proof-of-work / proof-of-stake）,
  "proofhash": （詳細不明、16進数の文字列）,
  "modifier": （詳細不明、16進数の文字列）,
  "signature": （詳細不明（PoWで生成された場合はありません）、16進数の文字列）
}
```
---
### getblockchaininfo
ブロックチェーンの情報を返す
#### 引数
（無し）
#### 結果の詳細
```
{
  "chain": （BIP70で定義されている現在のネットワーク名 main、test、regtestのいずれか）,
  "blocks": （処理済のブロック数、数字）,
  "headers": （検証済のヘッダー数、数字）,
  "bestblockhash": （最新ブロックのハッシュ）,
  "difficulty": （現在の採掘難易度）,
  "mediantime": （1970/01/01(GMT)からの経過時間（秒）の中央値、数字）,
  "verificationprogress": （同期状況の推定数値、0から1の数字）,
  "chainwork": （必要なハッシュの予想数、16進数の文字列）,
  "pruned": （剪定しているかどうか、TrueかFalse）,
  "softforks": [
    {
      "id": "bip34",
      "version": 2,
      "reject": {
        "status": true
      }
    },
    {
      "id": "bip66",
      "version": 3,
      "reject": {
        "status": true
      }
    },
    {
      "id": "bip65",
      "version": 4,
      "reject": {
        "status": true
      }
    }
  ],
  "bip9_softforks": {
    "csv": {
      "status": "active",
      "startTime": 0,
      "timeout": 999999999999,
      "since": 60480
    },
    "segwit": {
      "status": "active",
      "startTime": 0,
      "timeout": 999999999999,
      "since": 60480
    }
  }
}
```
（補足）softforksについてはよく分からなかったので`help getblockchaininfo`でご確認ください

---
### getblockcount
現在のブロック高を返す
#### 引数
（無し）
#### 結果の詳細
```
（現在のブロック高）
```
---
### getblockhash "height"
指定ブロックのハッシュを返す
#### 引数
`"height"`（必須） 情報を取得したいブロックの高さ
#### 結果の詳細
```
（指定のブロックハッシュ）
```
---
### getblockheader "hash" "verbose"
指定ブロックのヘッダー情報を返す
#### 引数
`"hash"`（必須） 情報を取得したいブロックのハッシュ  
`"verbose"` （任意、true / false） 初期値:true falseを指定すると16進数の文字列を返す
#### 結果の詳細（verbose=true）
```
{
  "hash": （指定のブロックのハッシュ）,
  "confirmations": （承認数、数字）,
  "height": （ブロック高、数字）,
  "version": （ブロックのバージョン、数字）,
  "versionHex": （ブロックのバージョン、16進数の文字列）,
  "merkleroot": （merkle root、詳細不明、16進数の文字列）,
  "time": （1970/01/01(GMT)からの経過時間（秒）、数字）,
  "mediantime": （1970/01/01(GMT)からの経過時間（秒）の中央値、数字）,
  "nonce": （ナンス、数字）,
  "bits": （bits、16進数の文字列）,
  "difficulty": （採掘難易度、数字）,
  "chainwork": （必要なハッシュの予想数、16進数の文字列）,
  "hashStateRoot": （詳細不明、16進数の文字列）,
  "hashUTXORoot": （詳細不明、16進数の文字列）,
  "previousblockhash": （前のブロックのハッシュ、16進数の文字列）,
  "nextblockhash": "（次のブロックのハッシュ（最新ブロックの場合はありません）、16進数の文字列）",
  "flags": （proof-of-work / proof-of-stake）,
  "proofhash": （詳細不明、16進数の文字列）,
  "modifier": （詳細不明、16進数の文字列）
}
```
---
### getchaintips
全てのブロックツリー先端ブロックの情報を返す（メインチェーン、孤立したブランチの両方）
#### 引数
（無し）
#### 結果の詳細
```
[
  {
    "height": （最新ブロック数）,
    "hash": （最新ブロックのハッシュ）,
    "branchlen": 0,
    "status": "active"
  },
  {
    "height": （ブロック数）,
    "hash": （そのブロックのハッシュ）,
    "branchlen": （数字）,
    "status": （invalid、headers-only、valid-headers、valid-forkのいずれか）
  },
  (中略)
  {
    "height": （ブロック数）,
    "hash": （そのブロックのハッシュ）,
    "branchlen": （数字）,
    "status": （invalid、headers-only、valid-headers、valid-forkのいずれか）
  }
]
```
（補足）  
branchlenはそのブランチの長さ（メインチェーンは0）  
statusの詳細：active…有効なメインチェーン invalid…無効なブロックが含まれている  
headers-only…ヘッダーのみ有効 valid-headers…検証が不完全 valid-fork…検証済だがメインチェーンに含まれていない  

---
### getcheckpoint
チェックポイントについての情報を返す
#### 引数
（無し）
#### 結果の詳細
```
[
  {
    "synccheckpoint": "0000d068e1d30f79fb64446137106be9c6ee69a6a722295c131506b1ee09b77c",
    "height": 0,
    "timestamp": 1522223204
  }
]
```
---
### getdifficulty
採掘難易度を返す
#### 引数
（無し）
#### 結果の詳細
```
{
  "proof-of-work": （採掘難易度、数字）,
  "proof-of-stake": （採掘難易度、数字）
}
```
---
### getmempoolancestors "txid" "verbose"
mempool内のすべての先祖？(原文：ancestors)を取得
#### 引数
`"txid"`（必須） mempool内のtxidのみ指定可能  
`"verbose"` （任意、true / false） 初期値:true falseを指定すると16進数の文字列を返す
#### 結果の詳細
（不明）

---
### getmempooldescendants "txid" "verbose"
mempool内のすべての子孫？(原文：descendants)を取得
#### 引数
`"txid"`（必須） mempool内のtxidのみ指定可能  
`"verbose"` （任意、true / false） 初期値:true falseを指定すると16進数の文字列を返す
#### 結果の詳細
（不明）

---
### getmempoolentry "txid"
mempool内にあるトランザクションの情報を返す
#### 引数
`"txid"`（必須） mempool内のtxidのみ指定可能
#### 結果の詳細
```
{
  "size": （BIP141で定義されている仮想トランザクションサイズ、数字）,
  "fee": （取引手数料、数字）,
  "modifiedfee": （早くブロックに取り込まれるように追加した手数料を含む取引手数料、数字）,
  "time": （1970/01/01(GMT)からの経過時間（秒）、数字）,
  "height": （トランザクションがプールに入った時のブロック高）,
  "startingpriority": （【非推奨】トランザクションがプールに入った時の優先順位、数字）,
  "currentpriority": （【非推奨】現在の優先順位、数字）,
  "descendantcount": （mempool内のこのトランザクションを含む子孫のトランザクション数、数字）,
  "descendantsize": （mempool内のこのトランザクションを含む子孫の仮想トランザクションサイズ、数字）,
  "descendantfees": （mempool内のこのトランザクションを含む子孫のトランザクションの修正手数料、数字）,
  "ancestorcount": （mempool内のこのトランザクションを含む先祖のトランザクション数、数字）,
  "ancestorsize": （mempool内のこのトランザクションを含む先祖のトランザクションサイズ、数字）,
  "ancestorfees": （mempool内のこのトランザクションを含む先祖のトランザクションの修正手数料、数字）,
  "depends": [
    （このトランザクションの入力として使用される未確認のtxid）,
  ]
}
```
---
### getmempoolinfo
mempoolの情報を返す
#### 引数
（無し）
#### 結果の詳細
```
{
  "size": （現在のmempool内のトランザクション数、数字）,
  "bytes": （BIP141で定義されている仮想トランザクションサイズの合計、数字）,
  "usage": （mempoolのメモリ使用量、数字）,
  "maxmempool": （mempoolの最大メモリ使用量、数字）,
  "mempoolminfee": （トランザクションが受け入れられるための最低の手数料、数字）
}
```
---
### getrawmempool "verbose"
mempool内のすべてのトランザクションの情報を返す
#### 引数
`"verbose"`（任意、true / false） 初期値:true falseを指定するとtxidのみを返す
#### 結果の詳細（verbose=true）
```
{
  （mempool内の1つ目のtxid）: {
    "size": （BIP141で定義されている仮想トランザクションサイズ、数字）,
    "fee": （取引手数料、数字）,
    "modifiedfee": （早くブロックに取り込まれるように追加した手数料を含む取引手数料、数字）,
    "time": （1970/01/01(GMT)からの経過時間（秒）、数字）,
    "height": （トランザクションがプールに入った時のブロック高）,
    "startingpriority": （【非推奨】トランザクションがプールに入った時の優先順位、数字）,
    "currentpriority": （【非推奨】現在の優先順位、数字）,
    "descendantcount": （mempool内のこのトランザクションを含む子孫のトランザクション数、数字）,
    "descendantsize": （mempool内のこのトランザクションを含む子孫の仮想トランザクションサイズ、数字）,
    "descendantfees": （mempool内のこのトランザクションを含む子孫のトランザクションの修正手数料、数字）,
    "ancestorcount": （mempool内のこのトランザクションを含む先祖のトランザクション数、数字）,
    "ancestorsize": （mempool内のこのトランザクションを含む先祖のトランザクションサイズ、数字）,
    "ancestorfees": （mempool内のこのトランザクションを含む先祖のトランザクションの修正手数料、数字）,
    "depends": [
      （このトランザクションの入力として使用される未確認のtxid）,
    ]
  },
  （2つ目のtxidが続く）
}
```
#### 結果の詳細（verbose=false）
```
[
  (mempool内の1つ目のtxid),
  (2つ目のtxid…と続く)
]
```
---
### getstorage "address"
指定したコントラクトアドレスのストレージを返す
#### 引数
`"address"`（必須） コントラクトアドレス
#### 結果の詳細
```
{
  "（16進数の文字列）": {
    "（16進数の文字列）": "（16進数の文字列）"
  },
(中略　こんな感じなのが続く　中身はトークンだったら基本情報、残高情報など)
  "（16進数の文字列）": {
    "（16進数の文字列）": "（16進数の文字列）"
    }
}
```
---
### gettransactionreceipt "hash"
スマコン関係のコマンド？（詳細不明）  
-logeventsオプションを付けてウォレットを起動する必要あり（再インデックスが必要）
#### 引数
`"hash"` ブロックハッシュ
#### 結果の詳細
```
[
  {
    "blockHash": （ブロックのハッシュ）,
    "blockNumber": （そのブロック数）,
    "transactionHash": （txid）,
    "transactionIndex": （詳細不明、数字）,
    "from": （送り主の16進数化したアドレス）,
    "to": （スマートコントラクトアドレス？0の場合もあり）,
    "cumulativeGasUsed": （累積のガスの量？）,
    "gasUsed": （支払われたガスの量）,
    "contractAddress": （コントラクトアドレス）,
    "excepted": （詳細不明、テスト時は"None"）,
    "log": [
      {
        "address": （スマートコントラクトアドレス）,
        "topics": [
          （16進数の文字列）,
          （16進数の文字列）,
          （16進数の文字列）
        ],
        "data": （16進数の文字列）
      }
    ]
  }
]
```
---
### gettxout "txid" n "include_mempool"
（未使用の？）トランザクションの詳細を返す
#### 引数
`"txid"`（必須） トランザクションID  
`n`（必須） VOUT番号  
`"include_mempool"` （任意、true / false） 初期値：true mempool内のトランザクションを含めるかどうか
#### 結果の詳細
```
{
  "bestblock": （取得時の最新ブロックのハッシュ）,
  "confirmations": （認証数）,
  "value": （取引量、数字）,
  "scriptPubKey": {
    "asm": （コード、詳細不明、文字列）,
    "hex": （詳細不明、16進数の文字列）,
    "reqSigs": （必要な署名の数？詳細不明、数字）,
    "type": （例えばpubkeyhashらしい、nonstandardも確認）,
    "addresses": [
      （受け取りアドレス）
    ]
  },
  "coinbase": （coinbaseかどうか、true/false）,
  "coinstake": （PoSかどうか、true/false）
}
```
（補足）VOUT番号について  
アドレスA(100VIPS)→アドレスB(20VIPS)、アドレスC(10VIPS)、アドレスD(おつり、70VIPS)  
上の取引の例ではBの番号が0、Cの番号が1、Dの番号が2となる

---
### gettxoutproof ["txid",...] "blockhash"
txidがブロックに含まれていることを（16進数エンコードで）証明したものを返す  
たまに動作しないときがある（詳細不明、`help gettxoutproof`のNOTE参照）  
txindexするかblockhashを指定することで常に動作する
#### 引数
`["txid",...]`（必須） トランザクションID、`"[\"トランザクションID\"]"`のように指定する必要あり（複数指定の方法は不明）  
`"blockhash"`（任意） 指定した場合そのブロックにトランザクションが含まれているか調べる
#### 結果の詳細
```
（16進数の文字列）
```
---
### gettxoutsetinfo
UTXOに関する情報を返す
#### 引数
（無し）
#### 結果の詳細
```
{
  "height": （現在のブロック高、数字）,
  "bestblock": （最新ブロックのハッシュ）,
  "transactions": （トランザクション数（今までの？））,
  "txouts": （出力トランザクション数（今までの？））,
  "hash_serialized_2": （シリアル化されたハッシュ、詳細不明、16進数の文字列）,
  "disk_size": （ディスク上のchainstateの推定サイズ）,
  "total_amount": （合計金額（現在のCoin Supply？））
}
```
---
### listcontracts "start" "maxDisplay"
今までに作られたスマートコントラクトの一覧を返す
#### 引数
`"start"`（任意） 初期値：1 何個目のスマートコントラクトから表示するか  
`"maxDisplay"`（任意） 初期値：20 この数を超えたら表示をストップする
#### 結果の詳細
```
{
  （スマートコントラクトアドレス）: （詳細不明、数字）,
  （スマートコントラクトアドレス）: （詳細不明、数字）,
  （中略）
  （スマートコントラクトアドレス）: （詳細不明、数字）
}
```
---
### makekeypair
新しい公開鍵と秘密鍵のペアを作成
#### 引数
（無し）
#### 結果の詳細
```
[
  {
    "PublicKey": （生成された公開鍵）,
    "PrivateKey": （生成された秘密鍵）
  }
]
```
---
### preciousblock "blockhash"
指定したブロックを競合するブロックよりも早く受信したものとして扱う（複数回実行すると前の効果を上書きする）  
再起動でリセットされる
#### 引数
`"blockhash"`（必須） 競合するブロックよりも早く受信したものとして扱うブロックのハッシュ
#### 結果の詳細
（不明）

---
### pruneblockchain "height"
手動で剪定を行う（剪定機能をオンにしておく必要あり）
#### 引数
`"height"`（必須） 剪定するブロックの高さ（タイムスタンプも指定可能？）
#### 結果の詳細
```
（剪定したブロック数）
```
---
### searchlogs "fromBlock" "toBlock" "address" "topics"
ログを検索する  
-logeventsオプションを付けてウォレットを起動する必要あり（再インデックスが必要）  
`searchlogs 1 -1`を実行すると、100万行以上のログが出力されるので要注意
#### 引数
`"fronblock"`（必須） 検索開始位置のブロック高  
`"toBlock"`（必須） 検索終了位置のブロック高 最新ブロックなら`-1`  
`"address"`（任意） 検索するアドレスを指定 （おそらくスマートコントラクトアドレスのみ）  
`"topics"`（任意） topics内にその文字列が入っていたもののみ表示（部分指定は不可）
#### 結果の詳細
```
[
  {
    "blockHash": （ブロックハッシュ）,
    "blockNumber": （ブロック高）,
    "transactionHash": （txid）,
    "transactionIndex": （詳細不明、数字）,
    "from": （送り主の16進数化したアドレス）,
    "to": （スマートコントラクトアドレス？0の場合もあり）,
    "cumulativeGasUsed": （累積のガスの量？）,
    "gasUsed": （使われたガスの量）,
    "contractAddress": （スマートコントラクトアドレス）,
    "excepted": （詳細不明、テスト時は"None"）,
    "log": [
      {
        "address": （スマートコントラクトアドレス）,
        "topics": [
          （16進数の文字列）,
          （16進数の文字列）,
          （16進数の文字列）
        ],
        "data": （16進数の文字列）
      }
    ]
  },
  （以下略）
]
```
---
### sendcheckpoint "blockhash"
Send a synchronized checkpoint.（詳細不明）
#### 引数
`"blockhash"`（多分必須） ブロックハッシュ
#### 結果の詳細
（不明）

---
### verifychain "checklevel" "nblocks"
ブロックチェーンのデータベースを検証する  
#### 引数
`"checklevel"`（任意） どの程度検証するか  
```
0…Read from disk to ensure the files are accessible
1…Ensure each block is valid
2…Make sure undo files can be read from disk and are in a valid format
3…Test each block undo to ensure it results in correct state
4…After undoing blocks, reconnect them to ensure they reconnect correctly
```
`"nblocks"`（任意） 初期値：6 チェックするブロック数（0なら全ブロック検証）
#### 結果の詳細
```
（true/false 有効かどうか）
```
---
### verifytxoutproof "proof"
`gettxoutproof`の結果を検証する？（詳細不明）
#### 引数
`"proof"`（必須） `gettxoutproof`の結果
#### 結果の詳細
```
[
  （txid）
]
```
---
### waitforlogs "fromBlock" "toBlock" "filter" "minconf"
新しいログを待ち、条件に一致するログを取得（トークンの取引のみ？）  
logeventsを有効にする必要あり
#### 引数
`"fromblock"`（任意） ログの検索を始めるブロック高？  
`"toblock"`（任意）ログの検索を中止するブロック高？  
`"filter"`（任意） 条件を付ける `{ addresses?: Hex160String[], topics?: Hex256String[] }` （helpの記述例、動くかは不明）  
`"minconf"`（任意） 初期値：6 最小検証数
#### 結果の詳細
```
{
  "entries": [
    {
      "blockHash": （ブロックハッシュ）,
      "blockNumber": （ブロック高）,
      "transactionHash": （txid）,
      "transactionIndex": （詳細不明、数字）,
      "from": （送り主の16進数化アドレス）,
      "to": "（コントラクトアドレス？0の場合もあり）",
      "cumulativeGasUsed": （累積のガスの量？）,
      "gasUsed": （使われたガスの量）,
      "contractAddress": （コントラクトアドレス）,
      "excepted": （詳細不明、テスト時は"None"）,
      "topics": [
        （16進数の文字列）,
        （16進数の文字列）,
        （16進数の文字列）
      ],
      "data": （16進数の文字列）
    },
    （同じブロックに複数取引があった場合続く）
  ],
  "count": （取引数）,
  "nextblock": （次のブロック高）
}
```
## Control
### getinfo
様々な情報を返す  
#### 引数
（無し）
#### 結果の詳細
```
{
  "version": （サーバーバージョン数字）,
  "protocolversion": （プロトコルバージョン、数字）,
  "walletversion": （ウォレットバージョン、数字）,
  "balance": （トータルの残高）,
  "stake": （stakeしている数量）,
  "blocks": （現在のブロック高）,
  "timeoffset": （タイムオフセット）,
  "connections": （接続数）,
  "proxy": （ホスト:ポート、proxy通してない場合は無し）,
  "difficulty": {
    "proof-of-work": （PoWの採掘難易度）,
    "proof-of-stake": （PoSの採掘難易度）
  },
  "testnet": （testnetかどうか、true/false）,
  "moneysupply": （VIPSの総額）,
  "keypoololdest": 最も古いキーのタイムスタンプ,
  "keypoolsize": （pre-generatedされているキーの数）,
  "unlocked_until": （送金のためにロック解除した時のタイムスタンプ、ロックしているときは0）,
  "paytxfee": （1kbあたりに設定されている手数料）,
  "relayfee": （1kbあたりの中継手数料）,
  "errors": （エラーメッセージ）
}
```
---
### getmemoryinfo
メモリ使用量についての情報を返す  
#### 引数
（無し）
#### 結果の詳細
```
{
  "locked": {
    "used": （使用バイト数）,
    "free": （利用可能なバイト数）,
    "total": （トータルのバイト数）,
    "locked": （ロックに成功したバイト数）,
    "chunks_used": （割り当てられたチャンク数）,
    "chunks_free": （未使用のチャンク数）
  }
}
```
---
### help "command"
コマンドの詳細を返す  
#### 引数
`"command"`（任意） 指定した場合はそのコマンドについての詳細、していない場合はコマンド一覧を返す  
#### 結果の詳細（引数なし）
```
== Blockchain ==
callcontract "address" "data" ( address )
getaccountinfo "address"
（中略）
walletpassphrase "passphrase" timeout
walletpassphrasechange "oldpassphrase" "newpassphrase"
```
---
### stop
VIPSTARCOIN-Coreをストップする  
#### 引数
（無し）
#### 結果の詳細
```
VIPSTARCOIN server stopping
```
