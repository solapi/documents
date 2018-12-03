# 문서 업로드

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/senderid/v1/documents" %}
{% api-method-summary %}
문서 업로드
{% endapi-method-summary %}

{% api-method-description %}
인증,  발신번호 개수 증가, 중복해제 요청을 위한 문서를 업로드 합니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
인증정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="file" type="string" required=true %}
업로드할 파일 base64 endcoding 된 문자열  
\(pdf, jpg, gif, png, tif 지원\)
{% endapi-method-parameter %}

{% api-method-parameter name="category" type="string" required=true %}
발신번호 증빙자료용\('SENDERID-APPROVAL'\) 혹은 개수 증가 요청용\('SENDERID-LIMITATION'\) 중 하나 선택
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
파일 이름
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "name": "Zb6bg3BkKDeVxCa.pdf",
  "url": "https://coolsms-sender-id-test.s3.ap-northeast-2.amazonaws.com/temp/Zb6bg3BkKDeVxCa.pdf",
  "originalName": "Zb6bg3BkKDeVxCa.pdf",
  "accountId": "12925149",
  "documentId": "DOC20181120163020FEZZTZL1G5BXJO1",
  "dateCreated": "2018-11-20T07:30:20.367Z",
  "category": "SENDERID_APPROVAL",
  "use": false
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "InvalidFileType",
    "errorMessage": "'png', 'gif', 'jpg', 'jpeg', 'pdf', 'tif', 'tiff'형식의 파일만 지원가능 합니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=413 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "FileSizeTooLarge",
    "errorMessage": "파일 크기는 700KB를 넘을 수 없습니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



