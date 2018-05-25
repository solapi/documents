# 그룹메시지

그룹메시지는 대량메시지 뿐만 아니라 소량의 메시지도 안전하게 발송할 수 있는 메커니즘을 제공합니다.

> 그룹생성 &gt; 메시지 추가 &gt; 메시지 확인 &gt; 발송

예로, 10,000 건의 메시지를 발송하는 과정에서 네트웍 오류 혹은 응용프로그램 내부 사정에 의한 오류로 발송 도중 멈추는 경우 어디까지 발송되었는지 확인 후 재발송 하는 등, 뒷처리 과정이 매우 복잡하게 됩니다.

그룹메시지는 발송 할 모든 메시지를 서버에 먼저 접수 후 리뷰 과정을 거쳐 발송하므로 결과를 미리 예측 할 수 있습니다.

## 그룹 생성

메시지를 담을 그룹을 생성합니다. 생성된 그룹은 24시 뒤에 자동 삭제됩니다.

{% code-tabs %}
{% code-tabs-item title="createGroup.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

coolsms.createGroup(
  { appVersion: 'JsExample v1' },
  (error, result) => {
    if (error) console.log(error)
    else console.log('Group ID:', result.groupId)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

생성된 그룹의 ID 를 기록해 두었다가 메시지 추가, 리뷰, 발송 할 때 사용합니다.

## 메시지 추가

{% code-tabs %}
{% code-tabs-item title="addMessages.js" %}
```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT API SECRET--'
})

const groupId = '--INPUT GROUP-ID--'
const messages = [
  {
    "to": {
      "recipient": "01000000001"
    },
    "from": "0200000001",
    "text": "메시지 내용"
  }
]

coolsms.addGroupMessages(
  groupId,
  messages,
  (error, result) => {
    if (error) console.log(error)
    else console.log('Result:', JSON.stringify(result, null, 2))
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## 그룹 정보 확인

그룹정보 API 를 호출하여 그룹의 정보와 지금까지 접수된 메시지 내역을 확인합니다.

{% tabs %}
{% tab title="Request" %}
{% code-tabs %}
{% code-tabs-item title="getGroupInfo.js" %}
```javascript
'use strict'

const coolsms = require('../..')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--iNPUT API SECRET--'
})

const groupId = '--INPUT GROUP-ID--'

coolsms.getGroupInfo(
  groupId,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endtab %}

{% tab title="Response" %}
```javascript
'use strict'

const coolsms = require('../..')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--iNPUT API SECRET--'
})

const groupId = '--INPUT GROUP-ID--'

coolsms.getGroupInfo(
  groupId,
  (error, result) => {
    if (error) console.log(error)
    else console.log(result)
  }
)
```
{% endtab %}
{% endtabs %}

```javascript
{
  groupId: 'G3V20170919153907PSHKLLP3LRQWGW2',
  groupOptions: { 
    appId: 'null',
    appVersion: 'JsExample v1.0.0',
    apiVersion: '3',
    forceSms: 'false',
    onlyAta: 'false',
    osPlatform: 'NodeJS',
    devLanguage: 'NodeJS',
    sdkVersion: 'JS'
  },
  count: {
    sms: 0,
    lms: 0,
    mms: 0,
    ata: 0,
    cta: 0,
    push: 0
  },
  price: { 
    unitPrice: {
      sms: 20,
      lms: 50,
      mms: 200,
      ata: 15,
      cta: 20,
      push: 5
    },
    calculatedPrice: {
      sms: 0,
      lms: 0,
      mms: 0,
      ata: 0,
      cta: 0,
      push: 0,
      total: 0
    }
  },
  ttl: 7080
}
```

getMessageList 를 사용해 접수된 메시지 내용을 읽어와서 비교해 볼 수도 있습니다.

## 발송

리뷰 후 문제가 없다면 발송합니다.

```javascript
'use strict'

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--INPUT API KEY--',
  apiSecret: '--INPUT SERCRET KEY--'
})

const groupId = '--INPUT GROUP-ID--'

coolsms.sendGroupMessages(
  groupId,
  (error, result) => {
    if (error) {
      console.log(error)
    } else {
      console.log(result)
    }
  }
)
```

한 번 발송한 그룹메시지는 재사용이 불가합니다.

