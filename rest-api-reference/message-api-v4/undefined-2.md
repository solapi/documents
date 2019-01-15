# 메시지 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/messages/v4/list" %}
{% api-method-summary %}
getMessageList
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="criteria" type="string" required=false %}
메시지 검색 조건에 사용되는 key 의 값 입니다. \(e.g messageId, statusCode\)  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="cond" type="string" required=false %}
메시지 검색 조건에 사용되는 연산자 입니다.  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="value" type="string" required=false %}
검색 값 입니다.  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="startKey" type="number" required=false %}
데이터 조회 시작점
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
조회할 데이터 수
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  nextKey: 0,
  limit: 20,
  messageList: {
    M4V20180307110044DTYYJBBYLPQZIB1: {
      _id: 'M4V20180307110044DTYYJBBYLPQZIB1',
      kakaoOptions: [Object],
      type: null,
      country: '82',
      subject: null,
      imageId: null,
      dateProcessed: null,
      dateReported: null,
      dateReceived: null,
      statusCode: 'TEST1000',
      networkCode: null,
      log: [],
      replacement: false,
      autoTypeDetect: true,
      messageId: 'M4V20180307110044DTYYJBBYLPQZIB1',
      groupId: 'G4V20180307105937H3PTASXMNJG2JIO',
      accountId: '12925149',
      text: 'text',
      from: '01000000000',
      to: '01000000000',
      customFields: { },
      dateCreated: '2018-10-08T03:13:07.256Z',
      dateUpdated: '2018-10-08T03:13:07.256Z',
      reason: null,
      networkName: 'ETC'
    }
  },
  hasNext: 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "ValidationError",
    errorMessage: 상황마다 다른 메시지가 출력됩니다.
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "Forbidden",
    errorMessage: "잘못된 접근입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Body parameter 설명

### criteria

criteria 의 값은 "key1,key2,key3" 과 같이 ,\(콤마\) 로 구분되며 `cond`, `value` 와 함께 사용됩니다.

* `messageId` - 메시지 아이디 입니다.
* `groupId` - 그룹 아이디 입니다.
* `to` - 수신 번호 입니다.
* `from` - 발신 번호 입니다.
* `type` - 문자 메시지의 타입 입니다.  \(`SMS`, `LMS`, `MMS`, `ATA`, `CTA`\)
* `dateCreated` - 그룹 생성일 입니다.
* `dateUpdated` - 그룹 정보를 변경한 마지막 시각 입니다.
* `replacement` - 대체 발송 여부 입니다. \(`true`, `false`\)
* `statusCode` - 문자 메시지의 상태 코드 입니다.

### cond

criteria 와 같이 "cond1,cond2" 와 같이 ,\(콤마\)로 구분되며, `criteria`,`value` 와 함께 사용됩니다.

* `eq` - 같음 \(=\)
* `ne` - 같지 않음 \(!=\)
* `gt` - 보다 큼 \(&gt;\)
* `gte` - 보다 크거나 같음 \(&gt;=\)
* `lt` - 보다 작음 \(&lt;\)
* `lte` - 보다 작거나 같음 \(&lt;=\)

### value

`criteria` , `cond` 값에 대응하는 value 입니다.

criteria="messageId,statusCode"

cond="eq,eq"

일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다.

e.g - value="메시지아이디,2000"

## 예제 코드

[\[JavaScript\] get\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/get_group_message.js)

[\[Python\] get\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/tree/master/python/group)

[\[Java\] get\_group\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] get\_group\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/get_group_messages.php)

[\[Ruby\] get\_group\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/get_group_messages.rb)

