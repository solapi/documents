# 충전/차감 내역 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/balance/history" %}
{% api-method-summary %}
충전/차감 내역 조회
{% endapi-method-summary %}

{% api-method-description %}
잔액의 충전/차감 내역을 조회할 수 있습니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="offset" type="number" required=false %}
설정된 값만큼를 건너띄어 내역을 가져옵니다.  
\(default: 0\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
가져오는 내역의 수를 설정된 값 만큼 제한 합니다.  
\(default: 20\)
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=false %}
해당 날짜 이후의 내역만 가져옵니다.  
\(type: ISO8601\)
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=false %}
해당 날짜 이전의 내역만 가져옵니다.  
\(type: ISO8601\)
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" %}
'RECHARGE', 'DEDUCT', 'SET'로 구분되며 순서대로   
'충전',  '차감', '초기화'를 뜻합니다.
{% endapi-method-parameter %}

{% api-method-parameter name="groupId" type="string" %}
해당 그룹아이디에 연결된 내역들을 가져옵니다.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
[
    {
        "accountId": "129251492",
        "beforeBalance": 0,
        "afterBalance": 100,
        "amount": 100,
        "type": "RECHARGE", // 충전(RECHARGE), 차감(DEDUCT), 초기화(SET)
        "dateCreated": "2018-03-01T09:00:00.000Z"
    },
    ...
]
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidAccountId",
    "errorMessage": "accountId 가 유효하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

