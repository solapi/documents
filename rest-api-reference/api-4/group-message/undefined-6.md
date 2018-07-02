# 그룹 메시지 발송

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/send" %}
{% api-method-summary %}
그룹 메시지 발송
{% endapi-method-summary %}

{% api-method-description %}
이미 만들어진 그룹을  발송 요청할 수 있는 API 입니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
이미 만들어진 그룹의 아이
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
발송 요청이 성공한 경우
{% endapi-method-response-example-description %}

```javascript
{
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
서버에서 거절하는 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "DeletedGroup",
    "errorMessage": "삭제 처리된 그룹으로는 발송이 안됩니다."
}

{
    "errorCode": "ValidationError",
    "errorMessage": "groupId 의 형식이 잘못 된 경우"
}

{
    "errorCode": "FailedGroup",
    "errorMessage": "그룹 생성에 실패했던 그룹입니다.\n그룹 로그를 확인해주세요."
}

{
    "errorCode": "InactiveApp",
    "errorMessage": "현재 사용하시는 앱의 상태가 비활성화 상태입니다."
}

{
    "errorCode": "InvalidStatus",
    "errorMessage": "'PENDING' 상태의 그룹만 전송 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=402 %}
{% api-method-response-example-description %}
발송을 위한 보유 액이 부족한 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "NotEnoughBalance",
    "errorMessage": "현재보유 잔액이 부족합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
자신이 보유한 그룹이 아닌 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ResourceNotFound",
    "errorMessage": "해당 그룹아이디가 존재하지 않습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
이미 발송 요청한 그룹인 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "GroupInProcessing",
    "errorMessage": "이미 발송 요청된 그룹입니다."
}

{
    "errorCode": "ScheduledGroup",
    "errorMessage": "발송 예약된 그룹이므로 발송이 불가능합니다."
}

{
    "errorCode": "AlreadySent",
    "errorMessage": "이미 발송이 완료된 그룹입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



