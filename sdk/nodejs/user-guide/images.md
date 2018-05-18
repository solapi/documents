# 이미지 관리

MMS 타입으로 이미지를 휴대전화로 발송 할 수 있습니다. 발송 전에 미리 이미지를 서버로 올려 준비를 마쳐야 합니다. 이미지 발송 예제는 심플메시지의 [MMS 보내기](simple-message.md#mms-보내기) 를 참고 하세요.

## 이미지 업로드

업로드된 이미지는 24시간 후 자동 삭제됩니다.

```js
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const imagePath = '--INPUT IMAGE-PATH--'

coolsms.uploadImage(
  imagePath,
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## 이미지 정보

```js
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const imageId = '--INPUT IMAGE-ID--'

coolsms.getImageInfo(
  imageId,
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## 이미지 목록

```js
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.getImageList(
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

## 이미지 삭제

```js
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const imagesToDelete = [
  {
    imageId: "--INPUT IMAGE-ID--"
  }
]

coolsms.deleteImages(
  imagesToDelete
  , function(error, result) {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```