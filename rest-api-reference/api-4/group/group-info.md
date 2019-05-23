# 그룹 정보

메시지 그룹 정보 조회 API 사용방법을 기술합니다.

이전에 삭제 되었거나, 생성 실패된 메시지 그룹을 포함한 모든 그룹 조회가 가능합니다.

## Request

GET [https://api.solapi.com/messages/v4/groups/{groupId}](https://api.solapi.com/messages/v4/groups/{groupId})

curl -X GET [https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO](https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature= \[SIGNATURE\]" \

### Required Path Parameters

* `groupId` - 조회할 그룹 아이디

  **Sample Code**

  request\(

  {

    url: "[https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO](https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO)",

    method: 'get',

    headers: {

  ```text
  'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]`
  ```

    }

  }

  \)

  conn = HTTPSConnection\('api.solapi.com'\)

  conn.request\(

  "GET",

  "/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO",

  {"Authorization":"HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"}\)

  conn.close\(\)

  &lt;?php

  $ch = curl\_init\(\);

  curl\_setopt\($ch, CURLOPT\_URL, "[https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO](https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO)"\);

  curl\_setopt\($ch, CURLOPT\_HTTPHEADER, array\(

  'Authorization: HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]'

  \)\);

  curl\_exec\($ch\);

  curl\_close\($ch\);

## Response

{ "agent": { "appId": "String", "appVersion": "String", "sdkVersion": "String", "osPlatform": "String" }, "count": { "sms": Int, "lms": Int, "mms": Int, "ata": Int, "cta": Int, "push": Int }, "log": Array, "groupId": "String", "status": "String", "accountId": "String", "apiVersion": "String", "\_id": "String" }

{ "agent": { "appId": "MYAPPID", "appVersion": null, "sdkVersion": null, "osPlatform": null }, "count": { "sms": 0, "lms": 0, "mms": 0, "ata": 0, "cta": 0 }, "log": \[ { "date": "2018-04-03 15:32:21", "message": "메시지 그룹 생성", "agent": { "appId": "MYAPPID", "appVersion": null, "sdkVersion": null, "osPlatform": null } } \], "groupId": "G4V20180403153221CKAFBUVJ51OF7AV", "status": "PENDING", "accountId": "12925149", "apiVersion": "4", "\_id": "G4V20180403153221CKAFBUVJ51OF7AV" }

* `agent` - 사용자 agent 정보
  * `appId` - 그룹 생성 시 함께 요청한 appId
  * `appVersion` - 그룹 생성 시 함께 요청한 앱 버전
  * `sdkVersion` - sdk를 이용하여 발송한 경우 해당 sdk의 버전
  * `osPlatform` - 그룹 생성 시 함께 요청한 운영체제 환경
* `count` - 그룹에 등록되어 있는 문자메시지 수
  * `sms` - 그룹에 등록된 sms 수
  * `lms` - 그룹에 등록된 lms 수
  * `mms` - 그룹에 등록된 mms 수
  * `ata` - 그룹에 등록된 ata 수
  * `cta` - 그룹에 등록된 cta 수
* `log` - 해당 메시지 그룹의 모든 이력 정보
* `groupId` - 해당 메시지 그룹의 아이디
* `status` - 해당 메시지 그룹의 상태 정보. 표시되는 값은 아래 status 참조
* `accountId` - 사용자 고유 값
* `apiVersion` - 요청에 사용된 api 버전 정보
* `_id` - groupId와 동일한 그룹 고유 값

  **Group Status**

* `PENDING` - 발송 대기중. 해당 그룹에 메시지 추가 등록 가능
* `SENDING` - 발송 접수됨. 더 이상의 메시지 등록 불가
* `FAILURE` - 그룹 생성 실패. 메시지 그룹 생성 중 문제가 발생하여 그룹 생성이 취소되거나, 실패함
* `DELETED` - 삭제됨. 삭제된 그룹, 발송 불가

  **Errors**

* `ValidationError(400)` - 유효하지 않은 `groupId`
* `ResourceNotFound(404)` - 존재하지 않는 그룹 조회 시도

