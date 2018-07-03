# 단가 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/pricing/v1/messaging" %}
{% api-method-summary %}
단가 조회
{% endapi-method-summary %}

{% api-method-description %}
쿨에스엠에스에서 설정해둔 region을 바탕으로 메시지 단가를 조회합니다.  
  
\(현재는 '82' 한국으로 고정되어 었습니다.\)
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "sms": 20,
  "lms": 50,
  "mms": 200,
  "ata": 19,
  "cta": 13,
  "countryName": "Korea, South",
  "countryId": "82"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

