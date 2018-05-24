# 그룹 메시지 발송

그룹에 정상적으로 추가된 메시지들을 발송할 때 사용합니다.

## Request

{% tabs %}
{% tab title="URI" %}
POST `https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/send`
{% endtab %}

{% tab title="Sample" %}
$ curl -X POST https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/send  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATRUE\]"
{% endtab %}
{% endtabs %}

### Required path parameters

* `groupId` - 그룹 생성시에 발급받은 그룹 아이디입니다.

### Response status code

* `200` - 메시지 발송 접수가 성공적으로 완료된 경우입니다.

## Errors

* `ValidationError(400)` - 요청시에 입력된 parameter 들이 정상적인 값이 아닐경우에 출력됩니다.
* `NotEnoughBalance(402)` - 보유하고 있는 포인트와 캐쉬를 합한 값이 발송시에 드는 금액보다 더 낮은 경우에 출력됩니다.
* `Forbidden(403)` - 자신의 그룹이 아닌경우 출력됩니다.
* `ResourceNotFound(404)` - 해당 그룹아이디가 존재하지 않는 경우 또는 해당 그룹에 메시지가 추가되지 않은 경우 출력됩니다.
* `InternalError(500)` - 일시적으로 처리량이 많아 처리되지 못한경우 출력입니다.

