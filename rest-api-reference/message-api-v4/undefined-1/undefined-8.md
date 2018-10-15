# 그룹 메시지 예약 취소

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/schedule" %}
{% api-method-summary %}
cancelScheduledGroupMessage
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
그룹 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    createAt: "2018-10-15T06:45:33.353Z",
    message: "메시지 예약이 성공적으로 취소됐습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "InvalidStatus",
    errorMessage: "'SCHEDULED' 상태의 그룹만 취소가 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "ResourceNotFound",
    errorMessage: "해당 그룹아이디가 존재하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 예제 코드

[\[JavaScript\] cancel\_scheduledDate.js](https://github.com/coolsms/coolsms-v4-examples/javascript/cancel_scheduledDate.js)

[\[Python\] cancel\_scheduledDate.py](https://github.com/coolsms/coolsms-v4-examples/python/cancel_scheduledDate.py)

[\[Java\] cancel\_scheduledDate.java](https://github.com/coolsms/coolsms-v4-examples/java/cancel_scheduledDate.java)

[\[PHP\] cancel\_scheduledDate.php](https://github.com/coolsms/coolsms-v4-examples/php/cancel_scheduledDate.php)

[\[Ruby\] cancel\_scheduledDate.rb](https://github.com/coolsms/coolsms-v4-examples/ruby/cancel_scheduledDate.rb)

