## Notification > KakaoTalk Bizmessage > 오류 코드

## API 응답 코드
| service | isSuccess | resultCode | resultMessage |
| - | - | - | - |
| 공통 | true | 0 | 성공 |
| 공통 | false | -1000 | 유효하지 않은 appkey |
| 공통 | false | -1001 | 유효하지 않은 secretKey |
| 공통 | false | -1002 | 유효하지 않은 sms appkey |
| 공통 | false | -1003 | 유효하지 않은 sms 발신 번호 |
| 공통 | false | -1004 | 이미 등록된 플러스친구 |
| 공통 | false | -1005 | 플러스친구 10명 초과하여 등록 요청할 경우 |
| 공통 | false | -1008 | 플러스친구 토큰 등록 실패 |
| 공통 | false | -1009 | 첨부 파일 업로드 실패 |
| 공통 | false | -1017 | 일별 발송량을 초과한 발송 실패 |
| 공통 | false | -2016 | 수신자 1,000명 초과하여 발송 요청할 경우 |
| 공통 | false | -2017 | 존재하지 않는 플러스친구 |
| 공통 | false | -2018 | 유효하지 않은 버튼 parameter |
| 공통 | false | -2019 | 템플릿 본문 1,000글자 초과 실패 |
| 공통 | false | -2020 | 버튼명 14글자 초과 실패 |
| 공통 | false | -2021 | 모바일 링크/웹 링크(limkMo/linkPc) 100글자 초과 실패 |
| 공통 | false | -2022 | 이미지를 첨부하였는데 이미지링크(imageLink)를 입력하지 않은 경우 |
| 공통 | false | -2023 | 친구톡 메시지 본문이 400글자 초과할 경우 (이미지 첨부)|
| 공통 | false | -2024 | 친구톡 메시지 본문이 1,000글자 초과할 경우 |
| 공통 | false | -2025 | 예약 일시가 과거의 일시일 경우 |
| 공통 | false | -2026 | 예약 일시가 90일 이후의 일시일 경우 (최대 90일까지 가능) |
| 공통 | false | -2027 | 날짜 포맷이 달라 parsing 오류가 발생 |
| 공통 | false | -2028 | 유효하지 않은 요청 ID |
| 공통 | false | -2029 | 요청한 메시지가 없거나, 취소할 수 있는 메시지가 없는 경우 |
| 공통 | false | -2999 | 발송 요청한 모든 수신자 요청 실패 |
| 공통 | false | -3000 | 자유 버튼 타입의 템플릿일 경우, 버튼명/모바일 링크(linkMo)는 필수 값입니다 |
| 공통 | false | -3001 | 이미 존재하는 템플릿코드 또는 템플릿명 |
| 공통 | false | -3002 | 필요한 Request body 내용을 읽을 수 없을 경우 |
| 공통 | false | -3003 | 존재하는 않는 템플릿 |
| 공통 | false | -3004 | 발송할 템플릿 파라메터 오류 |
| 공통 | false | -3005 | 템플릿 상태 오류 (승인 전 발송 요청 시) |
| 공통 | false | -3006 | 버튼 URL은 반드시 http:// 또는 https:// 를 포함해야 합니다 |
| 공통 | false | -3007 | 자유 버튼 타입의 템플릿만 버튼명과 버튼 URL 입력 가능합니다 |
| 공통 | false | -3008 | 배송 조회 버튼 타입은 버튼 URL을 입력할 수 없습니다 |
| 공통 | false | -3009 | 버튼명이 존재하지 않습니다 |
| 공통 | false | -3010 | 템플릿 본문이 일치하지 않습니다. |
| 공통 | false | -3011 | 템플릿 버튼이 존재하지 않습니다 |
| 공통 | false | -4003 | 조회 범위는 한달 초과 |
| 공통 | false | -4004 | 존재하지 않는 appkey |
| 공통 | false | -4005 | 사용 종료 상태의 appkey |
| 공통 | false | -4006 | default 발신 프로필이 등록되지 않은 appkey |
| 공통 | false | -4007 | 파일 사이즈 500K 초과 |
| 공통 | false | -4015 | 유효하지 않은 request ID (requestId) |
| 공통 | false | -4016 | 요청한 값에 대응되는 데이터가 없는 경우 |
| 공통 | false | -4100 | 유효하지 않은 조회 기간 오류 |
| 공통 | false | -4101 | 유효하지 않은 통계 조회 parameter |
| 공통 | false | -4103 | 조회 시, 발송 요청 시작 시간/발송 요청 끝 시간 값이 없을 경우 |
| 공통 | false | -5000 | 유효하지 않은 수신 번호 |
| 공통 | false | -5001 | 발송 시, 수신자 리스트가 없을 경우 |
| 공통 | false | -7000 | 벤더 요청 API 실패 |
| 공통 | false | -8000 | 이미지 시퀀스(imageSeq)가 없는 경우 |
| 공통 | false | -8001 | 이미지 파일이 정상적이지 않은 경우 |
| 공통 | false | -8002 | 이미지 시퀀스(imageSeq)에 대응하느 이미지가 없는 경우 |
| 공통 | false | -8003 | 이미지 삭제에 실패하는 경우 |
| 공통 | false | -8005 | 이미지 업로드시 프로젝트에 등록된 플러스친구가 없는 경우 |
| 공통 | false | -9996 | Content-type이 application/json가 아닐 경우 |
| 공통 | false | -9998 | 존재하지 않는 API |
| 공통 | false | -9999 | 시스템 에러 |


## ATA V.1.0.9 전송결과코드
- ATA Version : ATA V1.0.9 이상

<table class="table table-striped table-hover">
<thead>
	<tr>
		<th>코드값</th>
		<th>의미</th>
	</tr>
</thead>
<tbody>
	<tr>
		<td>1000</td>
		<td>성공</td>
	</tr>
  <tr>
		<td>1001</td>
		<td>Server Busy (RS 내부 저장 Queue Full)</td>
	</tr>
  <tr>
		<td>1002</td>
		<td>수신번호 형식 오류</td>
	</tr>
  <tr>
		<td>1003</td>
		<td>회신번호 형식 오류</td>
	</tr>
  <tr>
		<td>1009</td>
		<td>CLIENT_MSG_KEY 없음</td>
	</tr>
  <tr>
		<td>1010</td>
		<td>CONTENT 없음</td>
	</tr>
  <tr>
		<td>1012</td>
		<td>RECIPIENT_INFO 없음</td>
	</tr>
  <tr>
		<td>1013</td>
		<td>SUBJECT 없음</td>
	</tr>
  <tr>
		<td>1018</td>
		<td>전송 권한 없음</td>
	</tr>
  <tr>
		<td>1019</td>
		<td>TTL 초과</td>
	</tr>
  <tr>
		<td>1020</td>
		<td>charset conversion error</td>
	</tr>
  <tr>
		<td>1099</td>
		<td>인증 실패</td>
	</tr>
	<tr>
		<td>2000</td>
		<td>전송 시간 초과</td>
	</tr>
	<tr>
		<td>2001</td>
		<td>메시지 전송 불가 (예기치 않은 오류 발생)</td>
	</tr>
	<tr>
		<td>3009</td>
		<td>메시지 형식 오류</td>
	</tr>
	<tr>
		<td>3014</td>
		<td>알 수 없는 메시지 상태</td>
	</tr>
	<tr>
		<td>3015</td>
		<td>msg_type 오류(1008 또는 1009 가 아닌경우)</td>
	</tr>
	<tr>
		<td>3023</td>
		<td>메시지 문법 오류(JSON형식오류)</td>
	</tr>
	<tr>
		<td>3024</td>
		<td>발신 프로필 키가 유효하지 않음</td>
	</tr>
	<tr>
		<td>3025</td>
		<td>메시지 전송 실패 (테스트 시, 친구관계가 아닌 경우)</td>
	</tr>
	<tr>
		<td>3026</td>
		<td>메시지와 템플릿의 일치성 확인시 오류 발생</td>
	</tr>
	<tr>
		<td>3027</td>
		<td>카카오톡을 사용하지 않는 사용자 (전화번호 오류 / 050 안심번호)</td>
	</tr>
	<tr>
		<td>3029</td>
		<td>메시지가 존재하지 않음</td>
	</tr>
	<tr>
		<td>3030</td>
		<td>메시지 일련번호가 중복됨</td>
	</tr>
	<tr>
		<td>3031</td>
		<td>메시지가 비어 있음</td>
	</tr>
	<tr>
		<td>3032</td>
		<td>메시지 길이 제한 오류 (공백 포함 1000 자)</td>
	</tr>
	<tr>
		<td>3033</td>
		<td>템플릿을 찾을 수 없음</td>
	</tr>
	<tr>
		<td>3034</td>
		<td>메시지가 템플릿과 일치하지 않음</td>
	</tr>
	<tr>
		<td>3040</td>
		<td>허브 파트너 키가 유효하지 않음</td>
	</tr>
	<tr>
		<td>3041</td>
		<td>Request Body에서 Name을 찾을수 없음</td>
	</tr>
	<tr>
		<td>3042</td>
		<td>발신 프로필을 찾을 수 없음</td>
	</tr>
	<tr>
		<td>3043</td>
		<td>삭제된 발신 프로필</td>
	</tr>
	<tr>
		<td>3044</td>
		<td>차단 상태의 발신 프로필</td>
	</tr>
	<tr>
		<td>3045</td>
		<td>차단 상태의 옐로아이디</td>
	</tr>
	<tr>
		<td>3046</td>
		<td>닫힘 상태의 옐로아이디</td>
	</tr>
	<tr>
		<td>3047</td>
		<td>삭제된 옐로아이디</td>
	</tr>
	<tr>
		<td>3048</td>
		<td>계약정보를 찾을수 없음</td>
	</tr>
	<tr>
		<td>3049</td>
		<td>내부 시스템 오류로 메시지 전송 실패</td>
	</tr>
	<tr>
		<td>3050</td>
		<td>카카오톡을 사용하지 않는 사용자<br>
        72시간 이내에 카카오톡 사용 이력이 없는 사용자 알림톡 차단을 선택한 사용자<br>
        친구톡의 경우 친구가 아닌경우<br></td>
	</tr>
	<tr>
		<td>3051</td>
		<td>메시지가 발송되지 않은 상태</td>
	</tr>
	<tr>
		<td>3054</td>
		<td>메시지 발송 가능한 시간이 아님</td>
	</tr>
  <tr>
		<td>3055</td>
		<td>메시지 그룹 정보를 찾을 수 없음</td>
	</tr>
  <tr>
		<td>3056</td>
		<td>메시지 전송 결과를 찾을 수 없음</td>
	</tr>
  <tr>
		<td>3060</td>
		<td>사용자에게 발송하였으나 수신여부 불투명(Polling)</td>
	</tr>
  <tr>
		<td>9998</td>
		<td>시스템에 문제가 발생하여 담당자가 확인중(현재 서비스 제공중이 아님)</td>
	</tr>
  <tr>
		<td>9999</td>
		<td>시스템에 문제가 발생하여 담당자가 확인중(시스템에 알 수 없는 오류 발생)</td>
	</tr>
	<tr>
		<td>E900</td>
		<td>전송키가 없는 경우</td>
	</tr>
	<tr>
		<td>E901</td>
		<td>수신번호가 없는 경우</td>
	</tr>
	<tr>
		<td>E903</td>
		<td>제목 없는 경우</td>
	</tr>
	<tr>
		<td>E904</td>
		<td>메시지가 없는 경우</td>
	</tr>
	<tr>
		<td>E905</td>
		<td>회신번호가 없는 경우</td>
	</tr>
	<tr>
		<td>E906</td>
		<td>메시지키가 없는 경우</td>
	</tr>
	<tr>
		<td>E915</td>
		<td>중복메시지</td>
	</tr>
	<tr>
		<td>E916</td>
		<td>인증서버 차단번호</td>
	</tr>
	<tr>
		<td>E917</td>
		<td>고객DB 차단번호</td>
	</tr>
	<tr>
		<td>E918</td>
		<td>USER CALLBACK FAIL</td>
	</tr>
	<tr>
		<td>E919</td>
		<td>발송 제한 시간인 경우, 메시지 재발송 처리가 금지 된 경우</td>
	</tr>
	<tr>
		<td>E920</td>
		<td>서비스 타입이 알림톡인 경우, 메시지 테이블에 파일그룹키가 있는 경우</td>
	</tr>
	<tr>
		<td>E999</td>
		<td>기타오류</td>
	</tr>
</tbody>
</table>
