# 그룹 정보

메시지 그룹 정보 조회 API 사용방법을 기술합니다.

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/{groupId}" %}
{% api-method-summary %}
getMessageGroupInfo
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
조회 대상 그룹 아이디
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
      "createAt": "2018-06-27T10:32:04.589Z"
    }
  ],
  "status": "PENDING",
  "scheduledDate": null,
  "_id": "G4V20180307105937H3PTASXMNJG2JIO",
  "groupId": "G4V20180307105937H3PTASXMNJG2JIO",
  "accountId": "12925149",
  "apiVersion": "4",
  "dateCreated": "2018-06-27T10:32:04.591Z",
  "dateUpdated": "2018-06-27T10:32:04.591Z"
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
    "errorMessage": "메시지 그룹을 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### Group Status

* `PENDING` - 대기중 \(그룹 전송 준비\)
* `SENDING` - 전송 요청됨
* `COMPLETE` - 처리 완료
* `FAILED` - 생성 실패
* `DELETED` - 삭제됨
* `SCHEDULED` - 발송 예약 됨 \(예약 취소전까지 그룹 삭제 불가\)

### Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X GET https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

