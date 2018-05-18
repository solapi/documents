# 메시지로그 조회

발송 요청된 메시지 로그를 조회합니다. 접수만 되고 발송 요청되지 않은 메시지는 로그로 남지 않으므로 조회 대상이 아닙니다. 레코드 정렬은 메시지 생성시각\(dateCreated\) 기준 내림차순으로 최근의 메시지가 먼저 조회됩니다.

## Resource URL

`https://solapi.com/MessageLog/3/getSentMessages`

## Request Syntax

```text
{
  "begin": "Date",
  "end": "Date",
  "offset": Number,
  "limit": Number,
  "condition": {
    "include": {
      "groupId": "String",
      "messageId": "String",
      "to": "String",
      "from": "String",
      "type": "String",
      "networkCode": "String",
      "statusCode": "String",
      "appId": "String"
    },
      "exclude": {
      "groupId": "String",
      "messageId": "String",
      "to": "String",
      "from": "String",
      "type": "String",
      "networkCode": "String",
      "statusCode": "String",
      "appId": "String"
    }
  }
}
```

## Request Sample

test

## Required Parameters

필수 입력 사항이 없습니다.

## Optional Parameters

begin

* 조회 시작 일시를 입력합니다. 기본값은 오늘날짜의 0시 0분 0초입니다.

end

* 조회 끝 일시를 입력합니다. 기본값은 오늘날짜의 현재 시각입니다.

condition

* 조건을 주어 원하는 레코드들만 조회 할 수 있습니다.
* include
  * 서브 파라메터의 입력값에 해당되는 레코드들만 리턴합니다. 두 개 이상 입력시 AND 연산으로 처리합니다.
* exclude
  * 서브 파라메터의 입력값을 제외한 나머지 레코드들만 리턴합니다. 두 개 이상 입력시 AND 연산으로 처리합니다.

## Response Syntax

```text
{
  "totalCount": Number,
  "offset": Number,
  "limit": Number,
  "messageList": {
    "messageId": {
      "groupId": "String",
      "to": "String",
      "from": "String",
      "text": "String",
      "type": "String",
      "country": "String",
      "subject": "String",
      "imageId": "String",
      "scheduledDate": "String",
      "kakaoOptions": {
        "senderKey": "String",
        "templateCode": "String",
        "buttonName": "String",
        "buttonUrl": "String"
      },
      "customFields": {
        "myCustomField": {Map} | [Array] | "String" | Number /* 사용자 정의 필드  */
      },
      "dateCreated": "Date",
      "statusCode": "String",
      "dateReceived": "Date",
      "networkCode": "String",
      "networkName": "String"
},
    ...
  }
}
```

## Response Sample

```javascript
test
```

messageList

* Map 형식의 조회된 메시지 목록
* subject
  * type이 LMS, MMS 일 때 제목
* customFields
  * 사용자정의 필드를 개수 제한없이 총 160 자까지 입력할 수 있습니다. 요청에 대한 응답에 그대로 리턴되며 발송 이후 메시지로그에서도 조회 가능합니다.
* dateCreated
  * 생성된 시각
* dateReceived
  * 단말기로 수신된 날짜와 시각
* networkName
  * 이동통신사 이름

