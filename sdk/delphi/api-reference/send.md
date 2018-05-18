### 문자전송(SEND)

구분 | 제한사항
---- | ----
SMS | 90바이트 까지 전송가능
LMS | 2,000바이트 까지 전송가능
MMS | 2,000바이트 텍스트, 1개의 이미지 전송

**Parameters : **
 - to - 받는사람 번호
 - from - 보내는사람 번호
 - text - 문자내용
 - type - 문자 타입
 - app_version - 어플리케이션 버젼 예) Purplebook 4.1
 - to - 받는사람 번호 여러개 입력시
 - image_path - image file path 이미지 파일 경로 설정 (기본 "./")
 - image - image file (지원형식 : 200KB 이하의 JPEG)
 - refname - 참조내용
 - country - 국가코드 한국:KR 일본:JP 미국:US 중국:CN
 - datetime - 예약전송시 날짜 설정        
 - subject - LMS, MMS 일때 제목        
 - charset - 인코딩 방식
 - srk - 솔루션 제공 수수료를 정산받을 솔루션 등록키
 - mode - test모드 수신번호를 반드시 01000000000 으로 테스트하세요. 예약필드 datetime는 무시됨. 결과값은 60. 잔액에서 실제 차감되며 다음날 새벽에 재충전됨
 - extension - 개별문자 보내기        
 
**Return : **아래와 같이 JSONObject 형태로 return
```json
{
  'recipient_number': '01012345678',
  'group_id': '20120217103829612403761364',
  'message_id': '20120217103830163531890062',
  'result_code': '00',
  'result_message': 'Success'
}
```