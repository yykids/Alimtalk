## Notification > KakaoTalk Bizmessage > 친구톡 > 콘솔 사용 가이드

## 친구톡 일반 발송

![friendtalk_01_201812.png](https://static.toastoven.net/prod_alimtalk/friendtalk_01_201812.png)

플러스친구를 설정하고 내용을 입력하여 친구톡 형태의 메시지를 발송할 수 있습니다.
메시지에 이미지를 첨부하려면, 먼저 **이미지 관리** 탭에서 이미지를 등록해야 합니다.
수신자는 핸드폰 번호 형태로 작성할 수 있습니다.

### 광고성 메시지 전송 시 유의 사항

![[그림 3] 친구톡 광고 메시지](http://static.toastoven.net/prod_alimtalk/friendtalk_02.png)

* 광고 여부에서 '광고'로 선택할 경우, 광고성 메시지로 간주합니다.
* 광고성 메시지의 경우 정통망법상 광고성 정보 전송시 명시사항을 표시해야 합니다. 메시지 내용 제일 앞에 '(광고)' 표시, 수신거부 방식(홈 > 친구차단)이 표시됩니다.

## 친구톡 대량 발송

### 대량 발송 요청
하단 탭에서 대량 발송을 선택합니다.

![[그림 4] 친구톡 대량 발송](http://static.toastoven.net/prod_alimtalk/friendtalk_mass_04.png)

* 내용에 템플릿 치환자 ex) #{이름} 을 입력 후, 템플릿 다운로드 버튼을 클릭 시 템플릿 치환자가 포함된 CSV 파일을 다운로드할 수 있습니다.
* CSV 파일을 엑셀로 열어 저장할 시, 한글이 정상적으로 저장되지 않을 수 있으므로 검수 후 발송으로 치환이 정상적으로 되었는지 확인을 권장합니다.
* 파일 업로드는 CSV 파일만 가능하며, 크기는 최대 20MB이고, 발송할 수 있는 최대 수신자 수는 10,000명입니다.

![[그림 5] 친구톡 대량 csv](http://static.toastoven.net/prod_alimtalk/friendtalk_mass_05.png)

* 각 수신자 별, 템플릿 치환자의 값을 입력해줄 수 있습니다.
* 만약 템플릿 치환자가 없이 내용을 입력할 경우, 동일한 내용으로 모든 수신자에게 발송됩니다.

## 발송 결과 조회

![friendtalk_02_201812.png](https://static.toastoven.net/prod_alimtalk/friendtalk_02_201812.png)

발송 결과 조회 탭에서는 친구톡 메시지를 조회할 수 있습니다.

## 이미지 관리

### 이미지 등록, 삭제, 조회

![friendtalk_03_201812.png](https://static.toastoven.net/prod_alimtalk/friendtalk_03_201812.png)

친구톡에 사용할 이미지를 등록, 삭제할 수 있습니다.

#### 이미지 업로드 허용 범위
* 권장 사이즈 : 720px * 720px
* 제한 사이즈 : 가로 500px 미만 or 가로 : 세로 비율 2:1 미만 or 가로 : 세로 비율 3:4 초과는 업로드 제한
* 파일 형식 : jpg, png
* 파일 크기 : 최대 500 KB

## 대체 발송 관리

* 알림톡/친구톡 각 메시지 타입에 따라 플러스친구의 대체 발송 설정을 할 수 있습니다.
* 대체 발송 설정을 한 플러스친구의 메시지만 LMS 또는 SMS로 대체 발송됩니다.
* SMS appkey 수정 시, 모든 플러스친구의 대체 발송 설정은 초기화 됩니다.
* sms 상품을 통해 대체 발송되므로, sms 상품의 발송 API 명세에 따라 필드를 입력해야합니다. (sms 상품에 등록된 발신번호, 각종 필드 길이제한 등)
* 지정한 대체발송 타입의 byte 제한을 초과하는 대체 발송 제목, 내용은 잘려서 대체발송 될 수 있습니다. ([[SMS 주의사항](https://docs.toast.com/ko/Notification/SMS/ko/api-guide/#_1)] 참고)
* 친구톡 광고 메시지는 광고 sms API로 대체 발송되므로, 반드시 080수신 거부 번호를 등록해야 정상 대체발송 됩니다.
* 친구톡 광고 메시지의 resendContent 필드를 입력할 경우, sms 광고 API의 <span style="color:red">광고 문구</span>를 필수로 입력해야 정상 대체발송 됩니다. `(광고)내용[무료 수신거부]080XXXXXXX`
* 친구톡 광고 메시지의 resendContent 필드가 없을 경우, 등록된 080수신거부번호로 <span style="color:red">광고 문구</span>를 자동 생성해서 대체발송 됩니다.

![plusfriend_03_201812.png](https://static.toastoven.net/prod_alimtalk/plusfriend_03-1_201904.png)

## 통계

![friendtalk_04_201812.png](https://static.toastoven.net/prod_alimtalk/friendtalk_04_201812.png)

발송한 메시지의 통계 내역을 그래프와 수치로 나타냅니다.
특정 기간 동안의 요청, 성공, 실패, 대체 발송 건수를 확인할 수 있습니다.
