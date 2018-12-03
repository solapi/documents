# 발신번호 중복 해제 요청

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/papers/duplicate/{phoneNumber}" %}
{% api-method-summary %}
중복 발신번호 해제 요청
{% endapi-method-summary %}

{% api-method-description %}
발신번호 상태가 'DUPLICATED'일 경우 중복 해제를 위한 요청입니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="phoneNumber" type="string" required=true %}
발신번호
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="reason" type="string" required=true %}
중복 해제 사유
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
담당자 명,  
없으면 유저정보에있는 닉네임이 들어가게 됩니다.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "accountId": "12925149",
  "dateCreated": "2018-11-20T05:25:27.757Z",
  "dateUpdated": "2018-11-20T05:25:27.757Z",
  "limit": 2,
  "limitationDocuments": [],
  "senderIds": [
    {
      "unlockDuplicate": {
        "duplicateId": "DUP20181120161327RIBHFBFB2X4BJJL",
        "reason": null,
        "reasonForRequested": "부서에 따른 아이디 할당을 위해 필요",
        "name": "홍길동",
        "status": "PENDING",
        "dateCreated": "2018-11-20T07:13:27.531Z",
        "dateUpdated": "2018-11-20T07:13:27.531Z"        
      },
      "status": "ACTIVE",
      "expireAt": null,
      "method": "ARS",
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "중복해제 요청을 하였습니다. 담당자명: 홍길동, 사유: 부서에 따른 아이디 할당을 위해 필요"
        }
      ],
      "approvalDocuments": [],
      "phoneNumber": "01000000000",
      "handleKey": "SED20181120142527G9MUYZKJXEV6ADY"
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidSenderId",
    "errorMessage": "등록된 발신번호 정보를 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=409 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "AlreadyApproved",
    "errorMessage": "이미 승인된 상태입니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



