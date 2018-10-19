# 그룹 메시지 발송

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/send" %}
{% api-method-summary %}
그룹 메시지 발송
{% endapi-method-summary %}

{% api-method-description %}
그룹에 담겨져 있는 메시지 발송 요청합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
이미 만들어진 그룹의 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
발송 요청이 성공한 경우
{% endapi-method-response-example-description %}

```javascript
{
    _id: 'G4V20181019142110RCZZBOHIUJD4OUE',
    count: {
        total: 3,
        sentTotal: 0,
        sentFailed: 0,
        sentSuccess: 0,
        sentPending: 0,
        sentReplacement: 0,
        refund: 0,
        registeredFailed: 2,
        registeredSuccess: 1
    },
    countForCharge: {
        sms: {'82': 1},
        lms: {},
        mms: {},
        ata: {},
        cta: {}
    },
    balance: {
        requested: 0,
        replacement: 0,
        refund: 0,
        sum: 0
    },
    point: {
        requested: 20,
        replacement: 0,
        refund: 0,
        sum: 0
    },
    app: {
        profit: {
            sms: 0, 
            lms: 0,
            mms: 0,
            ata: 0,
            cta: 0
        },
        appId: None,
        version: None
    },
    sdkVersion: None,
    osPlatform: None,
    log: [
        {
            message: '메시지 그룹이 생성되었습니다.',
            createAt: '2018-10-19T05:21:10.192Z'
        },
        {
            createAt: '2018-10-19T05:22:53.156Z',
            message: '국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.'
        }, 
        {
            createAt: '2018-10-19T05:25:06.930Z', 
            message: '메시지를 발송했습니다.', 
            oldBalance: 0, 
            newBalance: 0, 
            oldPoint: 21312241, 
            newPoint: 21312221, 
            totalPrice: 20
        }
    ], 
    status: 'SENDING', 
    scheduledDate: None, 
    dateSent: '2018-10-19T05:25:06.930Z', 
    dateCompleted: None, 
    isRefunded: False, 
    flagUpdated: False, 
    accountId: '12062181', 
    apiVersion: '4', 
    groupId: 'G4V20181019142110RCZZBOHIUJD4OUE', 
    price: {
        '82': {
            sms: 20, 
            lms: 50, 
            mms: 200, 
            ata: 19, 
            cta: 13, 
            dateCreated: '2018-10-18T23:59:22.967Z', 
            dateUpdated: '2018-10-18T23:59:22.967Z'
        }
    }, 
    dateCreated: '2018-10-19T05:21:10.205Z', 
    dateUpdated: '2018-10-19T05:25:06.931Z'
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
서버에서 거절하는 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "DeletedGroup",
    "errorMessage": "삭제 처리된 그룹으로는 발송이 안됩니다."
}

{
    "errorCode": "ValidationError",
    "errorMessage": "groupId 의 형식이 잘못 된 경우"
}

{
    "errorCode": "FailedGroup",
    "errorMessage": "그룹 생성에 실패했던 그룹입니다.\n그룹 로그를 확인해주세요."
}

{
    "errorCode": "InactiveApp",
    "errorMessage": "현재 사용하시는 앱의 상태가 비활성화 상태입니다."
}

{
    "errorCode": "InvalidStatus",
    "errorMessage": "'PENDING' 상태의 그룹만 전송 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=402 %}
{% api-method-response-example-description %}
발송을 위한 보유 액이 부족한 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "NotEnoughBalance",
    "errorMessage": "현재보유 잔액이 부족합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
자신이 보유한 그룹이 아닌 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ResourceNotFound",
    "errorMessage": "해당 그룹아이디가 존재하지 않습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}
이미 발송 요청한 그룹인 경우
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "GroupInProcessing",
    "errorMessage": "이미 발송 요청된 그룹입니다."
}

{
    "errorCode": "ScheduledGroup",
    "errorMessage": "발송 예약된 그룹이므로 발송이 불가능합니다."
}

{
    "errorCode": "AlreadySent",
    "errorMessage": "이미 발송이 완료된 그룹입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 예제 코드

[\[JavaScript\] send\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/send_group_message.js)

[\[Python\] send\_group\_message.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] send\_group\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] send\_group\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/send_group_message.php)

[\[Ruby\] send\_group\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/send_group_message.rb)

