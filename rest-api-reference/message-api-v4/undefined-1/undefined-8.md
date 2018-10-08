# 그룹 메시지 예약 취소

예약된 그룹 메시지를 예약 취소 합니다.

취소 처리된 그룹은 '대기중\(PENDING\)'상태로 돌아가게 되며, 기존 그룹과 마찬가지로 '수정', '삭제', '발송' 등이 가능합니다.

## Request

{% tabs %}
{% tab title="URI" %}
DELETE [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule](https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule)
{% endtab %}

{% tab title="Sample" %}
curl -X DELETE [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule](https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule) --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]" 
{% endtab %}
{% endtabs %}

### Required query parameters

* `groupId` - 예약 접수할 그룹 아이디.

### Response status code

* `200` - 그룹 예약 접수가 성공적으로 완료된 경우 입니다.

## Errors

`ResourceNotFound(404)` - 그룹 아이디가 존재하지 않는 경우

`InvalidStatus(400)` - 'SCHEDULED' 상태의 그룹만 예약 가능

`InternalError(500)` - 서버에 일시적으로 처리량이 많아 지연되는 경우

## 예제 코드

[\[JavaScript\] cancel\_scheduledDate.js](https://github.com/coolsms/coolsms-v4-examples/javascript/cancel_scheduledDate.js)

[\[Python\] cancel\_scheduledDate.py](https://github.com/coolsms/coolsms-v4-examples/python/cancel_scheduledDate.py)

[\[Java\] cancel\_scheduledDate.java](https://github.com/coolsms/coolsms-v4-examples/java/cancel_scheduledDate.java)

[\[PHP\] cancel\_scheduledDate.php](https://github.com/coolsms/coolsms-v4-examples/php/cancel_scheduledDate.php)

[\[Ruby\] cancel\_scheduledDate.rb](https://github.com/coolsms/coolsms-v4-examples/ruby/cancel_scheduledDate.rb)

