# 심플 메시지

{% api-method method="post" host="https://api.solapi.com" path="/messages/v4/send" %}
{% api-method-summary %}
sendSimpleMessage
{% endapi-method-summary %}

{% api-method-description %}
여러 건을 한 번에 발송 요청할 수 있는 그룹 메시지와 다르게 한 건의 메시지만 발송이 가능합니다.HTTP Status Code 가 200 이어도 Response 의 `statusCode` 값이 2000 이 아닌 경우 문제가 있는 것으로  
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

{% api-method-parameter name="agent" type="object" required=false %}
rappId, osPlatform, sdkVersion을 담을 수 있는 개체 하단의 설명을 참고해주세요.
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

| Key | Type | Value |
| :--- | :--- | :--- |


| to | String | \[required\] 수신 받는 번호입니다. |
| :--- | :--- | :--- |


| from | String | \[required\] 해당 계정에 등록된 발신 번호 입니다. |
| :--- | :--- | :--- |


| text | String | \[required\] 메시지의 내용입니다. |
| :--- | :--- | :--- |


| type | String | \[optional\] SMS, LMS, MMS, ATA, CTA 중 한 가지를 입력하시면 됩니다. |
| :--- | :--- | :--- |


| country | String | \[optional\] 기본으로 설정되는 값은 `82` 이며, 발송하실 국가에 맞게 입력하시면 됩니다. \* 현재 한국\(82\) 발송만 지원됩니다. |
| :--- | :--- | :--- |


| subject | String | \[optional\] `LMS`,`MMS` 로 발송하게 되는 경우 필수로 입력되는 제목입니다. |
| :--- | :--- | :--- |


| imageId | String | \[optional\] `MMS` 일 때, 첨부되는 이미지의 고유 번호이며, Image API 를 참고 해주세요. |
| :--- | :--- | :--- |


| kakaoOptions | Object | \[optional\] `ATA`, `CTA` 일 때, 입력이 필요한 값 입니다. 하단의 설명을 참고해주세요. |
| :--- | :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">customFields</th>
      <th style="text-align:left">Object</th>
      <th style="text-align:left">
        <p>[optional] &#xD68C;&#xC6D0;&#xB2D8;&#xC758; &#xBA54;&#xBAA8; &#xC6A9;&#xB3C4;&#xB85C;
          &#xC0AC;&#xC6A9;&#xD558;&#xC2E4; &#xAC1D;&#xCCB4;&#xC785;&#xB2C8;&#xB2E4;.</p>
        <p>&#xD544;&#xB4DC; &#xBA85;&#xC740; 30 &#xC790;, &#xAC12;&#xC740; 100</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>| autoTypeDetect | Boolean | \[optional\] 기본 값은 `false` 이며, `true` 를 하게 되면 입력값에 맞는 적절한 `type` 이 설정됩니다. |
| :--- | :--- | :--- |


| Key | Type | Value |
| :--- | :--- | :--- |
| pfId | String | \[required\] 플러스친구 연동 아이디 |
| templateId | String | \[optional\] 템플릿 아이디 \(알림톡 발송시 필수\) |
| buttons | Array | \[optional\] 아래 설명된 button 객체를 Array 형식에 담습니다. |
| disableSms | Boolean | \[optional\] `true` 로 설정해서 보내게 되면, 발송 실패시 문자 메시지를 대체 발송하지 않습니다. 기본값은 `false` 입니다. |

### button

| Key | Type | Value |
| :--- | :--- | :--- |
| buttonType | String | \[required\] DS:배송조회, WL:웹링크, AL:앱링크, BK:봇키워드 MD: 메시지전달 |
| buttonName | String | \[required\] 버튼 이름 |
| linkMo | String | \[optional\] 모바일 웹 링크 주소, WL 사용시 필수 |
| linkPc | String | \[optional\] PC 웹 링크 주소, WL 사용시 선택 |
| linkIos | String | \[optional\] Android 앱 링크 주소, AL 사용시 필수 |
| linkAnd | String | \[optional\] IOS 앱 링크 주소, AL 사용시 필수 |

### agent

| Key | Type | Value |
| :--- | :--- | :--- |


<table>
  <thead>
    <tr>
      <th style="text-align:left">appId</th>
      <th style="text-align:left">String</th>
      <th style="text-align:left">
        <p>[optional] &#xCFE8;&#xC5D0;&#xC2A4;&#xC5E0;&#xC5D0;&#xC2A4; &#xC571;&#xC2A4;&#xD1A0;&#xC5B4;&#xC5D0;
          &#xC571;&#xC774; &#xB4F1;&#xB85D;&#xB418;&#xC5B4; &#xC788;&#xB294; &#xACBD;&#xC6B0;,</p>
        <p>&#xD574;&#xB2F9; &#xC571;&#xC758; &#xC544;&#xC774;&#xB514;&#xB97C; &#xC774;&#xC6A9;&#xD558;&#xC5EC;
          &#xBC1C;&#xC1A1; &#xC2DC; &#xC218;&#xC775;&#xC744; &#xACF5;&#xC720; &#xBC1B;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>| osPlatform | String | \[optional\] 발송 운영체제 환경 |
| :--- | :--- | :--- |


| sdkVersion | String | \[optional\] SDK를 이용하여 발송하 경우, 해당 SDK의 정보 및 버전 |
| :--- | :--- | :--- |


[\[JavaScript\] send\_simple\_message.js](https://github.com/solapi/examples/blob/master/javascript/send_simple_message.js)

[\[Python\] send\_simple\_message.py](https://github.com/solapi/examples/blob/master/python/simple/simple_message.py)

[\[Java\] send\_simple\_message.java](https://github.com/solapi/examples/tree/master/java)

[\[PHP\] send\_simple\_message.php](https://github.com/solapi/examples/blob/master/php/send_simple_message.php)

[\[Ruby\] send\_simple\_message.rb](https://github.com/solapi/examples/blob/master/ruby/send_simple_message.rb)

