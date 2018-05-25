# 심플메시지

1,000건 이하의 소량의 문자메시지를 발송합니다. 대량의 문자메시지를 안정적으로 발송하려면 [그룹메시지](https://github.com/coolsms/documents/tree/7c909967934227b9d386a76b06c08bf448c91c98/sdk/nodejs/user-guide/group-message.md) 을 사용하세요.

## AUTO 타입

type 을 별도로 지정하지 않으면 기본은 AUTO 입니다. 메시지 길이 혹은 이미지 포함 여부에 따라 SMS, LMS, MMS 로 변환됩니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.sendSimpleMessages(
  {
    messages: [
      {
        "to": {
          "recipient": "01000000001"
        },
        "from": "0200000001",
        "text": "쿨에스엠에스 테스트 메시지",
      }
    ]
  },
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## LMS 보내기

최대 영어 2,000 자, 한글 1,000 자 발송 가능합니다. type 을 LMS 로 하면 text 내용이 짧아도 LMS 로 발송됩니다. 수신받은 단말기에서 subject 의 내용으로 메시지 목록에 출력되고 상세 페이지에 text 내용이 출력됩니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.sendSimpleMessages(
  {
    messages: [
      {
        "type": "LMS",
        "to": {
          "recipient": "01000000001"
        },
        "from": "0200000001",
        "subject": "LMS 제목",
        "text": "내용이 짧아도 LMS로 발송됩니다"
      }
    ]
  },
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## MMS 보내기

[이미지 업로드](image.md) 를 통해 미리 업로드 해둔 이미지의 ID 를 imageId 에 입력해 주어야 합니다.

수신받은 단말기에서 subject 의 내용으로 메시지 목록에 출력되고 상세 페이지에 text 내용과 이미지가 출력됩니다. 대부분은 위쪽에 이미지가 출력되고 아래로 텍스트가 출력되지만 출력 위치는 단말기에 따라 다를 수 있습니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.sendSimpleMessages(
  {
    messages: [
      {
        "type": "MMS",
        "to": {
          "recipient": "01000000001"
        },
        "from": "0200000001",
        "subject": "MMS 제목",
        "text": "이미지를 발송합니다",
        "imageId": "--INPUT IMAGE-ID--"
      }
    ]
  },
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## 메시지 예약

scheduledDate 에 "YYYY-MM-DD HH:MI:SS" 형식의 값을 입력하여 정해진 시간에 메시지가 발송하도록 합니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.sendSimpleMessages(
  {
    messages: [
      {
        "to": {
          "recipient": "01000000001"
        },
        "from": "0200000001",
        "text": "예약 메시지",
        "scheduledDate": "2017-04-10 11:40:00"
      }
    ]
  },
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

