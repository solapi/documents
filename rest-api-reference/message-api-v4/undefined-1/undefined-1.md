# 그룹 목록

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/messages/v4/groups" %}
{% api-method-summary %}
getMessageGroupList
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
그룹 검색 조건에 사용되는 key 의 값 입니다. \(e.g status, groupId\)  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="cond" type="string" required=false %}
그룹 검색 조건에 사용되는 연산자 입니다.  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="value" type="string" required=false %}
검색 값 입니다.  
자세한 사용 방법은 하단의 설명을 참고해주세요.
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
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
응답 값의 자세한 필드 정보는 '그룹 생성' 문서 참조
{% endapi-method-response-example-description %}

```javascript
{
  "offset": 0, // 그룹 목록 조회 시작점
  "limit": 20, // 최대 조회 그룹 수
  "groupList": {
    "G4V20180627175335EF3PIYNFRQAGNDO": {
      "_id": "G4V20180627175335EF3PIYNFRQAGNDO",
      "agent": {
        "appId": "TEST",
        "appVersion": "2.0",
        "sdkVersion": "1.0",
        "osPlatform": "win"
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
          "createAt": "2018-06-27T08:53:35.560Z"
        }
      ],
      "status": "PENDING",
      "scheduledDate": null,
      "accountId": "12925149",
      "apiVersion": "4",
      "groupId": "G4V20180627175335EF3PIYNFRQAGNDO",
      "dateCreated": "2018-06-27 17:53:35",
      "dateUpdated": "2018-06-27 17:53:35"
    }
  },
  "hasNext": 0 // 다음 데이터 존재 여부
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Body parameter 설명

### criteria

criteria 의 값은 "key1,key2,key3" 과 같이 ,\(콤마\) 로 구분되며 `cond`, `value` 와 함께 사용됩니다.

* `status` - 그룹의 상태 입니다.
* `groupId` - 그룹 아이디 입니다.
* `dateCreated` - 그룹 생성일 입니다.
* `dateUpdated` - 그룹 정보를 변경한 마지막 시각 입니다.
* `scheduledDate` - 발송이 시작 될 날 입니다.\(예약\)
* `count.total` - 총 문자메시지의 개수 입니다.
* `count.sentTotal` - 발송된 문자메시지의 개수 입니다.

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

criteria="groupId,status"

cond="eq,eq"

일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다.

e.g - value="그룹아이디,PENDING"

## Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X GET https://rest.coolsms.co.kr/messages/v4/groups --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}

## 예제 코드

[\[Javascript\] get\_group\_list.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/get_group_list.js)

[\[Python\] get\_group\_list.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] get\_group\_list.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] get\_group\_list.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/get_group_list.php)

[\[Ruby\] get\_group\_list.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/get_group_list.rb)

