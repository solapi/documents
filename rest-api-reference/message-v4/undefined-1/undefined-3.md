# 그룹 삭제

메시지 그룹 삭제 API 사용방법을 기술합니다.

## Request

{% tabs %}
{% tab title="URI" %}
DELETE [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}](https://rest.coolsms.co.kr/messages/v4/groups/{groupId})
{% endtab %}

{% tab title="Sample" %}
curl -X DELETE https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature= \[SIGNATURE\]"
{% endtab %}
{% endtabs %}

### Required Path Parameters

* `groupId` - 삭제할 그룹 아이디

## **Response**

{% tabs %}
{% tab title="Syntax" %}
{

"agent": {

  "appId": "String",

  "appVersion": "String",

  "sdkVersion": "String",

  "osPlatform": "String"

},

"count": {

  "sms": Int,

  "lms": Int,

  "mms": Int,

  "ata": Int,

  "cta": Int,

  "push": Int

},

"log": Array,

"groupId": "String",

"status": "String",

"accountId": "String",

"apiVersion": "String",

"\_id": "String"

}
{% endtab %}

{% tab title="Sample" %}
{

"agent": {

  "appId": "MYAPPID",

  "appVersion": null,

  "sdkVersion": null,

  "osPlatform": null

},

"count": {

  "sms": 0,

  "lms": 0,

  "mms": 0,

  "ata": 0,

  "cta": 0

},

"log": \[

  {

```text
"date": "2018-04-03 15:32:21",
"message": "메시지 그룹 생성",
"agent": {
  "appId": "MYAPPID",
  "appVersion": null,
  "sdkVersion": null,
  "osPlatform": null
}
```

  },

  {

```text
"date": "2018-04-05 17:07:01",
"message": "메시지 그룹 삭제"
```

  }

\],

"groupId": "G4V20180403153221CKAFBUVJ51OF7AV",

"status": "PENDING",

"accountId": "12925149",

"apiVersion": "4",

"\_id": "G4V20180403153221CKAFBUVJ51OF7AV"

}
{% endtab %}
{% endtabs %}

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
* `status` - 해당 메시지 그룹의 상태 정보. \(자세한 사항은 그룹정보조회 문서 참조\)
* `accountId` - 사용자 고유 값
* `apiVersion` - 요청에 사용된 api 버전 정보
* `_id` - groupId와 동일한 그룹 고유 값

  **Errors**

* `ValidationError(400)` - 유효하지 않은 `groupId`
* `ResourceNotFound(404)` - 존재하지 않는 그룹 삭제 시도 

