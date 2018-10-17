# 그룹 정보

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

### Group Status

* `PENDING` - 대기중 \(그룹 전송 준비\)
* `SENDING` - 전송 요청됨
* `COMPLETE` - 처리 완료
* `FAILED` - 생성 실패
* `DELETED` - 삭제됨
* `SCHEDULED` - 발송 예약 됨 \(예약 취소전까지 그룹 삭제 불가\)

## Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X GET https://rest.coolsms.co.kr/messages/v4/groups/G4V20180307105937H3PTASXMNJG2JIO
  --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

## 예제 코드

[\[JavaScript\] get\_group\_info.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/get_group_info.js)

[\[Python\] get\_group\_info.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] get\_group\_info.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] get\_group\_info.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/get_group_info.php)

[\[Ruby\] get\_group\_info.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/get_group_info.rb)

