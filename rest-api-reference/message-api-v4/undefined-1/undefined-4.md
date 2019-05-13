# 그룹 메시지 추가

{% api-method method="put" host="https://rest.coolsms.co.kr" path="/messages/v4/groups/:groupId/messages" %}
{% api-method-summary %}
addGroupMessages
{% endapi-method-summary %}

{% api-method-description %}
여러 건의 메시지를 발송하기 위한 그룹에 메시지를 추가합니다.  
실패된 건들도 그룹에 저장이 되나, 발송은 하지 않습니다.  
메시지 추가 실패 시 사유는 상태코드표를 확인 부탁드립니다.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="groupId" type="string" required=true %}
추가를 원하는 그룹 아이디
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
쿨에스엠에스 인증 정보
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="messages" type="array" required=true %}
message 객체를 담고 있는 array 형식으로 입력합니다.  
  
message 객체는 아래를 참고하세요.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCount: 0,
    resultList: [{
       to: '01000000001',
       from: '029302266',
       type: 'SMS',
       statusMessage: '정상 접수(이통사로 접수 예정) ',
       country: '82',
       messageId: 'M4V20181008113012XDVBONQ3TDLO2LM',
       statusCode: '2000',
       accountId: '12925149'
    }]
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "ValidationError"
    errorMessage: "messages 의 데이터 타입은 배열이어야 됩니다."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=413 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    errorCode: "RecipientsTooMany",
    errorMessage: "한 번에 추가할 수 있는 수신번호는 최대 10000건 입니다."
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
        &#xD544;&#xC694;&#xD55C; &#xAC12; &#xC785;&#xB2C8;&#xB2E4;. &#xC544;&#xB798;&#xC758;
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

## 제한 사항

그룹메시지 추가 API에 다음 3가지 제한사항이 있습니다.

* 요청의 총 데이터 크기는 15MB를 넘을 수 없습니다.
* 한번의 요청\(Request\)에 대해 수신번호는 10,000 개를 넘을 수 없습니다.
* 하나의 그룹에 담을 수 있는 메시지는 1,000,000 개 입니다.

## 상태코드

[확인 하기](../../message-status-codes.md#undefined)

## 예제 코드

[\[JavaScript\] add\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/javascript/add_group_message.js)

[\[Python\] add\_group\_message.js](https://github.com/coolsms/coolsms-v4-examples/blob/master/python/group/)

[\[Java\] add\_group\_message.java](https://github.com/coolsms/coolsms-v4-examples/tree/master/java)

[\[PHP\] add\_group\_message.php](https://github.com/coolsms/coolsms-v4-examples/blob/master/php/add_group_message.php)

[\[Ruby\] add\_group\_message.rb](https://github.com/coolsms/coolsms-v4-examples/blob/master/ruby/add_group_message.rb)

