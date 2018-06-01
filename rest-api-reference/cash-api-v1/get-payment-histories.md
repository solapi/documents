---
description: 등록된 결제 수단으로 결제된 목록을 조회합니다.
---

# 결제 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/cash/v1/payment" %}
{% api-method-summary %}
Get Payment Histories
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter type="string" name="paymentId" required=true %}
결제수단의 Id 입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="startAmount" type="number" %}
결제된 금액의 시작값 입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="endAmount" type="number" required=false %}
결제된 금액의 끝 값 입니다. 
{% endapi-method-parameter %}

{% api-method-parameter name="startDate" type="string" required=false %}
검색을 시작할 날짜 입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="endDate" type="string" required=false %}
검색을 마칠 날짜 입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
검색을 시작할 번호입니다.
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" %}
검색할 갯수 입니다.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



