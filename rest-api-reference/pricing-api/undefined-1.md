# 해외 단가 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/pricing/v1/messaging/countries" %}
{% api-method-summary %}
해외 단가 조회
{% endapi-method-summary %}

{% api-method-description %}
각 나라별 메시지 타입에 따른 단가를 조회합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="contryId" type="string" required=false %}
조회를 원하는 국가코드
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
설정된 값만큼를 건너띄어 내역을 가져옵니다.  
\(default: 0\)
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" %}
가져오는 내역의 수를 설정된 값 만큼 제한 합니다.  
\(default: 20\)
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
        "sms": 20,
        "lms": 50,
        "mms": 200,
        "ata": 19,
        "cta": 13,
        "countryName": "Korea, South",
        "countryId": "82"
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
    "errorCode": "InvalidCountryId",
    "errorMessage": "유효하지 않은 'countryId' 값입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

