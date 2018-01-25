## Notification > Alimtalk > API Guide

## Alimtalk

#### [API 도메인]

<table>
<thead>
<tr>
<th>도메인</th>
</tr>
</thead>
<tbody>
<tr>
<td>https://api-alimtalk.cloud.toast.com</td>
</tr>
</tbody>
</table>

## 메시지 발송

#### 요청

[URL]

```
POST  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

|값|	타입|	설명|
|---|---|---|
|appkey|	String|	고유의 appkey|

[Header]
```
{
  "X-Secret-Key": String
}
```
|값|	타입|	필수|	설명|
|---|---|---|---|
|X-Secret-Key|	String| O | [CONSOLE]에서 생성할 수 있다. [[참고](./console-guide/#x-secret-key)] |

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

|값|	타입|	필수|	설명|
|---|---|---|---|
|plusFriendId|	String|	X | 플러스친구 아이디 |
|templateCode|	String|	O | 등록한 발송 템플릿 코드 |
|recipientList|	List|	O|	수신자 리스트 (최대 1000명) |
|- recipientNo|	String|	O|	수신번호 |
|- templateParameter|	Object|	X|	템플릿 파라미터<br>(템플릿에 치환할 변수 포함 시, 필수) |
|-- key|	String|	X |	치환 키(#{key})|
|-- value| String |	X |	치환 키에 매핑되는 Value값|

* <b>플러스친구 아이디 필드를 보내지 않을 경우, 첫 번째 등록한 플러스친구로 발송됩니다.</b>

#### 응답

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

|값|	타입|	설명|
|---|---|---|
|header|	Object|	헤더 영역|
|- resultCode|	Integer|	결과 코드|
|- resultMessage|	String| 결과 메시지|
|- isSuccessful|	Boolean| 성공 여부|
|message|	Object|	본문 영역|
|- requestId | String |	요청 아이디 |

## 발송 리스트 조회

#### 요청

[URL]

```
GET  /alimtalk/v1.0/appkeys/{appkey}/messages
Content-Type: application/json;charset=UTF-8
```

[Path parameter]

|값|	타입|	설명|
|---|---|---|
|appkey|	String|	고유의 appkey|

[Header]
```
{
  "X-Secret-Key": String
}
```
|값|	타입|	필수|	설명|
|---|---|---|---|
|X-Secret-Key|	String| O | [CONSOLE]에서 생성할 수 있다. [[참고](./console-guide/#x-secret-key)] |

[Query parameter] 1번 or 2번 조건 필수

|값|	타입|	필수|	설명|
|---|---|---|---|
|requestId|	String|	조건 필수 (1번) | 요청 아이디 |
|startRequestDate|	String|	조건 필수 (2번) | 발송 요청 날짜 시작 값(yyyy-MM-dd HH:mm)|
|endRequestDate|	String| 조건 필수 (2번) |	발송 요청 날짜 끝 값(yyyy-MM-dd HH:mm) |
|recipientNo|	String|	X |	수신번호 |
|plusFriendId|	String|	X |	플러스 친구 아이디 |
|templateCode|	String|	X |	템플릿 코드|
|messageStatus| String |	X | 요청 상태 ( COMPLETED -> 성공, FAILED -> 실패 )	|
|resultCode| String |	X | 발송 결과 ( MRC01 -> 성공 MRC02 -> 실패 )	|
|pageNum|	Integer|	X|	페이지 번호(Default : 1)|
|pageSize|	Integer|	X|	조회 건수(Default : 15)|

#### 응답
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
      "resendStatus" :  String,
      "messageStatus" :  String,
      "resultCode" :  String,
      "resultCodeName" : String,
      "buttons" : [
      {
        "ordering" :  Integer,
        "type" :  String,
        "name" :  String,
        "linkMo" :  String
      }
      ]
    }
    ],
    "totalCount" :  Integer
  }
}
```

|값|	타입|	설명|
|---|---|---|
|header|	Object|	헤더 영역|
|- resultCode|	Integer|	결과 코드|
|- resultMessage|	String| 결과 메시지|
|- isSuccessful|	Boolean| 성공 여부|
|messageSearchResultResponse|	Object|	본문 영역|
|- messages | List |	메세지 리스트 |
|-- requestId | String |	요청 아이디 |
|-- plusFriendId | String |	플러스 친구 아이디 |
|-- templateCode | String |	템플릿 코드 |
|-- recipientNo | String |	수신 번호 |
|-- content | String |	본문 |
|-- requestDate | String |	요청 일시 |
|-- resendStatus | String |	재발송 상태 |
|-- messageStatus | String |	요청 상태 ( COMPLETED -> 성공, FAILED -> 실패 ) |
|-- resultCode | String |	수신 결과 코드 |
|-- resultCodeName | String |	수신 결과 코드명 |
|-- buttons | List |	버튼 리스트 |
|--- ordering | Integer |	버튼 순서 |
|--- type | String |	버튼 타입 |
|--- name | String |	버튼 이름 |
|--- linkMo | String |	버튼 링크 |

#### 재발송 상태
|값|	설명|
|---|---|
|RSC01|	재발송 미대상|
|RSC02|	재발송 대상 (발송 결과 실패 시, 재발송이 진행됩니다.)|
|RSC03|	재발송 중|
|RSC04|	재발송 성공|
|RSC05|	재발송 실패|
