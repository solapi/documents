# 발신번호 목록 조회

{% api-method method="get" host="https://rest.coolsms.co.kr" path="/senderid/v1/numbers" %}
{% api-method-summary %}
발신번호 목록 조회
{% endapi-method-summary %}

{% api-method-description %}
발신번호, 인증문서, 로그 등이 포함되어 있는 모든 정보를 리턴합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}
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
        "duplicateId": null,
        "reason": null,
        "reasonForRequested": null,
        "name": null,
        "status": null,
        "dateCreated": null,
        "dateUpdated": null
      },
      "status": "ACTIVE",
      "expireAt": null,
      "method": "ARS",
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "인증수단 'ARS'로 발신번호 인증이 완료되었습니다."
        }
      ],
      "approvalDocuments": [],
      "phoneNumber": "01000000000",
      "handleKey": "SED20181120142527G9MUYZKJXEV6ADY"
    },
    {
      "unlockDuplicate": {
        "reason": null,
        "reasonForRequested": null,
        "name": null,
        "status": null,
        "dateCreated": null,
        "dateUpdated": null
      },
      "status": "ACTIVE",
      "expireAt": null,
      "method": "ARS",
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "인증수단 'ARS'로 발신번호 인증이 완료되었습니다."
        }
      ],
      "approvalDocuments": [],
      "phoneNumber": "01000000001",
      "handleKey": "SED20181120142527G9MUYZKJXEV6AFY"
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
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



