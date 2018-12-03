# 발신번호 업데이트

{% api-method method="put" host="https://rest.coolsms.co.kr" path="/senderid/v1/numbers/{phoneNumber}" %}
{% api-method-summary %}
발신번호 업데이트
{% endapi-method-summary %}

{% api-method-description %}
발신번호 상태를 'ACTIVE'에서 'INACTIVE' 혹은 'INACTIVE' 에서 'ACTIVE'로 변경합니다..
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
{% api-method-parameter name="status" type="string" required=true %}
발신번호 상태 값 'ACTIVE', 'INACTIVE'만 가능합니다.
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
        "duplicateId": null,
        "reason": null,
        "reasonForRequested": null,
        "name": null,
        "status": null,
        "dateCreated": null,
        "dateUpdated": null
      },
      "status": "INACTIVE",
      "expireAt": null,
      "method": "ARS",
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "발신번호 상태를 'INACTIVE'로 변경하였습니다."
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
    "errorCode": "FailedToUpdate",
    "errorMessage": "등록된 발신번호의 상태가 'ACTIVE', 'INACTIVE'가 아닙니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



