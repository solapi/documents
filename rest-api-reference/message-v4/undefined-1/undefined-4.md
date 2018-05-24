# 그룹 메시지 추가

그룹에 발송할 메시지를 추가 합니다.

실패된 건들도 그룹에 저장이 되나, 발송은 하지 않습니다.

메시지 추가 실패시 사유는 상태코드표를 확인 부탁드립니다. [상태코드표 보기](https://docs.coolsms.co.kr/3.%20rest/messageStatusCode.html)

## Resource URL

`https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages`

## Request Syntax

{% tabs %}
{% tab title="URI" %}
POST`https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages`
{% endtab %}

{% tab title="Syntax" %}
```text
{
  "messages": [
    {
      "to": "String" or Array /* required */,
      "from": "String", /* required */
      "text": "String", /* required */
      "type": "String",
      "country": "String",
      "subject": "String",
      "imageId": "String",
      "kakaoOptions": {
        "senderKey": "String",
        "templateCode": "String",
        "buttonName": "String",
        "buttonUrl": "String",
        "disableSms": "Boolean"
      }
      "customFields": {
        ...
      }
    },
    ...
  ],
}
```
{% endtab %}

{% tab title="Sample" %}
$ curl -X POST https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATRUE\]"  -d '{ "messages": \[ { "to": "01000000000" or \[ "01000000000", "01000000001" \], "from": "029302266", "text": "테스트 메시지", "type":"sms", "customFields": { "myCustomField": "Value" } } \] }'
{% endtab %}
{% endtabs %}

### Required Parameters

* `messages` - Array 형식의 메시지 발송 정보
  * `to` - 수신번호 String이나 Array형식으로 받을 수 있으며 같은 문자내용으로 여러명에게 보낼때는 String형식으로 각각 다른 문자내용으로 보낼 때는 Array형식으로 보내는 것을 권장 합니다.
  * `from` - 발신번호
  * `text` - 메시지 내용, 완성형 한글 코드표에 나와있는 문자들만 지원하며 타입에 따라 제한길이가 다르며 한글은 2byte 띄어쓰기 및 줄내림은 1byte를 차지합니다.
    * SMS : 90byte 이하
    * LMS, MMS : 2000byte 이하
    * ATA, CTA: 한/영포함 1000자까지

### Optional Parameters

* `messages` - Array 형식의 메시지 발송 정보
  * `type` - 메시지 타입 기본은 'AUTO' \(타입이 'AUTO'일 경우 알아서 판단하여 들어간다.\)
  * `country` - 국가번호 기본은 '82'
  * `subject` - 타입이 LMS, MMS일 때 제목
  * `imageid` - 이미지 ID
  * `kakaoOptions` - 카카오톡 메시지 옵션
    * `senderKey` - 카카오톡 센더 키
    * `templateCode` - 템플릿 코드
    * `buttonName` - 버튼 이름, 10자 제한
    * `buttonUrl` - 버튼 URL, 100자 제한
    * `disableSms` - 'true'로 하면 알림톡 및 친구톡 발송이 실패하여도 문자메시지로 대체하여 발송하지 않습니다. 기본은 'false'
  * `customFilds` - 메시지 조회 시 사용할 수 있으며 필드명은 30자 설정값은 100자까지 가능합니다.

### Limits

그룹메시지 추가 API에 다음 3가지 제한사항이 있습니다.

* 요청의 총 데이터 크기는 15MB를 넘을 수 없습니다.
* 한번의 요청\(Request\)에 대해 수신번호는 10,000 개를 넘을 수 없습니다.
* 하나의 그룹에 담을 수 있는 메시지는 1,000,000 개 입니다.

## Response

{% tabs %}
{% tab title="Syntax" %}
```text
{
  "errorCount": Number,
  "resultList": [
    {
      "to": "String",
      "from": "String",     
      "type": "String",
      "statusCode": "String",
      "statusMessage": "String",
      "messageId": "String",
      "customFields": {
        ...
      },      
    }
  ],
}
```
{% endtab %}

{% tab title="Sample" %}
```javascript
{
    "errorCount": 0,
    "resultList": [
        {
            "to": "01000000001",
            "from": "029302266",
            "type": "SMS",            
            "statusCode": "2000",
            "statusMessage": "정상 접수(이통사로 접수 예정)"
            "messageId": "M3V20170911164820TCBLKDEWPAO8VOK",
            "customFields": {
              "myCustomField": "Value"
            }
        }
    ]
}
```
{% endtab %}
{% endtabs %}

## Errors

* `ValidationError(400)` - 정해진 형식에 맞게 Parameter를 입력 안할 시
* `InvalidAccountId(400)` - 해당 AccountId가 없음
* `InvalidUserId(400)` - 해당 유저 아이디가 없음
* `InternalError(500)` - 서버 오류
* `RecipientsTooMany(413)` -입력된 수신번호가 1000개를 넘음

