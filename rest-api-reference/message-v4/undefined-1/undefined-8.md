# 그룹 메시지 예약 접수

그룹 메시지를 예약 접수 합니다.

최대 6개월까지 접수 가능하며 **발송시에 잔액이 차감되니 주의** 부탁드립니다.

**\(발송 시점에 잔액이 없을 경우 발송 실패 처리\)**

## Request

{% tabs %}
{% tab title="URI" %}
POST [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule](https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule)
{% endtab %}

{% tab title="Sample" %}
curl -X POST [https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule](https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/schedule) --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"  -d '{ "scheduledDate": "2019-01-01 00:00:00"}
{% endtab %}
{% endtabs %}

### Required query parameters

* `groupId` - 예약 접수할 그룹 아이디.

### Required body parameters

* `scheduledDate` - 예약 날짜,  최대 6개월까지 설정 가능합니다.

### Response status code

* `200` - 그룹 예약 접수가 성공적으로 완료된 경우 입니다.

## Errors

* `ValidationError(400)` - 정해진 형식에 맞게 Parameter를 입력 안할 시
* `ResourceNotFound(404)` - 그룹 아이디가 존재하지 않는 경우
* `MessagesInProcessing(409)` -이미 발송된 메시지
* `DeletedGroup(400)` -삭제 처리된 그룹
* `FailedGroup(400)` - 그룹 생성에 실패했던 그룹
* `ScheduledGroup(409)` - 이미 발송 예약된 그룹
* `InvalidStatus(400)` - 'PENDING' 상태의 그룹만 예약 가능
* `MessagesNotFound(404)` - 해당 그룹에 메시지가 없음
* `InvalidAppId(400)` - 유효하지 않은 앱 아이디
* `InactiveApp(400)` - 현재 사용하는 앱의 상태가 비활성화
* `InvalidScheduledDate(400)` - 잘못된 'scheduled
* `InternalError(500)` - 서버에 일시적으로 처리량이 많아 지연되는 경우



