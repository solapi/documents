# 그룹 메시지 예약 취소

{% api-method method="delete" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/schedule" %}
{% api-method-summary %}
cancelScheduledGroupMessage
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
그룹 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    _id: 'G4V20181019090749JPZH8HEYXURHFQ6', 
    count: {
        total: 1,
        sentTotal: 0,
        sentFailed: 0,
        sentSuccess: 0,
        sentPending: 0,
        sentReplacement: 0,
        refund: 0,
        registeredFailed: 0,
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
        requested: 0,
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
            createAt: '2018-10-19T00:07:49.822Z'
        },
        {
            createAt: '2018-10-19T00:08:02.671Z', 
            message: '국가코드(82)의 단문문자(SMS) 1 건이 추가되었습니다.'
        },
        {
            createAt: '2018-10-19T00:09:12.062Z',
            message: '메시지 예약이 성공적으로 접수됐습니다.',
            messageCount: {
                total: 1,
                sentTotal: 0,
                sentFailed: 0,
                sentSuccess: 0,
                sentPending: 0,
                sentReplacement: 0,
                refund: 0,
                registeredFailed: 0,
                registeredSuccess: 1
            }
        },
        {
            createAt: '2018-10-19T00:12:51.873Z',
            message: '메시지 예약이 성공적으로 취소됐습니다.'
        }
    ],
    status: 'PENDING',
    scheduledDate: None,
    dateSent: None,
    dateCompleted: None,
    isRefunded: False,
    flagUpdated: False,
    accountId: '12062181',
    apiVersion: '4',
    groupId: 'G4V20181019090749JPZH8HEYXURHFQ6',
    price: {},
    dateCreated: '2018-10-19T00:07:49.835Z',
    dateUpdated: '2018-10-19T00:14:20.301Z'
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "InvalidStatus",
    errorMessage: "'SCHEDULED' 상태의 그룹만 취소가 가능합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "ResourceNotFound",
    errorMessage: "해당 그룹아이디가 존재하지 않습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## 예제 코드

[\[JavaScript\] cancel\_scheduledDate.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/cancel_scheduledDate.js)

[\[Python\] cancel\_scheduledDate.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] cancel\_scheduledDate.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] cancel\_scheduledDate.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/cancel_scheduledDate.php)

[\[Ruby\] cancel\_scheduledDate.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/cancel_scheduledDate.rb)

