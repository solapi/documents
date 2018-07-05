# 심플 메시지

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/send" %}
{% api-method-summary %}
심플 메시지 발송
{% endapi-method-summary %}

{% api-method-description %}
여러 건을 한 번에 발송 요청할 수 있는 그룹 메시지와 다르게 한 건의 메시지만 발송이 가능합니다.  
  
HTTP Status Code 가 200 이어도 Response 의 `statusCode` 값이 2000 이 아닌 경우 문제가 있는 것으로  
Message Status Codes 에서 상세한 설명을 참고하세요.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="message" type="object" required=true %}
메시지 정보를 담은 객체
{% endapi-method-parameter %}

{% api-method-parameter name="-to" type="string" required=true %}
수신 번호
{% endapi-method-parameter %}

{% api-method-parameter name="-from" type="string" required=true %}
발신 번호
{% endapi-method-parameter %}

{% api-method-parameter name="-text" type="string" required=true %}
메시지 내용
{% endapi-method-parameter %}

{% api-method-parameter name="-type" type="string" required=false %}
메시지 타입  
SMS, LMS, MMS, CTA, ATA
{% endapi-method-parameter %}

{% api-method-parameter name="-country" type="string" required=false %}
국가 번호  
한국 \(82\)
{% endapi-method-parameter %}

{% api-method-parameter name="-subject" type="string" required=false %}
LMS, MMS 일 때 제목
{% endapi-method-parameter %}

{% api-method-parameter name="-imageId" type="string" required=false %}
MMS 일 때 이미지 아이디
{% endapi-method-parameter %}

{% api-method-parameter name="-kakaoOptions" type="object" required=false %}
CTA, ATA 일 때 사용
{% endapi-method-parameter %}

{% api-method-parameter name="--senderKey" type="string" required=false %}
센더키
{% endapi-method-parameter %}

{% api-method-parameter name="--templateCode" type="string" required=false %}
템플릿 코드
{% endapi-method-parameter %}

{% api-method-parameter name="--buttonName" type="string" required=false %}
버튼 이름 10 자 제한
{% endapi-method-parameter %}

{% api-method-parameter name="--buttonUrl" type="string" required=false %}
버튼 주소 100 자 제한
{% endapi-method-parameter %}

{% api-method-parameter name="--disableSms" type="boolean" required=false %}
친구톡 및 알림톡 발송이 실패했을 경우  
대체 문자를 발송안할 경우 true
{% endapi-method-parameter %}

{% api-method-parameter name="-customFields" type="object" required=false %}
사용자 정의 필드
{% endapi-method-parameter %}

{% api-method-parameter name="-agent" type="object" required=false %}
앱의 정보를 담은 객체
{% endapi-method-parameter %}

{% api-method-parameter name="--appId" type="string" required=false %}
앱 아이디
{% endapi-method-parameter %}

{% api-method-parameter name="--appVersion" type="string" required=false %}
앱 버전
{% endapi-method-parameter %}

{% api-method-parameter name="--osPlatform" type="string" required=false %}
사용하는 OS 플랫폼
{% endapi-method-parameter %}

{% api-method-parameter name="--sdkVersion" type="string" required=false %}
사용하는 SDK 버
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "groupId": String,
    "messageId": String,
    "statusCode": String,
    "statusMessage": String,
    "to": String,
    "type": String,
    "from": String,
    "customFields": Object
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "ValidationError",
    "errorMessage": "상황에 따라 다릅니다."
}


{
    "errorCode": "InvalidStatusCode",
    "errorMessage": "{messageId} 의 statusCode({statusCode})"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=402 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "errorCode": "NotEnoughBalance",
    "errorMessage": "보유 잔액이 부족합니다."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

