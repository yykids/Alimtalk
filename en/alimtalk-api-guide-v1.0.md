## Notification > KakaoTalk Bizmessage > Alimtalk > API v1.0 Guide

## Alimtalk

#### [API Domain]

<table>
<thead>
<tr>
<th>Domain</th>
</tr>
</thead>
<tbody>
<tr>
<td>https://api-alimtalk.cloud.toast.com</td>
</tr>
</tbody>
</table>

## Send Messages

#### Request of Sending Replaced Messages

[URL]

```
POST  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| Value  | Type   | Description     |
| ------ | ------ | --------------- |
| appkey | String | Original appkey |

[Header]
```
{
  "X-Secret-Key": String
}
```
| Value        | Type   | Required | Description                                                  |
| ------------ | ------ | -------- | ------------------------------------------------------------ |
| X-Secret-Key | String | O        | Can be created on a console. [[Reference](./plus-friend-console-guide/#x-secret-key)] |

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

| Value               | Type   | Required | Description                                                  |
| ------------------- | ------ | -------- | ------------------------------------------------------------ |
| plusFriendId        | String | X        | PlusFriend ID                                                |
| templateCode        | String | O        | Registered delivery template code                            |
| recipientList       | List   | O        | List of recipients (up to 1000)                              |
| - recipientNo       | String | O        | Recipient number                                             |
| - templateParameter | Object | X        | Template parameter<br>(Required, if it includes a variable to be replaced for template) |
| -- key              | String | X        | Replacement key (#{key})                                     |
| -- value            | String | X        | Value which is mapped for replacement key                    |

* <b>Send the first-registered Plusfriend, if Plusfriend ID field is not sent. </b>

[Example]
```
curl -X POST -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/messages -d '{"plusFriendId": "{PlusFriend ID}","templateCode": "{template code}","recipientList":[{"recipientNo": "{recipient number}","templateParameter": { "{replaced field}": "{replacement data}" }}]}'
```

#### Request of Sending Full Text  

[URL]

```
POST  /alimtalk/v1.0/appkeys/{appkey}/raw-messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| Value  | Type   | Description     |
| ------ | ------ | --------------- |
| appkey | String | Original appkey |

[Header]

```
{
  "X-Secret-Key": String
}
```
| Value        | Type   | Required | Description                                                  |
| ------------ | ------ | -------- | ------------------------------------------------------------ |
| X-Secret-Key | String | O        | Can be created on console. [[Reference](./plus-friend-console-guide/#x-secret-key)] |

[Request Body]

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

| Value            | Type    | Required | Description                                                  |
| ---------------- | ------- | -------- | ------------------------------------------------------------ |
| plusFriendId     | String  | X        | PlusFriend ID                                                |
| templateCode     | String  | O        | Registered delivery template code                            |
| recipientList    | List    | O        | List of recipients (up to 1,000)                             |
| - recipientNo    | String  | O        | Recipient number                                             |
| - content        | String  | O        | Body                                                         |
| - buttons        | List    | X        | Button                                                       |
| -- ordering      | Integer | X        | Button sequence (required, if there is a button)             |
| -- type          | String  | X        | Button type (WL: Web Link, AL: App Link, DS: Delivery Search, BK: Bot Keyword, MD: Message Delivery) |
| -- name          | String  | X        | Button name (required, if there is a button)                 |
| -- linkMo        | String  | X        | Mobile web link (required for the WL type)                   |
| -- linkPc        | String  | X        | PC web link (optional for the WL type)                       |
| -- schemeIos     | String  | X        | iOS app link (required for the AL type)                      |
| -- schemeAndroid | String  | X        | Android app link (required for the AL type)                  |


* <b>Send the first-registered PlusFriend if PlusFriend ID field is not sent. </b>
* <b>Enter data completed with replacement in the body and button. </b>

[Example]
```
curl -X POST -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/raw-messages -d '{"plusFriendId": "{PlusFriend ID}","templateCode": "{template code}","recipientList":[{"recipientNo": "{recipient number}", "content": "{body}", "buttons": [{ "ordering": "{button sequence}", "type": "{button type}", "name": "{button name}", "linkMo": "{mobile web link}" }]}]}'
```

#### Response

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

| Value           | Type    | Description       |
| --------------- | ------- | ----------------- |
| header          | Object  | Header area       |
| - resultCode    | Integer | Result code       |
| - resultMessage | String  | Result message    |
| - isSuccessful  | Boolean | Successful or not |
| message         | Object  | Body area         |
| - requestId     | String  | Request ID        |

## List Deliveries

#### Request

[URL]

```
GET  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| Value  | Type   | Description     |
| ------ | ------ | --------------- |
| appkey | String | Original appkey |

[Header]
```
{
  "X-Secret-Key": String
}
```
| Value        | Type   | Required | Description                                                  |
| ------------ | ------ | -------- | ------------------------------------------------------------ |
| X-Secret-Key | String | O        | Can be created on console. [[Reference](./plus-friend-console-guide/#x-secret-key)] |

[Query parameter] No. 1 or 2 is conditionally required

| Value            | Type    | Required                      | Description                                                |
| ---------------- | ------- | ----------------------------- | ---------------------------------------------------------- |
| requestId        | String  | Conditionally required (no.1) | Request ID                                                 |
| startRequestDate | String  | Conditionally required (no.2) | Start date of delivery request (yyyy-MM-dd HH:mm)          |
| endRequestDate   | String  | Conditionally required (no.2) | End date of delivery request (yyyy-MM-dd HH:mm)            |
| recipientNo      | String  | X                             | Recipient number                                           |
| plusFriendId     | String  | X                             | PlusFriend ID                                              |
| templateCode     | String  | X                             | Template code                                              |
| messageStatus    | String  | X                             | Request status (COMPLETED -> successful, FAILED -> failed) |
| resultCode       | String  | X                             | Delivery result (MRC01 ->successful, MRC02 -> failed)      |
| pageNum          | Integer | X                             | Page number (default: 1)                                   |
| pageSize         | Integer | X                             | Number of queries (default: 15, max : 1000)                |

#### Response
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

| Value                       | Type    | Description                                                  |
| --------------------------- | ------- | ------------------------------------------------------------ |
| header                      | Object  | Header area                                                  |
| - resultCode                | Integer | Result code                                                  |
| - resultMessage             | String  | Result message                                               |
| - isSuccessful              | Boolean | Successful or not                                            |
| messageSearchResultResponse | Object  | Body area                                                    |
| - messages                  | List    | List of messages                                             |
| -- requestId                | String  | Request ID                                                   |
| -- plusFriendId             | String  | PlusFriend ID                                                |
| -- templateCode             | String  | Template code                                                |
| -- recipientNo              | String  | Recipient number                                             |
| -- content                  | String  | Body message                                                 |
| -- requestDate              | String  | Date and time of request                                     |
| -- receiveDate              | String  | Date and time of receiving                                   |
| -- resendStatus             | String  | Status code of resending                                     |
| -- resendStatusName         | String  | Status code name of resending                                |
| -- messageStatus            | String  | Request status (COMPLETED -> successful, FAILED -> failed )  |
| -- resultCode               | String  | Result code of receiving                                     |
| -- resultCodeName           | String  | Result code name of receiving                                |
| -- buttons                  | List    | List of buttons                                              |
| --- ordering                | Integer | Button sequence                                              |
| --- type                    | String  | Button type (WL: Web Link, AL: App Link, DS: Delivery Search, BK: Bot Keyword, MD: Message Delivery) |
| --- name                    | String  | Button name                                                  |
| --- linkMo                  | String  | Mobile web link (required for the WL type)                   |
| --- linkPc                  | String  | PC web link (required for the WL type)                       |
| --- schemeIos               | String  | iOS app link (required for the AL type)                      |
| --- schemeAndroid           | String  | Android app link (required for the AL type)                  |
| - totalCount                | Integer | Total Count                                                  |

[Example]
```
curl -X GET -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" "https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/messages?startRequestDate=2018-05-01%20:00&endRequestDate=2018-05-30%20:59"
```

#### Status of Resending SMS/LMS
| Value | Description                                     |
| ----- | ----------------------------------------------- |
| RSC01 | No target of resending                          |
| RSC02 | Target of resending (resent, if sending fails.) |
| RSC03 | Resending                                       |
| RSC04 | Resending successful                            |
| RSC05 | Resending failed                                |

## List Templates

#### Request

[URL]

```
GET  /alimtalk/v1.0/appkeys/{appkey}/templates
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

| Value  | Type   | Description     |
| ------ | ------ | --------------- |
| appkey | String | Original appkey |

[Header]
```
{
  "X-Secret-Key": String
}
```
| Value        | Type   | Required | Description                                                  |
| ------------ | ------ | -------- | ------------------------------------------------------------ |
| X-Secret-Key | String | O        | Can be created on console. [[Reference](./plus-friend-console-guide/#x-secret-key)] |

[Query parameter]

| Value          | Type    | Required | Description                     |
| -------------- | ------- | -------- | ------------------------------- |
| plusFriendId   | String  | X        | PlusFriend ID                   |
| templateCode   | String  | X        | Template code                   |
| templateName   | String  | X        | Template name                   |
| templateStatus | String  | X        | Template status code            |
| pageNum        | Integer | X        | Page number (default: 1)        |
| pageSize       | Integer | X        | Number of queries (default: 15, max : 1000) |

| Template Status Code | Description |
| -------------------- | ----------- |
| TSC01                | Requested   |
| TSC02                | Inspecting  |
| TSC03                | Approved    |
| TSC04                | Returned    |

[Example]

```
curl -X GET -H "Content-Type: application/json;charset=UTF-8" -H "X-Secret-Key:{secretkey}" "https://api-alimtalk.cloud.toast.com/alimtalk/v1.0/appkeys/{appkey}/templates?plusFriendId={PlusFriend ID}&templateStatus={template status code}"
```

#### Response
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

| Value                | Type    | Description                                                  |
| -------------------- | ------- | ------------------------------------------------------------ |
| header               | Object  | Header area                                                  |
| - resultCode         | Integer | Result code                                                  |
| - resultMessage      | String  | Result message                                               |
| - isSuccessful       | Boolean | Successful or not                                            |
| templateListResponse | Object  | Body area                                                    |
| - templates          | List    | List of templates                                            |
| -- plusFriendId      | String  | PlusFriend ID                                                |
| -- templateCode      | String  | Template code                                                |
| -- templateName      | String  | Template name                                                |
| -- templateContent   | String  | Template body                                                |
| -- buttons           | List    | List of buttons                                              |
| --- ordering         | Integer | Button sequence (1~5)                                        |
| --- type             | String  | Button type (WL: Web Link, AL: App Link, DS: Delivery Search, BK: Bot Keyword, MD: Message Delivery) |
| --- name             | String  | Button name                                                  |
| --- linkMo           | String  | Mobile web link (required for the WL type)                   |
| --- linkPc           | String  | PC web link (optional for the WL type)                       |
| --- schemeIos        | String  | iOS app link (required for the AL type)                      |
| --- schemeAndroid    | String  | Android app link (required for the AL type)                  |
| -- comments          | List    | Inspection result                                            |
| --- id               | Integer | Inquiry ID                                                   |
| --- content          | String  | Inquiry content                                              |
| ---userName          | String  | Creator                                                      |
| ---createAt          | String  | Date of registration                                         |
| ---status            | String  | Comment status (INQ: Inquired, APR: Approved, REJ: Returned, REP: Replied) |
| -- status            | String  | Template status                                              |
| -- statusName        | String  | Template status name                                         |
| -- createDate        | String  | Date and time of creation                                    |
| - totalCount         | Integer | Total Count                                                  |
