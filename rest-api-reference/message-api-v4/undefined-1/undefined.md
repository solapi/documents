# 그룹 생성

메시지 그룹 생성 API 사용방법을 기술합니다.

메시지 그룹은 메시지를 담는 그릇이 됩니다.  
한번의 요청으로 대량의 메시지를 관리/발송하기 위해서 발송 전 메시지 그룹을 생성해야 합니다.

그룹 생성 후 메시지를 등록하여 전송이 가능합니다. 모든 전송 요청은 그룹 단위로 진행되어, 해당 그룹에 등록된 모든 메시지는 일괄적으로 발송됩니다.

이미 발송에 사용된 메시지 그룹은 더 이상 발송할 수 없습니다.

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/groups" %}
{% api-method-summary %}
createMessageGroup
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="osPlatform" type="string" required=false %}
발송 운영체제 환경
{% endapi-method-parameter %}

{% api-method-parameter name="appVersion" type="string" required=false %}
발송하는 앱의 버전
{% endapi-method-parameter %}

{% api-method-parameter name="appId" type="string" required=false %}
쿨에스엠에스 앱스토어에 앱이 등록되어 있는 경우, 해당 앱의 아이디를 이용하여 발송 시 수익을 공유 받습니다.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "agent": { // 사용자 agent 정보
    "appId": null, // 그룹 생성 시 함께 요청한 appId
    "appVersion": "2.0", // 그룹 생성 시 함께 요청한 앱 버전
    "sdkVersion": "1.0", // sdk를 이용하여 발송한 경우 해당 sdk의 버전
    "osPlatform": "win" // 그룹 생성 시 함께 요청한 운영체제 환경
  },
  "count": {
    "total": 0, // 등록된 총 메시지 수
    "sentTotal": 0, // 전송 시도 메시지 수
    "sentFailed": 0, // 전송 실패 메시지 수
    "sentSuccess": 0, // 전송 완료 메시지 수
    "sentPending": 0, // 전송중 메시지 수
    "registeredFailed": 0, // 접수 실패 메시지 수
    "registeredSuccess": 0, // 접수 성공 메시지 수
    "sms": 0, // 그룹에 등록된 sms 수
    "lms": 0,
    "mms": 0,
    "ata": 0,
    "cta": 0
  },
  "log": [ // 그룹 이력
    {
      "message": "메시지 그룹이 생성되었습니다.",
      "createAt": "2018-06-27T09:56:22.556Z"
    }
  ],
  "status": "PENDING", // 해당 메시지 그룹의 상태 정보. (자세한 사항은 '그룹정보' 문서 참조)
  "scheduledDate": null, // 예약 발송일
  "accountId": "12925149", // 그룹 생성자 계정 고유번호
  "apiVersion": "4", // 사용된 api 버전
  "groupId": "G4V20180627185622HOXPCZNCRJ0U0TV", // 그룹 고유값
  "dateCreated": "2018-06-27T09:56:22.558Z", // 그룹 생성시각
  "dateUpdated": "2018-06-27T09:56:22.558Z", // 마지막 그룹 수정시각
  "_id": "G4V20180627185622HOXPCZNCRJ0U0TV"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
 유효하지 않은 앱 아이디
{% endapi-method-response-example-description %}

```javascript
{
    "statusCode": "400",
    "errorCode": "InvalidAppId",
    "errorMessage": "유효하지 않은 앱 아이디"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X POST https://rest.coolsms.co.kr/messages/v4/groups
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}
