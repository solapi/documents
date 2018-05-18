# 시작하기

## 준비

Node.js 용 Coolsms SDK 를 사용하여 문자메시지, 카카오톡, 푸시메시지를 손쉽게 발송 할 수 있습니다. 발송 전에 회원가입을 비롯하여 몇 가지 선행해야 할 작업이 있습니다.

> [서비스 계정 생성](https://www.coolsms.co.kr/index.php?mid=frontpage&act=dispMemberSignUpForm) &gt; [발신번호 등록](https://www.coolsms.co.kr/index.php?mid=service_setup&act=dispSmsconfigSenderNumbers) &gt; [API Key 생성](https://www.coolsms.co.kr/index.php?mid=service_setup&act=dispSmsconfigCredentials)

**서비스 계정 생성**

쿨에스엠에스 사이트에서 회원가입을 통해 서비스 계정을 생성합니다. 서비스 약관에 동의하는 것으로 서비스 사용계약 및 신청서를 대체할 수 있습니다. 회원가입을 마쳤으면 테스트 용도로 300원이 자동충전 됩니다.

**발신번호 등록**

2015년 10월 16일부터는 관련 법\(발신번호 사전등록제\)으로 인해 발신번호로 미리 등록 후 사용해야 합니다. 발신번호 설정 에서 발신번호를 미리 등록해 두세요.

**API Key 생성**

API Key 관리 페이지에서 API Key를 생성합니다. 자동으로 생성된 API Key, API Secret 을 예제 실행할 때 사용합니다. API Secret은 외부에 노출되지 않도록 주의하세요.

## 설치

NPM 을 사용할 경우 install 명령을 통해 Project 에 간단히 설치 할 수 있습니다.

```bash
npm install coolsms-sdk --save
```

Github 를 통해 내려받을 수도 있습니다.

```bash
git clone https://github.com/coolsms/coolsms-sdk-js.git
```

## 발송

준비과정에서 발급받은 API Key, API Secret 및 발신번호\(sender's phone number\) 를 예제에서 사용하세요. 등록된 발신번호 외에는 사용이 불가합니다.

수신받을 전화번호를 recipient 에 입력하고 발송하려는 메시지를 text 에 입력하세요.

```javascript
// example.js

const coolsms = require('coolsms-sdk')

coolsms.setCredential({
  apiKey: '--- Input API Key ---',
  apiSecret: '--- Input API Secret ---'
})

coolsms.sendSimpleMessages(
  {
    messages: [
      {
        "to": {
          "recipient": "--- Input recipient's phone number ---"
        },
        "from": "--- Input sender's phone number ---",
        "text": "--- Input text to send ---",
      }
    ]
  },
  (error, result) => {
    if (error) {
      return console.log(error)
    }
    console.log(result)
  }
)
```

입력을 마쳤으면 node 를 실행하여 실제 메시지를 발송합니다.

```bash
node example.js
```

발송된 메시지는 메시지의 길이에 따라 SMS 혹은 LMS 가격이 적용되어 차감되며 실패 건에 대해서는 바로 재충전됩니다.

## 예제

아래 클릭시 Github 로 연결됩니다.

* [그룹메시지](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/groupMessage)
* [심플메시지](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/simpleMessage)
* [카카오톡](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/kakaoTalk)
* [이미지 업로드](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/images)
* [메시지로그](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/messageLog)
* [예약메시지 관리](https://github.com/coolsms/coolsms-sdk-js/tree/master/examples/scheduledMessage)
* [잔액조회](https://github.com/coolsms/coolsms-sdk-js/blob/master/examples/getBalance.js)

## 이슈

문제 발견 및 건의사항은 [Github 이슈](https://github.com/coolsms/coolsms-sdk-js/issues/new) 로 남겨주세요.

## 라이선스

Coolsms SDK for Javascript 의 소스 코드는 MIT License 를 따릅니다.

