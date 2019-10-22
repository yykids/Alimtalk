## Notification > KakaoTalk Bizmessage > お知らせトーク > API v1.0 Guide

## お知らせトーク

#### [APIドメイン]

<table>
<thead>
<tr>
<th>ドメイン</th>
</tr>
</thead>
<tbody>
<tr>
<td>https://api-alimtalk.cloud.toast.com</td>
</tr>
</tbody>
</table>

## メッセージの送信

#### 置換送信リクエスト

[URL]

```
POST  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| 値 | タイプ | 説明 |
| ------ | ------ | ------ |
| appkey | String | 固有のアプリケーションキー |

[Header]
```
{
  "X-Secret-Key": String
}
```
| 値       | タイプ | 必須 | 説明                                  |
| ------------ | ------ | ---- | ---------------------------------------- |
| X-Secret-Key | String | O    | コンソールで作成できる。[[参考](./plus-friend-console-guide/#x-secret-key)] |

[Request body]

```
{
    "plusFriendId": String,
    "templateCode": String,
    "recipientList": [{
        "recipientNo": String,
        "templateParameter": {
            String: String
        }
    }]
}
```

| 値              | タイプ | 必須 | 説明                            |
| ------------------- | ------ | ---- | ---------------------------------- |
| plusFriendId        | String | X    | プラスフレンドID                           |
| templateCode        | String | O    | 登録した送信テンプレートコード                 |
| recipientList       | List   | O    | 受信者リスト(最大1000人)                   |
| - recipientNo       | String | O    | 受信番号                         |
| - templateParameter | Object | X    | テンプレートパラメータ<br>(テンプレートに置換する変数が含まれる時は必須) |
| -- key              | String | X    | 置換キー(#{key})                       |
| -- value            | String | X    | 置換キーにマッピングされるValue値             |

* <b>プラスフレンドIDフィールドを送信しない場合、最初に登録したプラスフレンドに送信されます。</b>

[例]
```
curl -X POST -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/messages -d '{"plusFriendId": "{プラスフレンドID}","templateCode": "{テンプレートコード}","recipientList":[{"recipientNo": "{受信番号}","templateParameter": { "{日本語識別子フィールド}": "{置換データ}" }}]}'
```

#### 全文送信リクエスト

[URL]

```
POST  /alimtalk/v1.0/appkeys/{appkey}/raw-messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| 値 | タイプ | 説明 |
| ------ | ------ | ------ |
| appkey | String | 固有のアプリケーションキー |

[Header]
```
{
  "X-Secret-Key": String
}
```
| 値       | タイプ | 必須 | 説明                                  |
| ------------ | ------ | ---- | ---------------------------------------- |
| X-Secret-Key | String | O    | コンソールで作成できる。[[参考](./plus-friend-console-guide/#x-secret-key)] |

[Request body]

```
{
    "plusFriendId": String,
    "templateCode": String,
    "recipientList": [
        {
            "recipientNo": String,
            "content": String,
            "buttons": [
                {
                    "ordering": Integer,
                    "type": String,
                    "name": String,
                    "linkMo": String,
                    "linkPc": String,
                    "schemeIos": String,
                    "schemeAndroid": String
                }
            ]
        }
    ]
}
```

| 値           | タイプ | 必須 | 説明                                  |
| ---------------- | ------- | ---- | ---------------------------------------- |
| plusFriendId     | String  | X    | プラスフレンドID                                 |
| templateCode     | String  | O    | 登録した送信テンプレートコード                       |
| recipientList    | List    | O    | 受信者リスト(最大1,000人)                        |
| - recipientNo    | String  | O    | 受信番号                               |
| - content        | String  | O    | 内容                                  |
| - buttons        | List    | X    | ボタン                                  |
| -- ordering      | Integer | X    | ボタン順序(ボタンがある場合は必須)                      |
| -- type          | String  | X    | ボタンタイプ(WL：Webリンク、AL：アプリリンク、DS：配送照会、BK：Botキーワード、MD：メッセージ伝達) |
| -- name          | String  | X    | ボタン名(ボタンがある場合は必須)                      |
| -- linkMo        | String  | X    | モバイルWebリンク(WLタイプの場合、必須フィールド)                |
| -- linkPc        | String  | X    | PC Webリンク(WLタイプの場合、任意フィールド)                 |
| -- schemeIos     | String  | X    | iOSアプリリンク(ALタイプの場合、必須フィールド)                |
| -- schemeAndroid | String  | X    | Androidアプリリンク(ALタイプの場合、必須フィールド)            |


* <b>プラスフレンドIDフィールドを送信しない場合、最初に登録したプラスフレンドに送信されます。</b>
* <b>本文とボタンに置換が完了したデータを入れてください。</b>

[例]
```
curl -X POST -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/raw-messages -d '{"plusFriendId": "{プラスフレンドID}","templateCode": "{テンプレートコード}","recipientList":[{"recipientNo": "{受信番号}", "content": "{内容}", "buttons": [{ "ordering": "{ボタン順序}", "type": "{ボタンタイプ}", "name": "{ボタン名}", "linkMo": "{モバイルWebリンク}" }]}]}'
```

#### レスポンス

```
{
  "header": {
    "resultCode": Integer,
    "resultMessage": String,
    "isSuccessful": boolean
  },
  "message": {
    "requestId": String
  }
}
```

| 値          | タイプ | 説明 |
| --------------- | ------- | ------ |
| header          | Object  | ヘッダ領域 |
| - resultCode    | Integer | 結果コード |
| - resultMessage | String  | 結果メッセージ |
| - isSuccessful  | Boolean | 成否 |
| message         | Object  | 本文領域 |
| - requestId     | String  | リクエストID  |

## 送信リスト照会

#### リクエスト

[URL]

```
GET  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| 値 | タイプ | 説明 |
| ------ | ------ | ------ |
| appkey | String | 固有のアプリケーションキー |

[Header]
```
{
  "X-Secret-Key": String
}
```
| 値       | タイプ | 必須 | 説明                                  |
| ------------ | ------ | ---- | ---------------------------------------- |
| X-Secret-Key | String | O    | コンソールで作成できる。[[参考](./plus-friend-console-guide/#x-secret-key)] |

[Query parameter] 1番or 2番の条件は必須

| 値           | タイプ | 必須   | 説明                               |
| ---------------- | ------- | --------- | ------------------------------------- |
| requestId        | String  | 条件必須(1番) | リクエストID                                 |
| startRequestDate | String  | 条件必須(2番) | 送信リクエスト日の開始値(yyyy-MM-dd HH:mm)       |
| endRequestDate   | String  | 条件必須(2番) | 送信リクエスト日の終了値(yyyy-MM-dd HH:mm)        |
| recipientNo      | String  | X         | 受信番号                            |
| plusFriendId     | String  | X         | プラスフレンドID                              |
| templateCode     | String  | X         | テンプレートコード                           |
| messageStatus    | String  | X         | リクエストステータス(COMPLETED -> 成功、FAILED -> 失敗) |
| resultCode       | String  | X         | 送信結果(MRC01 -> 成功MRC02 -> 失敗)       |
| pageNum          | Integer | X         | ページ番号(基本：1)                         |
| pageSize         | Integer | X         | 照会件数(基本：15, 最大 : 1000)             |

#### レスポンス
```
{
  "header" : {
      "resultCode" :  Integer,
      "resultMessage" :  String,
      "isSuccessful" :  boolean
  },
  "messageSearchResultResponse" : {
    "messages" : [
    {
      "requestId" :  String,
      "plusFriendId" :  String,
      "templateCode" :  String,
      "recipientNo" :  String,
      "content" :  String,
      "requestDate" :  String,
      "receiveDate" : String,
      "resendStatus" :  String,
      "resendStatusName" :  String,
      "messageStatus" :  String,
      "resultCode" :  String,
      "resultCodeName" : String,
      "buttons" : [
        {
          "ordering" :  Integer,
          "type" :  String,
          "name" :  String,
          "linkMo" :  String,
          "linkPc": String,
          "schemeIos": String,
          "schemeAndroid": String
        }
      ]
    }
    ],
    "totalCount" :  Integer
  }
}
```

| 値                      | タイプ | 説明                                  |
| --------------------------- | ------- | ---------------------------------------- |
| header                      | Object  | ヘッダ領域                               |
| - resultCode                | Integer | 結果コード                               |
| - resultMessage             | String  | 結果メッセージ                              |
| - isSuccessful              | Boolean | 成否                                |
| messageSearchResultResponse | Object  | 本文領域                               |
| - messages                  | List    | メッセージリスト                             |
| -- requestId                | String  | リクエストID                                    |
| -- plusFriendId             | String  | プラスフレンドID                                 |
| -- templateCode             | String  | テンプレートコード                              |
| -- recipientNo              | String  | 受信番号                               |
| -- content                  | String  | 本文                                  |
| -- requestDate              | String  | リクエスト日時                               |
| -- receiveDate              | String  | 受信日時                               |
| -- resendStatus             | String  | 再送信ステータスコード                           |
| -- resendStatusName         | String  | 再送信ステータスコード名                           |
| -- messageStatus            | String  | リクエストステータス(COMPLETED -> 成功、FAILED -> 失敗)   |
| -- resultCode               | String  | 受信結果コード                            |
| -- resultCodeName           | String  | 受信結果コード名                            |
| -- buttons                  | List    | ボタンリスト                               |
| --- ordering                | Integer | ボタン順序                               |
| --- type                    | String  | ボタンタイプ(WL：Webリンク、AL：アプリリンク、DS：配送照会、BK：Botキーワード、MD：メッセージ伝達) |
| --- name                    | String  | ボタン名                               |
| --- linkMo                  | String  | モバイルWebリンク(WLタイプの場合、必須フィールド)                |
| --- linkPc                  | String  | PC Webリンク(WLタイプの場合、任意フィールド)                 |
| --- schemeIos               | String  | iOSアプリリンク(ALタイプの場合、必須フィールド)                |
| --- schemeAndroid           | String  | Androidアプリリンク(ALタイプの場合、必須フィールド)            |
| - totalCount                | Integer | 総個数                                 |

[例]
```
curl -X GET -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" "https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/messages?startRequestDate=2018-05-01%20:00&endRequestDate=2018-05-30%20:59"
```

#### SMS/LMS再送信ステータス
| 値 | 説明                         |
| ----- | ------------------------------- |
| RSC01 | 再送信の対象ではない                    |
| RSC02 | 再送信の対象(送信結果が失敗の時、再送信が行われます。) |
| RSC03 | 再送信中                       |
| RSC04 | 再送信成功                     |
| RSC05 | 再送信失敗                     |

## テンプレートリストの照会

#### リクエスト

[URL]

```
GET  /alimtalk/v1.0/appkeys/{appkey}/templates
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| 値 | タイプ | 説明 |
| ------ | ------ | ------ |
| appkey | String | 固有のアプリケーションキー |

[Header]
```
{
  "X-Secret-Key": String
}
```
| 値       | タイプ | 必須 | 説明                                  |
| ------------ | ------ | ---- | ---------------------------------------- |
| X-Secret-Key | String | O    | コンソールで作成できる。[[参考](./plus-friend-console-guide/#x-secret-key)] |

[Query parameter]

| 値         | タイプ | 必須 | 説明       |
| -------------- | ------- | ---- | ------------- |
| plusFriendId   | String  | X    | プラスフレンドID      |
| templateCode   | String  | X    | テンプレートコード   |
| templateName   | String  | X    | テンプレート名   |
| templateStatus | String  | X    | テンプレートステータスコード |
| pageNum        | Integer | X    | ページ番号(基本：1) |
| pageSize       | Integer | X    | 照会件数(基本：15, 最大 : 1000) |

| テンプレートステータスコード | 説明 |
| --------- | ---- |
| TSC01     | リクエスト |
| TSC02     | 検収中 |
| TSC03     | 承認 |
| TSC04     | 差し戻し |

[例]
```
curl -X GET -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" "https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/templates?plusFriendId={プラスフレンドID}&templateStatus={テンプレートステータスコード}"
```

#### レスポンス
```

{
  "header" : {
      "resultCode" :  Integer,
      "resultMessage" :  String,
      "isSuccessful" :  boolean
  },
  "templateListResponse": {
      "templates": [
          {
              "plusFriendId": String,
              "templateCode": String,
              "templateName": String,
              "templateContent": String,
              "buttons": [
                {
                    "ordering":Integer,
                    "type": String,
                    "name": String,
                    "linkMo": String,
                    "linkPc": String,
                    "schemeIos": String,
                    "schemeAndroid": String
                }
                ],
                "comments": [
                  {
                      "id": Integer,
                      "content": String,
                      "userName": String,
                      "createdAt": String,
                      "status": String
                    }  
                ],
                "status": String,
                "statusName": String,
                "createDate": String
            }
        ],
        "totalCount": Integer
    }
}
```

| 値               | タイプ | 説明                                  |
| -------------------- | ------- | ---------------------------------------- |
| header               | Object  | ヘッダ領域                               |
| - resultCode         | Integer | 結果コード                               |
| - resultMessage      | String  | 結果メッセージ                              |
| - isSuccessful       | Boolean | 成否                                |
| templateListResponse | Object  | 本文領域                               |
| - templates          | List    | テンプレートリスト                             |
| -- plusFriendId      | String  | プラスフレンドID                                 |
| -- templateCode      | String  | テンプレートコード                              |
| -- templateName      | String  | テンプレート名                                |
| -- templateContent   | String  | テンプレート本文                              |
| -- buttons           | List    | ボタンリスト                               |
| --- ordering         | Integer | ボタン順序(1～5)                               |
| --- type             | String  | ボタンタイプ(WL：Webリンク、AL：アプリリンク、DS：配送照会、BK：Botキーワード、MD：メッセージ伝達) |
| --- name             | String  | ボタン名                               |
| --- linkMo           | String  | モバイルWebリンク(WLタイプの場合、必須フィールド)                |
| --- linkPc           | String  | PC Webリンク(WLタイプの場合、任意フィールド)                 |
| --- schemeIos        | String  | iOSアプリリンク(ALタイプの場合、必須フィールド)                |
| --- schemeAndroid    | String  | Androidアプリリンク(ALタイプの場合、必須フィールド)            |
| -- comments          | List    | 検収結果                               |
| --- id               | Integer | お問い合わせID                                   |
| --- content          | String  | お問い合わせ内容                               |
| ---userName          | String  | 作成者                                  |
| ---createAt          | String  | 登録日                               |
| ---status            | String  | 応答状態(INQ：お問い合わせ、APR：承認、REJ：差し戻し、REP：返信) |
| -- status            | String  | テンプレートのステータス                              |
| -- statusName        | String  | テンプレートのステータス名                              |
| -- createDate        | String  | 作成日時                               |
| - totalCount         | Integer | 総個数                                 |
