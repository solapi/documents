# 그룹 삭제

메시지 그룹 삭제 API 사용방법을 기술합니다.  
그룹 삭제 후 발송 및 복구가 불가합니다.

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/{groupId}" %}
{% api-method-summary %}
deleteMessageGroup
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
삭제 대상 그룹 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
응답 값의 자세한 필드 정보는 '그룹 생성' 문서 참조
{% endapi-method-response-example-description %}

```javascript
{
  "agent": {
    "appId": null,
    "appVersion": null,
    "sdkVersion": null,
    "osPlatform": null
  },
  "count": {
    "total": 0,
    "sentTotal": 0,
    "sentFailed": 0,
    "sentSuccess": 0,
    "sentPending": 0,
    "registeredFailed": 0,
    "registeredSuccess": 0,
    "sms": 0,
    "lms": 0,
    "mms": 0,
    "ata": 0,
    "cta": 0
  },
  "log": [
    {
      "message": "메시지 그룹이 생성되었습니다.",
      "createAt": "2018-06-27T10:27:47.176Z"
    },
    {
      "message": "메시지 그룹이 삭제되었습니다.",
      "createAt": "2018-06-27T10:28:00.184Z"
    }
  ],
  "status": "DELETED",
  "scheduledDate": null,
  "_id": "G4V20180307105937H3PTASXMNJG2JIO",
  "groupId": "G4V20180307105937H3PTASXMNJG2JIO",
  "accountId": "12925149",
  "apiVersion": "4",
  "dateCreated": "2018-06-27T10:27:47.177Z",
  "dateUpdated": "2018-06-27T10:28:00.266Z"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
유효하지 않은 groupId
{% endapi-method-response-example-description %}

```javascript
{
    "statusCode": "400",
    "errorCode": "ValidationError",
    "errorMessage": "유효하지 않은 groupId"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
존재하지 않는 메시지 그룹
{% endapi-method-response-example-description %}

```javascript
{
    "statusCode": "404",
    "errorCode": "ResourceNotFound",
    "errorMessage": "존재하지 않는 그룹 삭제 시도"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X DELETE https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

