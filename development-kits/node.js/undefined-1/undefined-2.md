# 카카오톡

| Input Type | Result Type |
| --- | --- | --- |
| ATA | 알림톡 |
| CTA | 친구톡 |

## 알림톡

이미 등록된 템플릿에 발송 문구가 일치해야 정상적으로 발송됩니다.

{% code-tabs %}
{% code-tabs-item title="sendAlimTalk.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const params = {
  messages: [
    {
      "to": {
        "recipient": "01000000001"
      },
      "from": "0200000001",
      "text": "홍길동님 가입을 환영합니다.",
      "type": "ATA",
      "subject": "LMS 대체 발송시 제목",
      "kakaoOptions": {
        "senderKey": "--INPUT SENDER-KEY--",
        "templateCode": "--INPUT TEMPLATE-CODE--",        
        "disableSms": "false"
      }
    }
  ],
  options: {
    appVersion: 'JsExample v1.0'
  }
}

coolsms.sendSimpleMessages(
  params,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## 알림톡 버튼

알림톡 템플릿에 버튼을 함께 등록한 경우 하단 버튼이 출력되는 형식의 알림톡을 발송 할 수 있습니다.

{% code-tabs %}
{% code-tabs-item title="sendAlimTalkWithButton.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const params = {
  messages: [
    {
      "to": {
        "recipient": "01000000001"
      },
      "from": "0200000001",
      "text": "홍길동님 가입을 환영합니다.",
      "type": "ATA",
      "country": "82",
      "subject": "LMS 대체 발송시 제목",
      "kakaoOptions": {
        "senderKey": "--INPUT SENDER-KEY--",
        "templateCode": "--INPUT TEMPLATE-CODE--",   
        "buttonName": "프로필 보기",
        "buttonUrl": "https://example.com/profile?id=1234"
      }
    }
  ],
  options: {
    appVersion: 'JsExample v1.0'
  }
}

coolsms.sendSimpleMessages(
  params,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## 친구톡

플러스친구를 친구로 등록만 되어있다면 사전에 등록된 문구가 아니라 자유롭게 텍스트를 전송할 수 있습니다.

{% code-tabs %}
{% code-tabs-item title="sendChinguTalk.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const params = {
  messages: [
    {
      "to": {
        "recipient": "01000000001"
      },
      "from": "0200000001",
      "text": "카톡메시지 친구톡 테스트입니다.",
      "type": "CTA",
      "country": "82",
      "subject": "MMS 제목",
      "kakaoOptions": {
        "senderKey": "--INPUT SENDER-KEY--",
        "disableSms": "false"
      }
    }
  ],
  options: {
    appId: 'K00031',
    appVersion: 'JsExample 1.0'
  }
}

coolsms.sendSimpleMessages(
  params,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## 친구톡 버튼

자유로운 내용으로 하단 버튼 출력 형식의 친구톡을 발송 할 수 있습니다.

{% code-tabs %}
{% code-tabs-item title="sendChinguTalkWithButton.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const params = {
  messages: [
    {
      "to": {
        "recipient": "01000000001"
      },
      "from": "0200000001",
      "text": "(광고) 친구톡 이벤트 홍보",
      "type": "CTA",
      "country": "82",
      "subject": "LMS 대체 발송시 제목",
      "kakaoOptions": {
        "senderKey": "--INPUT SENDER-KEY--",
        "buttonName": "이벤트 상세히 보기",
        "buttonUrl": "https://example.com/event01"
      }
    }
  ],
  options: {
    appVersion: 'JsExample v1.0'
  }
}

coolsms.sendSimpleMessages(
  params,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

