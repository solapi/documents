# 메시지 로그

발송처리된 메시지의 목록을 조회합니다. 예약으로 접수된 메시지는 [예약메시지 관리](scheduled-message.md) 에서 확인할 수 있습니다.

```javascript
'use strict'

const coolsms = require('cooosms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const params = {
  begin: '2017-03-18 00:00:00',
  end: '2017-03-19 23:59:59'
}

coolsms.getSentMessages(
  params,
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

