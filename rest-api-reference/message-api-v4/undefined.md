# 심플 메시지

{% api-method method="post" host="https://rest.coolsms.co.kr" path="/messages/v4/send" %}
{% api-method-summary %}
sendSimpleMessage
{% endapi-method-summary %}

{% api-method-description %}
여러 건을 한 번에 발송 요청할 수 있는 그룹 메시지와 다르게 한 건의 메시지만 발송이 가능합니다.  
  
HTTP Status Code 가 200 이어도 Response 의 `statusCode` 값이 2000 이 아닌 경우 문제가 있는 것으로  
Message Status Codes 에서 상세한 설명을 참고하세요.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="message" type="object" required=true %}
메시지 정보를 담은 객체  
하단의 설명을 참고해주세요.
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

## Body Parameters 설명

### message

<table>
  <thead>
    <tr>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">to</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[required] 수신 받는 번호입니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">from</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[required] 해당 계정에 등록된 발신 번호 입니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">text</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[required] 메시지의 내용입니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] SMS, LMS, MMS, ATA, CTA 중 한 가지를 입력하시면 됩니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">country</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] 기본으로 설정되는 값은 <code>82</code> 이며, 발송하실 국가에 맞게 입력하시면 됩니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">subject</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] <code>LMS</code>,<code>MMS</code> 로 발송하게 되는 경우 입력되는 제목입니다.</td>
    </tr>
    <tr>
      <td style="text-align:left">imageId</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] <code>MMS</code> 일 때, 첨부되는 이미지의 고유 번호이며, Image API 를 참고 해주세요.</td>
    </tr>
    <tr>
      <td style="text-align:left">kakaoOptions</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">[optional] <code>ATA</code>, <code>CTA</code> 일 때, 입력이 필요한 값 입니다. 하단의 설명을
        참고해주세요.</td>
    </tr>
    <tr>
      <td style="text-align:left">customFields</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>[optional] 회원님의 메모 용도로 사용하실 객체입니다.</p>
        <p>필드 명은 30 자, 값은 100</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">autoTypeDetect</td>
      <td style="text-align:left">Boolean</td>
      <td style="text-align:left">[optional] 기본 값은 <code>false</code> 이며, <code>true</code> 를 하게 되면 입력값에 맞는
        적절한 <code>type</code> 이 설정됩니다.</td>
    </tr>
  </tbody>
</table>### kakaoOptions

| Key | Type | Value |
| :--- | :--- | :--- |
| senderKey | String | \[required\] 센더키 입니다. |
| templateCode | String | \[optional\] 템플릿 코드입니다. |
| buttonName | String | \[optional\] 버튼 이름이며, 최대 10 자 입력 가능합니다. |
| buttonUrl | String | \[optional\] 버튼 URL 이며, 최대 100 자 입력 가능합니다. |
| disableSms | Boolean | \[optional\] `true` 로 설정해서 보내게 되면, 발송 실패시 문자 메시지를 대체 발송하지 않습니다. 기본값은 `false` 입니다. |

### 

### 예제 코드

[\[JavaScript\] send\_simple\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/send_simple_message.js)

[\[Python\] send\_simple\_message.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/simple/simple_message.py)

[\[Java\] send\_simple\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] send\_simple\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/send_simple_message.php)

[\[Ruby\] send\_simple\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/send_simple_message.rb)

