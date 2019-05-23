# 그룹 메시지 목록

그룹에 추가된 문자메시지 목록을 조회합니다.

## Request

{% tabs %}
{% tab title="URI" %}
GET [https://api.solapi.com/messages/v4/groups/{groupId}/messages](https://api.solapi.com/messages/v4/groups/{groupId}/messages)
{% endtab %}

{% tab title="Sample" %}
curl -X GET [https://api.solapi.com/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages](https://api.solapi.com/messages/v4/groups/{G4V20180307105937H3PTASXMNJG2JIO}/messages)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"
{% endtab %}
{% endtabs %}

### Required Path Parameters

* `groupId` - 조회할 메시지가 있는 그룹의 아이디

### Optional Query Parameters

* `offset` - 가져올 레코드 시작 위치 \(default: 0\)
* `limit` - 가져올 레코드의 수 \(default: 20\)

## Response

{% tabs %}
{% tab title="Syntax" %}
{ "offset": Int, "limit": Int, "totalCount": Int, "messageList": { "String": { "kakaoOptions": { "senderKey": "String", "templateCode": "String", "buttonName": "String", "buttonUrl": "String", "disableSms": Boolean }, "type": "String", "customFields": Object, "country": "String", "subject": "String", "imageId": "String", "dateReceived": "String", "statusCode": "String", "networkCode": "String", "log": Array, "\_id": "String", "messageId": "String", "groupId": "String", "text": "String", "from": "String", "to": "String", "dateCreated": "String" } } ... }
{% endtab %}

{% tab title="Sample" %}
{ "offset": 0, "limit": 20, "totalCount": 1, "messageList": { "MESSAGE89012345678901234567890BB": { "kakaoOptions": { "senderKey": null, "templateCode": null, "buttonName": null, "buttonUrl": null, "disableSms": false }, "type": "AUTO", "customFields": null, "country": "82", "subject": null, "imageId": null, "dateReceived": null, "statusCode": null, "networkCode": null, "log": \[\], "\_id": "MESSAGE89012345678901234567890BB", "messageId": "MESSAGE89012345678901234567890BB", "groupId": "G4V20180307105937H3PTASXMNJG2JIO", "text": "text", "from": "01000000000", "to": "01000000000", "dateCreated": "2018-03-23T06:24:04.615Z" } } }
{% endtab %}
{% endtabs %}

* `offset` - 가져온 레코드 시작 위치
* `limit` - 가져온 레코드 수
* `totalCount` - 가져온 레코드 개수
* `messageList` - 가져온 메시지 정보
  * `messageId` - 메시지 아이디
    * `kakaoOptions` - 카카오톡 관련된 메시지 정보
      * `senderKey` - 카카오톡 센더키
      * `templateCode` - 알림톡의 경우 템플릿 코드
      * `buttonName` - 버튼의 이름
      * `buttonUrl` - 버튼의 링크
      * `disableSms` - 카카오톡 발송에 실패해도 SMS로 발송하지 않음
    * `type` - 메시지 타입
    * `customFields` - 사용자 정의 필드
    * `country` - 국가 코드
    * `subject` - 메시지 제목
    * `imageId` - 이미지의 아이디
    * `dateReceived` - 단말기로 수신된 일시
    * `statusCode` - 메시지 상태 코드
    * `networkCode` - 결과 코드
    * `log` - 메세지 로그
    * `_id` - 메시지 아이디
    * `messageId` - 메시지 아이디
    * `groupId` - 그룹 아이디
    * `text` - 메시지 내용
    * `from` - 발신번호
    * `to` - 수신번호
    * `dateCreated` - 생성일시

## Errors

* `Unauthorized(401)` - 권한 오류

