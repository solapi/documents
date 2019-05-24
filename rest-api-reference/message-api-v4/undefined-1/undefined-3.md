# 그룹 삭제

메시지 그룹 삭제 API 사용방법을 기술합니다.  
그룹 삭제 후 발송 및 복구가 불가합니다.

{% api-method method="delete" host="https://api.solapi.com" path="/messages/v4/groups/{groupId}" %}
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
  "count":{
    "total":0, // 추가된 총 메시지의 개수
    "sentTotal":0, // 발송 시도된 총 메시지의 개수
    "sentFailed":0, // 발송 실패한 메시지의 개수
    "sentSuccess":0, // 발송 성공한 메시지의 개수
    "sentPending":0, // 발송 중인 메시지의 개수
    "sentReplacement":0, // 대체 발송 메시지의 개수
    "refund":0, // 환급된 메시지의 개수
    "registeredFailed":0, // 등록 실패한 메시지의 개수
    "registeredSuccess":0 // 등록 성공한 메시지의 개수
  },
  "countForCharge":{ // 차감할 타입/국가별 문자 카운트
    "sms":{ // { 국가코드: 카운트 } 형식으로 돼있습니다.

    },
    "lms":{

    },
    "mms":{

    },
    "ata":{

    },
    "cta":{

    }
  },
  "balance":{
    "requested":0, // 발송시 차감 금액
    "replacement":0, // 대체발송 차감 금액
    "refund":0, // 환급으로 인해 충전된 금액
    "sum":0 // 실제로 차감된 금액
  },
  "point":{
    "requested":0, // 발송시 차감 포인트
    "replacement":0, // 대체발송 차감 포인트
    "refund":0, // 환급으로 인해 충전된 포인트
    "sum":0 // 실제로 차감된 포인트
  },
  "app":{
    "profit":{
      "sms":0, // 타입별 앱에 설정된 수익금
      "lms":0,
      "mms":0,
      "ata":0,
      "cta":0
    },
    // 앱 정보
    "appId":null,
    "version":null
  },
  "sdkVersion":"1.0",
  "osPlatform":"win",
  "log":[
    {
      "message":"메시지 그룹이 생성되었습니다.",
      "createAt":"2018-10-05T07:25:02.493Z"
    },
    {
      "message":"메시지 그룹이 삭제되었습니다.",
      "createAt":"2018-10-05T07:25:02.493Z"
    }
  ],
  "status":"DELETED",
  "scheduledDate":null,
  "dateSent":null, // 발송 요청 시각
  "dateCompleted":null, // 그룹 발송이 완료된 시각
  "isRefunded":false, // 환급 여부
  "flagUpdated":false,
  "accountId":"12925149",
  "apiVersion":"4",
  "groupId":"G4V20181005162502HEA0ZB9AQOUMSE1",
  "price":{ // 그룹에 사용된 국가별 가격
// 82: { sms: 10, ... }, ...
  },
  "dateCreated":"2018-10-05T07:25:02.496Z",
  "dateUpdated":"2018-10-05T07:25:02.496Z",
  "_id":"G4V20181005162502HEA0ZB9AQOUMSE1"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ValidationError",
    "errorMessage": "유효하지 않은 groupId"
}

{
    "errorCode": "NotOperationalStatus",
    "errorMessage": "PENDING 상태의 그룹만 삭제할 수 있습니다. 현재 상태는 {status} 입니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "Forbidde",
    "errorMessage": "해당계정의 그룹만 삭제 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ResourceNotFound",
    "errorMessage": "요청하신 Resource를 찾을수 없습니다."
}

{
    "errorCode": "ResourceNotFound",
    "errorMessage": "해당 메시지 그룹을 찾을 수 없습니다."
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
curl -X DELETE https://api.solapi.com/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

## 예제 코드

[\[JavaScript\] delete\_group.js](https://github.com/solapi/examples/blob/master/javascript/delete_group.js)

[\[Python\] delete\_group.py](https://github.com/solapi/examples/blob/master/python/group/)

[\[Java\] delete\_group.java](https://github.com/solapi/examples/tree/master/java)

[\[PHP\] delete\_group.php](https://github.com/solapi/examples/blob/master/php/delete_group.php)

[\[Ruby\] delete\_group.rb](https://github.com/solapi/examples/blob/master/ruby/delete_group.rb)



