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
      <td style="text-align:left">[required] &#xC218;&#xC2E0; &#xBC1B;&#xB294; &#xBC88;&#xD638;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">from</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[required] &#xD574;&#xB2F9; &#xACC4;&#xC815;&#xC5D0; &#xB4F1;&#xB85D;&#xB41C;
        &#xBC1C;&#xC2E0; &#xBC88;&#xD638; &#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">text</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[required] &#xBA54;&#xC2DC;&#xC9C0;&#xC758; &#xB0B4;&#xC6A9;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] SMS, LMS, MMS, ATA, CTA &#xC911; &#xD55C; &#xAC00;&#xC9C0;&#xB97C;
        &#xC785;&#xB825;&#xD558;&#xC2DC;&#xBA74; &#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">country</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] &#xAE30;&#xBCF8;&#xC73C;&#xB85C; &#xC124;&#xC815;&#xB418;&#xB294;
        &#xAC12;&#xC740; <code>82</code> &#xC774;&#xBA70;, &#xBC1C;&#xC1A1;&#xD558;&#xC2E4;
        &#xAD6D;&#xAC00;&#xC5D0; &#xB9DE;&#xAC8C; &#xC785;&#xB825;&#xD558;&#xC2DC;&#xBA74;
        &#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">subject</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] <code>LMS</code>,<code>MMS</code> &#xB85C; &#xBC1C;&#xC1A1;&#xD558;&#xAC8C;
        &#xB418;&#xB294; &#xACBD;&#xC6B0; &#xD544;&#xC218;&#xB85C; &#xC785;&#xB825;&#xB418;&#xB294;
        &#xC81C;&#xBAA9;&#xC785;&#xB2C8;&#xB2E4;.</td>
    </tr>
    <tr>
      <td style="text-align:left">imageId</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] <code>MMS</code> &#xC77C; &#xB54C;, &#xCCA8;&#xBD80;&#xB418;&#xB294;
        &#xC774;&#xBBF8;&#xC9C0;&#xC758; &#xACE0;&#xC720; &#xBC88;&#xD638;&#xC774;&#xBA70;,
        Image API &#xB97C; &#xCC38;&#xACE0; &#xD574;&#xC8FC;&#xC138;&#xC694;.</td>
    </tr>
    <tr>
      <td style="text-align:left">kakaoOptions</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">[optional] <code>ATA</code>, <code>CTA</code> &#xC77C; &#xB54C;, &#xC785;&#xB825;&#xC774;
        &#xD544;&#xC694;&#xD55C; &#xAC12; &#xC785;&#xB2C8;&#xB2E4;. &#xD558;&#xB2E8;&#xC758;
        &#xC124;&#xBA85;&#xC744; &#xCC38;&#xACE0;&#xD574;&#xC8FC;&#xC138;&#xC694;.</td>
    </tr>
    <tr>
      <td style="text-align:left">customFields</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">
        <p>[optional] &#xD68C;&#xC6D0;&#xB2D8;&#xC758; &#xBA54;&#xBAA8; &#xC6A9;&#xB3C4;&#xB85C;
          &#xC0AC;&#xC6A9;&#xD558;&#xC2E4; &#xAC1D;&#xCCB4;&#xC785;&#xB2C8;&#xB2E4;.</p>
        <p>&#xD544;&#xB4DC; &#xBA85;&#xC740; 30 &#xC790;, &#xAC12;&#xC740; 100</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">autoTypeDetect</td>
      <td style="text-align:left">Boolean</td>
      <td style="text-align:left">[optional] &#xAE30;&#xBCF8; &#xAC12;&#xC740; <code>false</code> &#xC774;&#xBA70;, <code>true</code> &#xB97C;
        &#xD558;&#xAC8C; &#xB418;&#xBA74; &#xC785;&#xB825;&#xAC12;&#xC5D0; &#xB9DE;&#xB294;
        &#xC801;&#xC808;&#xD55C; <code>type</code> &#xC774; &#xC124;&#xC815;&#xB429;&#xB2C8;&#xB2E4;.</td>
    </tr>
  </tbody>
</table>### kakaoOptions

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
      <td style="text-align:left">appId</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>[optional] &#xCFE8;&#xC5D0;&#xC2A4;&#xC5E0;&#xC5D0;&#xC2A4; &#xC571;&#xC2A4;&#xD1A0;&#xC5B4;&#xC5D0;
          &#xC571;&#xC774; &#xB4F1;&#xB85D;&#xB418;&#xC5B4; &#xC788;&#xB294; &#xACBD;&#xC6B0;,</p>
        <p>&#xD574;&#xB2F9; &#xC571;&#xC758; &#xC544;&#xC774;&#xB514;&#xB97C; &#xC774;&#xC6A9;&#xD558;&#xC5EC;
          &#xBC1C;&#xC1A1; &#xC2DC; &#xC218;&#xC775;&#xC744; &#xACF5;&#xC720; &#xBC1B;&#xC2B5;&#xB2C8;&#xB2E4;.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">osPlatform</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] &#xBC1C;&#xC1A1; &#xC6B4;&#xC601;&#xCCB4;&#xC81C; &#xD658;&#xACBD;</td>
    </tr>
    <tr>
      <td style="text-align:left">sdkVersion</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">[optional] SDK&#xB97C; &#xC774;&#xC6A9;&#xD558;&#xC5EC; &#xBC1C;&#xC1A1;&#xD558;
        &#xACBD;&#xC6B0;, &#xD574;&#xB2F9; SDK&#xC758; &#xC815;&#xBCF4; &#xBC0F;
        &#xBC84;&#xC804;</td>
    </tr>
  </tbody>
</table>### 예제 코드

[\[JavaScript\] send\_simple\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/send_simple_message.js)

[\[Python\] send\_simple\_message.py](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/simple/simple_message.py)

[\[Java\] send\_simple\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] send\_simple\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/send_simple_message.php)

[\[Ruby\] send\_simple\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/send_simple_message.rb)

