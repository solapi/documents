# 그룹 메시지 발송

그룹에 정상적으로 추가된 메시지들을 발송할 때 사용합니다.

## Request

{% tabs %}
{% tab title="URI" %}
POST `https://api.solapi.com/messages/v4/groups/{groupId}/send`
{% endtab %}

{% tab title="Sample" %}
$ curl -X POST https://api.solapi.com/messages/v4/groups/{groupId}/send  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATRUE\]"
{% endtab %}
{% endtabs %}

### Required path parameters

* `groupId` - 그룹 생성시에 발급받은 그룹 아이디입니다.

### Response status code

* `200` - 메시지 발송 접수가 성공적으로 완료된 경우입니다.

## Errors

* `ValidationError(400)`- 요청시에 보낸 값이 잘못된 경우입니다.
* `InvalidStatus(400)`- 해당 그룹의 status 가 PENDING 이 아닌 경우입니다.
* `DeletedGroup(400)`- 해당 그룹이 삭제된 경우입니.
* `FailedGroup(400)`- 해당 그룹이 생성시에 실패된 경우입니다.
* `ScheduledGroup(400)`- 해당 그룹이 발송 대기상태인 경우입니다.
* `AlreadySent(400)`- 해당 그룹이 이미 발송 처리가 된 경우입니다..
* `InactiveApp(400)`- 해당 앱이 사용 불가능한 상태인 경우입니다.
* `NotEnoughBalance(402)`- 보유 잔액이 메시지 발송 금액보다 적은 경우입니다
* `ResourceNotFound(404)`- 자신의 그룹이 아니거나 그룹 아이디가 존재하지 않습니다.
* `MessagesInProcessing(409)`- 해당 그룹이 이미 발송 처리가 된 경우입니다.
* `InternalError(500)` - 일시적으로 처리량이 많아 처리되지 못한경우 출력입니다.

