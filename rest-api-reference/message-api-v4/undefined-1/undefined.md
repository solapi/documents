# 그룹 생성

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/groups" %}
{% api-method-summary %}
createMessageGroup
{% endapi-method-summary %}

{% api-method-description %}
메시지 대량 발송을 위한 그룹 생성 API 입니다.  
메시지 그룹은 메시지를 담는 그릇이 됩니다.  
  
한 건의 요청으로 하나의 메시지를 보낼 수 있는 심플 메시지와는 달리 그룹을 사용한다면,  
한 번의 요청으로 많은 메시지를 보낼 수 있습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="osPlatform" type="string" required=false %}
발송 운영체제 환경
{% endapi-method-parameter %}

{% api-method-parameter name="sdkVersion" type="string" required=false %}
SDK를 이용하여 발송하는 경우, 해당 SDK의 정보 및 버전
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
    }
  ],
  "status":"PENDING",
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
유효하지 않은 앱 아이디
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidAppId",
    "errorMessage": "유효하지 않은 앱 아이디"
}

{
    "errorCode": "BlockedApp",
    "errorMessage": "차단 처리된 앱으로 사용이 불가능합니다."
}

{
    "errorCode": "InDevelopment",
    "errorMessage": "개발단계의 앱으로 아직 출시되지 않았습니다."
}

{
    "errorCode": "InvalidAppId",
    "errorMessage": "유효하지 않은 AppId"
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
curl -X POST https://rest.coolsms.co.kr/messages/v4/groups
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

## 예제 코드

[\[Javascript\] create\_group.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/create_group.js)

[\[Python\] create\_group.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] create\_group.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] create\_group.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/create_group.php)

[\[Ruby\] create\_group.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/create_group.rb)

