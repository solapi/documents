# 그룹 메시지 삭제

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/messages" %}
{% api-method-summary %}
deleteGroupMessages
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
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="messageIds" type="array" required=true %}
메시지 아이디를 담은 배열입니다.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  groupId: 'G4V20180307105937H3PTASXMNJG2JIB',
  errorCount: 0,
  resultList: [{
    messageId: 'M4V20200308120044DTYYJBBYLPQZIB1',
    resultCode: 'Success'
  }]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "ResourceNotFound",
    errorMessage: "그룹 아이디를 다시 확인해주세요."
}

{
    errorCode: "InvalidGroupStatus",
    errorMessage: "처리가 가능한 그룹이 아닙니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 예제 코드

[\[JavaScript\] delete\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/delete_group_messages.js)

[\[Python\] delete\_group\_message.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] delete\_group\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] delete\_group\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/delete_group_messages.php)

[\[Ruby\] delete\_group\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/delete_group_messages.rb)

