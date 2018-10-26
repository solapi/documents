# 그룹 메시지 예약 접수

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/schedule" %}
{% api-method-summary %}
scheduleGroupMessage
{% endapi-method-summary %}

{% api-method-description %}
그룹 메시지를 예약 접수 합니다.  
최대 6개월까지 접수 가능하며 **발송시**에 **잔액이 차감**되니 주의 부탁드립니다.  
\(**발송 시점에 잔액이 없을 경우 발송 실패\)**
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

{% api-method-body-parameters %}
{% api-method-parameter name="scheduledDate" type="string" required=true %}
ISO 8601 형식의 발송될 시각
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
    errorCode: "BlockedApp",
    errorMessage: "차단 처리된 앱으로 사용이 불가능합니다."
}

{
    errorCode: "InDevelopment",
    errorMessage: "개발단계의 앱으로 아직 출시되지 않았습니다."
}

{
    errorCode: "InvalidScheduledDate",
    errorMessage: "예약시간은 현재시간보다 늦게 설정 가능합니다."
}

{
    errorCode: "InvalidScheduledDate",
    errorMessage: "발송 예정일이 6개월을 초과하여 발송 예약에 실패하였습니다."
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

[\[JavaScript\] add\_scheduledDate.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/add_scheduledDate.js)

[\[Python\] add\_scheduledDate.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] add\_scheduledDate.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] add\_scheduledDate.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/add_scheduledDate.php)

[\[Ruby\] add\_scheduledDate.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/add_scheduledDate.rb)

