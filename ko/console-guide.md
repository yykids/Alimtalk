## Notification > Alimtalk > 콘솔 사용 가이드

## 준비 사항
### 플러스친구 생성
카카오 알림톡을 발송하려면 플러스친구를 먼저 등록하셔야 합니다. 플러스친구는 카카오톡 비즈니스 아이디입니다. 카카오 홈페이지에서 무료로 만들 수 있습니다. <a target="_blank" href="https://center-pf.kakao.com">[플러스친구 신청]</a>

<b>* 2017년 5월 24일 옐로아이디에서 플러스 친구로 변경되었습니다.</b>

![[그림 1] 플러스친구 개설하기](http://static.toastoven.net/prod_alimtalk/img01.png)
<center>[그림 1] 플러스친구 개설하기</center>

<b>인증을 위해 등록 이후 홈 공개로 설정 변경이 필요합니다.</b>
![[그림 2] 홈 공개 변경](http://static.toastoven.net/prod_alimtalk/img02.png)
<center>[그림 2] 홈 공개 변경</center>

## 상품 이용

### 상품 활성화

Console에 접속하여 Alimtalk을 활성화 합니다.

![[그림 3] 알림톡 서비스 활성화](http://static.toastoven.net/prod_alimtalk/img03.png)
<center>[그림 3] 알림톡 서비스 활성화</center>

### X-Secret-Key 생성
Console에 접속하여 SecretKey를 생성합니다.

![[그림 4] SecretKey 생성](http://static.toastoven.net/prod_alimtalk/img04.png)
<center>[그림 4] SecretKey 생성</center>

### 플러스 친구 등록
플러스 친구 등록이 완료되면 관리자 핸드폰으로 카카오 토큰 메시지가 전달됩니다.<br>
관리자로 등록된 핸드폰으로만 카카오톡 토큰 메시지가 전달됩니다.

![[그림 5] 플러스 친구 등록](http://static.toastoven.net/prod_alimtalk/image05.png)
<center>[그림 5] 플러스 친구 등록</center>
#### [참고 사항]
* 플러스친구 아이디는 플러스친구 개설 시, 등록한 검색용 아이디를 입력해야 합니다.
* 고객이 받는 알림톡 메세지는 카카오톡에 등록한 플러스 친구 이름으로 노출됩니다.

![[그림 6] 카카오톡 토큰](http://static.toastoven.net/prod_alimtalk/img06.png)
<center>[그림 6] 카카오톡 토큰</center>

### 토큰 등록
관리자 핸드폰으로 받은 토큰 메시지를 입력하면 등록이 완료됩니다.
![[그림 7] 토큰 등록](http://static.toastoven.net/prod_alimtalk/image07.png)
<center>[그림 7] 토큰 등록</center>

## 발신 프로필 관리
![[그림 8] 발신 프로필 관리](http://static.toastoven.net/prod_alimtalk/image08.png)
<center>[그림 8] 발신 프로필 관리</center>

## 알림톡 발송
![[그림 9] 알림톡 발송](http://static.toastoven.net/prod_alimtalk/img09.png)
<center>[그림 9] 알림톡 발송</center>

## 알림톡 대량 발송
![[그림 10] 알림톡 발송](http://static.toastoven.net/prod_alimtalk/img10.png)
<center>[그림 10] 알림톡 대량 발송</center>
#### [참고 사항]
* 템플릿을 선택 후, 템플릿 다운로드 버튼을 클릭 시 템플릿 치환자가 포함된 CSV 파일을 다운로드할 수 있습니다. 템플릿 치환자가 포함되지 않을 경우 발송 실패처리 됩니다.
* CSV 파일을 엑셀로 열어 저장할 시, 한글이 정상적으로 저장되지 않을 수 있으므로 검수 후 발송으로 치환이 정상적으로 되었는지 확인을 권장합니다.
* 파일 업로드는 CSV 파일만 가능하며, 크기는 최대 20MB입니다.

![[그림 11] 발송 선택](http://static.toastoven.net/prod_alimtalk/img11.png)
<center>[그림 11] 발송 선택</center>
#### [참고 사항]
* 검수 후 발송, 즉시 발송 2가지를 선택하여 발송할 수 있습니다.

![[그림 12] CSV 파일 작성](http://static.toastoven.net/prod_alimtalk/img12.png)
<center>[그림 12] CSV 파일 작성</center>

### 조회/발송/취소
![[그림 13] 대량 발송 조회](http://static.toastoven.net/prod_alimtalk/img13.png)
<center>[그림 13] 대량 발송 조회</center>
#### [참고 사항]
* 발송 중 상태에서 취소 버튼을 누를 시, 일부 수신자에게 발송이 진행될 수 있습니다.

![[그림 14] 수신자 내용 확인](http://static.toastoven.net/prod_alimtalk/img14.png)
<center>[그림 14] 수신자 내용 확인</center>
#### [참고 사항]
* 수신자 별 조회에서 해당 수신자를 선택하여, 발송 내용이 정상적으로 치환되었는지 확인할 수 있습니다.

### 대량 발송 진행 상태
대기: 템플릿 파일 데이터를 읽는 작업을 진행하기 전 상태입니다.
발송 준비: 템플릿 파일 데이터를 로드 중인 상태입니다.
발송 준비 완료: 템플릿 파일 데이터를 모두 로드하여 SMS발송 준비가 완료된 상태입니다. 예약 건(리스트의 행)을 선택하면 하단의 리스트에서 수신번호와 발송내용을 확인할 수 있습니다.
발송 대기: 발송 작업을 진행하기 전 상태입니다.
발송 중: 발송이 진행 중인 상태입니다.
발송 완료: 발송 요청이 정상적으로 완료된 상태입니다.
발송 실패: 발송 진행 중 발송 오류가 발생한 경우입니다.
발송 취소: 사용자가 발송을 취소한 상태입니다.


## 발송 결과 조회
![[그림 15] 알림톡 발송 결과 조회](http://static.toastoven.net/prod_alimtalk/img15.png)
<center>[그림 15] 알림톡 발송 결과 조회</center>

### 발송 결과 상세조회
![[그림 16] 발송결과 상세 조회](http://static.toastoven.net/prod_alimtalk/img16.png)
<center>[그림 16] 발송 결과 상세 조회</center>

## 템플릿 관리
### 템플릿 리스트 조회
![[그림 17] 템플릿 리스트 조회](http://static.toastoven.net/prod_alimtalk/img17.png)
<center>[그림 17] 템플릿 리스트 조회</center>

### 템플릿 상세내역
![[그림 18] 템플릿 상세내역](http://static.toastoven.net/prod_alimtalk/img18.png)
<center>[그림 18] 템플릿 상세내역</center>

### 템플릿 등록
![[그림 19] 템플릿 등록](http://static.toastoven.net/prod_alimtalk/img19.png)
<center>[그림 19] 템플릿 등록</center>

#### [주의 사항]
* 템플릿 코드는 10글자 이내의 영문/숫자만 등록 가능합니다.
* 템플릿명은 20글자까지 등록 가능합니다.
* 템플릿 내용은 한/영 구분없이 변수 및 URL 포함 1000자까지 등록 가능합니다.
* 버튼링크 URL은 100자까지 등록 가능합니다.
* 템플릿 치환자는 ex) #{치환자} 로 등록해주시면 됩니다.


## 발송 실패 설정
### SMS 정보 입력
![[그림 20] SMS 정보 입력 ](http://static.toastoven.net/prod_alimtalk/img20.png)
<center>[그림 20] SMS 정보 입력</center>

![[그림 21] 플러스친구 발송 실패 설정 ](http://static.toastoven.net/prod_alimtalk/img21.png)
<center>[그림 21] 플러스친구 발송 실패 설정</center>

* 플러스친구 별, 발송 실패 설정을 할 수 있습니다.
* 발송 실패 설정을 한 플러스친구의 알림톡 메세지만 LMS로 대체 발송됩니다.
* sms appkey 수정 시, 모든 플러스친구의 발송 실패 설정은 초기화 됩니다.

## 통계
### 통계 조회
![[그림 22] 통계 조회 ](http://static.toastoven.net/prod_alimtalk/img22.png)
<center>[그림 22] 통계 조회</center>

* 발송 요청 기간, 플러스친구, 템플릿 별로 통계를 조회할 수 있습니다.
* 발송요청, 성공, 실패, 대체발송건을 그래프와 표로 확인할 수 있습니다.

## 개인정보 수탁사 고지 안내
'고객'이 TOAST Cloud > Alimtalk 상품 이용 시, '고객' - '당사' 간 개인정보 처리에 관한 업무 위수탁 관계가 발생하는 바 정보통신망법 및 개인정보보호법에 따라 위탁자인 '고객'은 개인정보처리방침을 통해 '당사'에 개인정보를 위탁한 현황(수탁자 및 업무의내용)을 공개하여야 합니다.

이에, '당사'에서는 '고객'이 TOAST Cloud의 Alimtalk 상품을 이용함에 있어 관련 법령을 준수하고, 위탁현황 미공개로 인하여 과태료 등의 불이익을 받지 않도록 아래와 같이 가이드 할 수 있습니다.

(예시)<br>
[개인정보 수탁사 고지 안내]<br>
Alimtalk 상품 이용 시 고객사에서 운영하시는'개인정보처리방침' > 위탁 현황에 다음의 내용을 표기해주세요.<br>
수탁사 : 엔에이치엔엔터테인먼트<br>
업무의 내용 : 카카오 알림톡 발송 대행<br>
