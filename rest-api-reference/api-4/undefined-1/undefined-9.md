# 그룹 메시지 삭제

## 그룹 메시지 삭제

그룹에 추가된 문자메시지를 삭제합니다.

## Request

{% tabs %}
{% tab title="URI" %}
DELETE [https://api.solapi.com/messages/v4/groups/{groupId}/messages](https://api.solapi.com/messages/v4/groups/{groupId}/messages)
{% endtab %}

{% tab title="Sample" %}
curl -X DELETE [https://api.solapi.com/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages](https://api.solapi.com/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"  -d '{"messageIds":\["M4V20180308120044DTYYJBBYLPQZIB1", "M4V20180309120044DTYYJBBYLPQZIB1"\]}'
{% endtab %}
{% endtabs %}

#### Required Path Parameters

* `groupId` - 삭제할 메시지가 있는 그룹의 아이디

#### Required Body Parameters

* `messageIds` - 배열 형태인 삭제할 메시지의 아이디들

## Response

{% tabs %}
{% tab title="Syntax" %}
{ "errorCount": Number, "resultList": \[ { "messageId": "String", "resultCode": "String" } \] }
{% endtab %}

{% tab title="Sample" %}
{ "errorCount": 0, "resultList": \[ { "messageId": "MID1234567890", "resultCode": "Success" } \] }
{% endtab %}
{% endtabs %}

* `errorCount` - 오류 카운트
* `resultList` - 요청한 건수만큼 결과를 반환합니다. 
  * `messageId` - 삭제하려는 메시지의 아이디
  * `resultCode` - 삭제 성공 여부 \(Success, MessageNotFound, InternalError\)

## Errors

* `Unauthorized(401)` - 권한 오류

