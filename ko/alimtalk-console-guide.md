## Notification > KakaoTalk Bizmessage > 알림톡 > 콘솔 사용 가이드

## 알림톡 일반 발송

알림톡 발송 화면입니다.

![alimtalk_01_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_01_201812.png)

플러스친구를 선택 후 등록된 템플릿을 불러옵니다.
플러스친구는 **Notification > KakaoTalk Bizmessage > 플러스친구 관리** 탭에서 확인할 수 있습니다.
템플릿은 **Notification > KakaoTalk Bizmessage > 알림톡 > 템플릿 관리** 탭에서 관리할 수 있습니다.

하단 **일반 발송**탭에서 템플릿에 존재하는 치환키값을 입력한 후 수신자 번호를 입력합니다.

입력 완료 후 우측 **발송** 버튼을 클릭하여 즉시 전송합니다.

## 알림톡 대량 발송

### 대량 발송 요청

하단 탭에서 **대량 발송**을 선택합니다.

![alimtalk_02_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_02_201812.png)

* 템플릿을 선택 후, **템플릿 다운로드** 버튼을 클릭 시 템플릿 치환자가 포함된 CSV 파일을 다운로드할 수 있습니다. 템플릿 치환자가 포함되지 않을 경우 발송 실패처리 됩니다.
* CSV 파일을 엑셀로 열어 저장할 시, 한글이 정상적으로 저장되지 않을 수 있으므로 검수 후 발송으로 치환이 정상적으로 되었는지 확인을 권장합니다.
* 파일 업로드는 CSV 파일만 가능하며, 크기는 최대 20MB이고, 발송할 수 있는 최대 수신자 수는 10,000명입니다.

![alimtalk_03_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_03_201812.png)

* **발송** 버튼 클릭 시 **검수 후 진행**, **즉시 발송** 2가지를 선택하여 발송할 수 있습니다.

![alimtalk_04_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_04_201812.png)

## 발송 결과 조회

![alimtalk_05_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_05_201812.png)

일반 발송을 통한 발송 결과를 조회할 수 있습니다.
**발신 일시**는 필수 조건입니다.

각 발송 메시지에 대한 상세 조회를 원하면 검색 결과 레코드 열을 클릭 시 상세 조회 창이 나타납니다.

![alimtalk_06_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_06_201812.png)

## 대량 발송 조회

### 발송/취소

대량 알림톡 발송 시 **검수 후 진행**을 선택하면 **대량 발송 조회** 탭에서 발송 및 취소를 진행할 수 있습니다.

![alimtalk_07_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_07_201812.png)

* **발송** 버튼 클릭 시 대량 발송을 진행합니다. 먼저 상세 조회를 통해 치환값을 확인하는것을 권장합니다.
* 발송 중 상태에서 **취소** 버튼을 누를 시, 일부 수신자에게 발송이 진행될 수 있습니다.

조회 열 클릭 시 하단 수신자별 조회 패널에 수신자 항목이 나타납니다.

![alimtalk_08_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_08_201812.png)

* 수신자 별 조회에서 해당 수신자를 선택하여, 발송 내용이 정상적으로 치환되었는지 확인할 수 있습니다.

![alimtalk_09_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_09_201812.png)

### 대량 발송 진행 상태
  - <b>대기:</b> 템플릿 파일 데이터를 읽는 작업을 진행하기 전 상태입니다.
  - <b>발송 준비:</b> 템플릿 파일 데이터를 로드 중인 상태입니다.
  - <b>발송 준비 완료:</b> 템플릿 파일 데이터를 모두 로드하여 발송 준비가 완료된 상태입니다. 요청 건(리스트의 행)을 선택하면 하단의 리스트에서 수신번호와 발송내용을 확인할 수 있습니다.
  - <b>발송 대기:</b> 발송 작업을 진행하기 전 상태입니다.
  - <b>발송 중:</b> 발송이 진행 중인 상태입니다.
  - <b>발송 완료:</b> 발송 요청이 정상적으로 완료된 상태입니다.
  - <b>발송 실패:</b> 발송 진행 중 발송 오류가 발생한 경우입니다.
  - <b>발송 취소:</b> 사용자가 발송을 취소한 상태입니다.


## 템플릿 관리

### 템플릿 등록

![alimtalk_10_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_10_201812.png)

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

#### 템플릿 수정

* <b><span style="color:red">반려</span></b> 상태의 템플릿만 수정 가능합니다.

#### 템플릿 삭제

* <b><span style="color:red">요청/반려</span></b> 상태의 템플릿만 삭제 가능합니다.

#### 템플릿 문의 등록

* <b><span style="color:red">검수 중/반려</span></b> 상태의 템플릿만 문의 등록이 가능합니다.
* 등록한 문의는 검수 결과에 추가되며, 카카오 검수자가 이를 확인합니다.
* 검수 결과에 템플릿 용도에 관한 문의, 반려 사유 내용이 추가됩니다.

## 통계
### 통계 조회

![alimtalk_11_201812.png](https://static.toastoven.net/prod_alimtalk/alimtalk_11_201812.png)

* 발송 요청 기간, 플러스친구, 템플릿 별로 통계를 조회할 수 있습니다.
* 발송요청, 성공, 실패, 대체발송건을 그래프와 표로 확인할 수 있습니다.
