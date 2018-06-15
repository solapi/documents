# 메시지 조회

원하는 검색 조건으로 메시지를 조회합니다.

## Request

{% tabs %}
{% tab title="URI" %}
GET [https://rest.coolsms.co.kr/messages/v4/list](https://rest.coolsms.co.kr/messages/v4/list)
{% endtab %}

{% tab title="Sample" %}
curl -X GET [https://rest.coolsms.co.kr/messages/v4/list](https://rest.coolsms.co.kr/messages/v4/list)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"
{% endtab %}
{% endtabs %}

### Optional query parameters

* `groupId` - 그룹에 포함된 메시지를 조회하고 싶으시다면, 그룹 아이디를 조건으로 입력하시면 됩니다.
* `messageId` - 해당 메시지만 조회하고 싶으시다면, 메시지 아이디를 조건으로 입력하시면 됩니다.
* `startDate` - 조회하고 싶으신 기간의 시작 시각을 입력하시면 됩니다.
* `endDate` - 조회하고 싶으신 기간의 종료 시각을 입력하시면 됩니다.
* `from` - 조회하고 싶으신 발신번호를 입력하시면 됩니다.
* `to` - 조회하고 싶으신 수신번호를 입력하시면 됩니다.
* `type` - 조회하고 싶으신 메시지의 타입\(SMS, LMS, MMS, ATA, CTA, GCM, APN, PUSH, AUTO\)을 입력하시면 됩니다.
* `networkCode` - 조회하고 싶으신 수신받는 기기의 통신사코드를 입력하시면 됩니다.
* `statusCode` - 조회하고 싶으신 전송 상태값을 입력하시면 됩니다.
* `resultCode` - 조회하고 싶으신 전송 결과값을 입력하시면 됩니다.
* `offset` - 조회하고 싶으신 메시지의 시작 번호를 입력하시면 됩니다. \(0 &lt;= N\)
* `limit` - 조회하고 싶으신 메시지의 최대값을 입력하시면 됩니다. \(0 &lt; N &lt;= 500\)

## Response

{% tabs %}
{% tab title="Syntax" %}
```text
{
    [
        {
            "kakaoOptions": {
                "senderKey": "String",
                "templateCode": "String",
                "buttonName": "String",
                "buttonUrl": "String",
                "disableSms": "Boolean"
            },
            "type": String,
            "customFields": Object,
            "country": "String",
            "subject": "String",
            "imageId": "String",
            "dateReceived": "String",
            "statusCode": "String",
            "networkCode": "String",
            "log": Array,
            "messageId": "String",
            "groupId": "String",
            "text": "String",
            "from": "String",
            "to": "String",
            "dateCreated": "String"
        },
        {...}
    ]
}

```
{% endtab %}

{% tab title="Sample" %}
```text
{
    [
        {
            "kakaoOptions": {
                "senderKey": null,
                "templateCode": null,
                "buttonName": null,
                "buttonUrl": null,
                "disableSms": false
            },
            "type": "AUTO",
            "customFields": null,
            "country": "82",
            "subject": null,
            "imageId": null,
            "dateReceived": null, 
            "statusCode": "2000",
            "networkCode": "45005",
            "log": Array,
            "messageId": "M4V20180307110044DTYYJBBYLPQZIB1",
            "groupId": "G4V20180307105937H3PTASXMNJG2JI1",
            "text": "text",
            "from": "01000000000",
            "to": "01000000000",
            "dateCreated": "2018-03-23T00:37:25.305Z"
        },
        {...}
    ]
}
```
{% endtab %}
{% endtabs %}

* `kakaoOptions` - 카카오톡 메시지 옵션
  * `senderKey` - 알림톡 Sender Key
  * `templateCode` - 알림톡 Template Code
  * `buttonName` - 카카오톡 버튼 이름, 10 자 제한
  * `buttonUrl` - 카카오톡 버튼 URL, 100 자 제한
  * `disableSms` - 알림톡 및 친구톡 발송에 실패하여도 문자메시지로 대체하여 발송하지 않습니다.
* `type` - 메시지 타입
* `customFields` - 사용자 정의 필드
* `country` - 국가 코드
* `subject` - 메시지 제목
* `imageId` - 메시지에 첨부된 이미지아이디
* `dateReceived` - 수신자가 수신한 시각
* `statusCode` - 메시지 상태 코드
* `carrierCode` - 수신자의 통신사
* `log` - 메시지에 대한 로그
* `messageId` - 메시지 아이디
* `groupId` - 메시지 그룹 아이디
* `text` - 메시지 내용
* `to` - 수신번호
* `from` - 발신번호
* `dateCreated` - 메시지가 생성된 시각

## Errors

`ValidationError(400)` - 입력한 parameter 가 잘못된 경우

`Forbidden(403)` - 자신의 메시지아이디 또는 그룹아이디가 아닌데 조회하는 경우

`InternalError(500)` - 서버에 일시적으로 처리량이 많아 지연되는 경

