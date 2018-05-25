# 예약메시지 관리

[심플메시지](simple-message.md) 혹은 [그룹메시지](https://github.com/coolsms/documents/tree/7c909967934227b9d386a76b06c08bf448c91c98/sdk/nodejs/user-guide/group-message.md)를 통해 예약한 메시지의 목록을 조회하고 취소 할 수 있습니다.

## 예약 목록

예약된 메시지 목록을 조회합니다. 이미 발송처리된 예약 메시지는 목록에 나타나지 않습니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.getScheduledMessages(
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## 예약 취소

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const messagesToCancel = [
  {
    messageId: '--INPUT MESSAGE-ID--'
  }
]

coolsms.cancelScheduledMessages(
  messagesToCancel,
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

