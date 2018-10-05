# 그룹 메시지 추가

그룹에 발송할 메시지를 추가 합니다.

실패된 건들도 그룹에 저장이 되나, 발송은 하지 않습니다.

메시지 추가 실패시 사유는 상태코드표를 확인 부탁드립니다. [상태코드표 보기](https://docs.coolsms.co.kr/3.%20rest/messageStatusCode.html)

## 제한 사항

그룹메시지 추가 API에 다음 3가지 제한사항이 있습니다.

* 요청의 총 데이터 크기는 15MB를 넘을 수 없습니다.
* 한번의 요청\(Request\)에 대해 수신번호는 10,000 개를 넘을 수 없습니다.
* 하나의 그룹에 담을 수 있는 메시지는 1,000,000 개 입니다.

## Resource URL

`https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages`

## Request syntax

{% tabs %}
{% tab title="URI" %}
PUT`https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages`
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
      "autoTypeDetect": "Boolean",
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
curl -H "Content-Type: application/json” -H "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATRUE\]" -d '{ "messages": "\[ { \"to\": \"01000000000\", \"from\": \"029302266\", \"text\": \"테스트 메시지\", \"type\":\"sms\", \"customFields\": { \"myCustomField\": \"Value\" } } \]" }' -X PUT https://rest.coolsms.co.kr/messages/v4/groups/{groupId}/messages
{% endtab %}
{% endtabs %}

### Required parameter

* `messages` - Array 형식의 메시지 발송 정보 \(JSON Object 형식의 데이터를 문자열로 만든 값 입니다.e.g { "key": "value } -&gt; "{ \"key\": \"value\" }"\)
  * `to` - 수신번호 문자열 이나 배열  형식으로 보내실 수 있습니다.
  * `from` - 발신번호를 문자열 형식으로 입력하시면 됩니다.
  * `text` - 메시지 내용, 완성형 한글 코드표에 나와있는 문자들만 지원하며 타입에 따라 제한길이가 다르며 한글은 2byte 띄어쓰기 와 영어 및 줄내림은 1byte를 차지합니다.
    * SMS : 90byte 이하
    * LMS, MMS : 2000byte 이하
    * ATA, CTA: 한/영포함 1000자까지

### Optional parameter

* `messages` - Array 형식의 메시지 발송 정보 \(JSON Object 형식의 데이터를 문자열로 만든 값 e.g { "key": "value } -&gt; "{ \"key\": \"value\" }"\)
  * `type` - 발송하실 메시지의 타입 입니다. \(SMS, LMS, MMS, ATA, CTA\)
  * `autoTypeDetect` - true 또는 값을 넣지 않으셔도 됩니다.
    * `true`: type 값을 입력하지 않는 경우이며, 입력하신 값에 따라서 자동으로 SMS, LMS, MMS 또는 ATA, CTA 가 설정됩니다.
  * `country` - 국가번호 입니다. 대한민국은 '82' 입니다.
  * `subject` - `type` 이 `LMS`, `MMS`일 때 필수 입력이며, 문자메시지의 제목입니다.
  * `imageId` - `MMS` 일 때 필수 입력이며, 이미지 등록시에 발급받은 imageId 를 입력하시면 됩니다.
  * `kakaoOptions` - `type`이 `ATA`,`CTA` 일 때 필수 입니다.
    * `senderKey` - 카카오톡 센더 키 입니다.
    * `templateCode` - 템플릿 코드입 니다.
    * `buttonName` - 버튼 이름, 10자 제한입니다.
    * `buttonUrl` - 버튼 URL, 100자 제한입니다.
    * `disableSms` - `true`로 하면 알림톡 및 친구톡 발송이 실패하여도 문자메시지로 대체하여 발송하지 않습니다. 기본은 `false` 입니다.
  * `customFilds` - 메시지 조회 시 사용할 수 있으며 필드명은 30자 설정값은 100자까지 가능합니다.

## Response data

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

## 에러 코드

`ValidationError(400)` - 정해진 형식에 맞게 Parameter를 입력 안할 시

`InvalidAccountId(400)` - 해당 AccountId가 없음

`InvalidUserId(400)` - 해당 유저 아이디가 없음

`InternalError(500)` - 서버 오류

`RecipientsTooMany(413)` -입력된 수신번호가 1000개를 넘음

