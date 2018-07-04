# 그룹 목록

메시지 그룹 목록 조회 API 사용방법을 기술합니다.  
이전에 삭제 되었거나, 생성 실패된 메시지 그룹 등을 포함한 생성되었던 모든 그룹 조회가 가능합니다.

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
쿨에스엠에스 인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="criteria" type="string" required=false %}
그룹 검색 기준 ,\(콤마\)로 구분하여 여러 검색 기준을 사용  
사용 가능 값 : groupId, status, dateCreated, dateUpdated,  scheduledDate
{% endapi-method-parameter %}

{% api-method-parameter name="cond" type="string" required=false %}
그룹 검색 조건에 사용되는 연산자 ,\(콤마\)로 구분하여 여러 조건 사용  
사용 가능 값: eq, ne, gt, gte, lt, lte
{% endapi-method-parameter %}

{% api-method-parameter name="value" type="string" required=false %}
검색 값 \(날짜 검색의 경우 ISO8601 표준을 이용합니다.\)
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

#### Search cond parameters 

* `eq` - 같음 \(=\)
* `ne` - 같지 않음 \(!=\)
* `gt` - 보다 큼 \(&gt;\)
* `gte` - 보다 크거나 같음 \(&gt;=\)
* `lt` - 보다 작음 \(&lt;\)
* `lte` - 보다 작거나 같음 \(&lt;=\)

### Request Sample

{% tabs %}
{% tab title="CURL" %}
```bash
curl -X GET https://rest.coolsms.co.kr/messages/v4/groups --header "Authorization : HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[UNIQID], Signature= [SIGNATURE]" \
```
{% endtab %}
{% endtabs %}
