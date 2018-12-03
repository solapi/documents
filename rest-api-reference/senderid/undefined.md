# 발신번호 생성

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/numbers" %}
{% api-method-summary %}
발신번호 생성
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="phoneNumber" type="string" required=true %}
생성할 발신번호
{% endapi-method-parameter %}

{% api-method-parameter name="documents" type="array" required=false %}
발신번호 인증을 위한 증빙자료 문서 아이디
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
      "status": "PENDING",
      "expireAt": null,
      "method": null,
      "dateCreated": "2018-11-20T05:25:27.285Z",
      "dateUpdated": "2018-11-20T05:25:27.285Z",
      "log": [
        {
          "createAt": "2018-11-20T05:25:27.755Z",
          "message": "발신번호를 생성하였습니다."
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
    "errorCode": "InvalidPhoneNumber",
    "errorMessage": "전화번호가 유효하지 않습니다."
},
{
    "errorCode": "InvalidDocumentId",
    "errorMessage": "등록된 문서 정보를 찾을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



