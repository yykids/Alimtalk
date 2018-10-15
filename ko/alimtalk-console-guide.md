## Notification > KakaoTalk Bizmessage > 알림톡 > 콘솔 사용 가이드

## 알림톡 발송
![[그림 1] 알림톡 발송](http://static.toastoven.net/prod_alimtalk/alimtalk_01.png)
<center>[그림 1] 알림톡 발송</center>

## 알림톡 대량 발송
### 대량 발송 요청
![[그림 2] 알림톡 발송](http://static.toastoven.net/prod_alimtalk/alimtalk_02.png)
<center>[그림 2] 알림톡 대량 발송</center>

<h4>[참고 사항]</h4>
* 템플릿을 선택 후, 템플릿 다운로드 버튼을 클릭 시 템플릿 치환자가 포함된 CSV 파일을 다운로드할 수 있습니다. 템플릿 치환자가 포함되지 않을 경우 발송 실패처리 됩니다.
* CSV 파일을 엑셀로 열어 저장할 시, 한글이 정상적으로 저장되지 않을 수 있으므로 검수 후 발송으로 치환이 정상적으로 되었는지 확인을 권장합니다.
* 파일 업로드는 CSV 파일만 가능하며, 크기는 최대 20MB이고, 발송할 수 있는 최대 수신자 수는 10,000명입니다.

![[그림 3] 발송 선택](http://static.toastoven.net/prod_alimtalk/alimtalk_03.png)
<center>[그림 3] 발송 선택</center>

<h4>[참고 사항]</h4>
* 검수 후 발송, 즉시 발송 2가지를 선택하여 발송할 수 있습니다.

### 조회/발송/취소
![[그림 4] 대량 발송 조회](http://static.toastoven.net/prod_alimtalk/alimtalk_04.png)
<center>[그림 4] 대량 발송 조회</center>

<h4>[참고 사항]</h4>
* 발송 중 상태에서 취소 버튼을 누를 시, 일부 수신자에게 발송이 진행될 수 있습니다.

![[그림 5] 수신자 내용 확인](http://static.toastoven.net/prod_alimtalk/alimtalk_05.png)
<center>[그림 5] 수신자 내용 확인</center>

<h4>[참고 사항]</h4>
* 수신자 별 조회에서 해당 수신자를 선택하여, 발송 내용이 정상적으로 치환되었는지 확인할 수 있습니다.

### 대량 발송 진행 상태
  - <b>대기:</b> 템플릿 파일 데이터를 읽는 작업을 진행하기 전 상태입니다.
  - <b>발송 준비:</b> 템플릿 파일 데이터를 로드 중인 상태입니다.
  - <b>발송 준비 완료:</b> 템플릿 파일 데이터를 모두 로드하여 발송 준비가 완료된 상태입니다. 요청 건(리스트의 행)을 선택하면 하단의 리스트에서 수신번호와 발송내용을 확인할 수 있습니다.
  - <b>발송 대기:</b> 발송 작업을 진행하기 전 상태입니다.
  - <b>발송 중:</b> 발송이 진행 중인 상태입니다.
  - <b>발송 완료:</b> 발송 요청이 정상적으로 완료된 상태입니다.
  - <b>발송 실패:</b> 발송 진행 중 발송 오류가 발생한 경우입니다.
  - <b>발송 취소:</b> 사용자가 발송을 취소한 상태입니다.


## 발송 결과 조회
![[그림 6] 알림톡 발송 결과 조회](http://static.toastoven.net/prod_alimtalk/alimtalk_06.png)
<center>[그림 6] 알림톡 발송 결과 조회</center>

### 발송 결과 상세조회
![[그림 7] 발송결과 상세 조회](http://static.toastoven.net/prod_alimtalk/alimtalk_07.png)
<center>[그림 7] 발송 결과 상세 조회</center>

## 템플릿 관리
### 템플릿 리스트 조회
![[그림 8] 템플릿 리스트 조회](http://static.toastoven.net/prod_alimtalk/alimtalk_08.png)
<center>[그림 8] 템플릿 리스트 조회</center>

### 템플릿 상세내역
![[그림 9] 템플릿 상세내역](http://static.toastoven.net/prod_alimtalk/alimtalk_09.png)
<center>[그림 9] 템플릿 상세내역</center>

### 템플릿 등록
![[그림 10] 템플릿 등록](http://static.toastoven.net/prod_alimtalk/alimtalk_10.png)
<center>[그림 10] 템플릿 등록</center>


<h4>[주의 사항]</h4>
* 템플릿 코드는 10글자 이내의 영문/숫자만 등록 가능합니다.
* 템플릿명은 20글자까지 등록 가능합니다.
* 템플릿 내용은 한/영 구분없이 변수 및 URL 포함 1000자까지 등록 가능합니다.
* 버튼링크 URL은 100자까지 등록 가능합니다.
* 템플릿 치환자는 ex) #{치환자} 로 등록해주시면 됩니다.
* 버튼링크에 치환자 사용 시 http:// 또는 https:// 프로토콜을 명시해야 등록 가능합니다. ex) http://#{URL} 또는 https://#{URL}
* 템플릿 등록 시, <b>요청 -> 검수 중 -> 승인/반려</b> 상태 순서로 업데이트됩니다.
* 템플릿 반려 시, <b>문의 등록</b> 및 <b>수정</b> 기능으로 재검수 가능합니다.
* 반려된 템플릿은 <b>삭제</b> 후, 재등록 가능합니다.
* 자세한 사항은 [[템플릿 검수 가이드](https://www.bizmsg.kr/collected_statics/assets_landing/doc/alimtalk_template_guide.pdf)] 를 참고하시기 바랍니다.

### 템플릿 수정
![[그림 11] 템플릿 등록](http://static.toastoven.net/prod_alimtalk/alimtalk_11.png)
<center>[그림 11] 템플릿 수정</center>

<h4>[참고 사항]</h4>
* <b><span style="color:red">반려</span></b> 상태의 템플릿만 수정 가능합니다.

### 템플릿 삭제
![[그림 12] 템플릿 등록](http://static.toastoven.net/prod_alimtalk/alimtalk_12.png)
<center>[그림 12] 템플릿 삭제</center>

<h4>[참고 사항]</h4>
* <b><span style="color:red">요청/반려</span></b> 상태의 템플릿만 삭제 가능합니다.

### 템플릿 문의 등록
![[그림 13] 템플릿 등록](http://static.toastoven.net/prod_alimtalk/alimtalk_13.png)
<center>[그림 13] 템플릿 문의 등록</center>

<h4>[참고 사항]</h4>
* <b><span style="color:red">검수 중/반려</span></b> 상태의 템플릿만 문의 등록이 가능합니다.
* 등록한 문의는 검수 결과에 추가되며, 카카오 검수자가 이를 확인합니다.
* 검수 결과에 템플릿 용도에 관한 문의, 반려 사유 내용이 추가됩니다.

## 통계
### 통계 조회
![[그림 14] 통계 조회 ](http://static.toastoven.net/prod_alimtalk/alimtalk_14.png)
<center>[그림 14] 통계 조회</center>

* 발송 요청 기간, 플러스친구, 템플릿 별로 통계를 조회할 수 있습니다.
* 발송요청, 성공, 실패, 대체발송건을 그래프와 표로 확인할 수 있습니다.
