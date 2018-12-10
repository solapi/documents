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
{% api-method-parameter name="messages" type="string" required=true %}
message 를 messages 배열에 넣고 stringify 한 값 입니다.  
e.g \) "\[message, message, message\]"  
  
message 객체는 하단을 참고해주세요.
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

### message 는 JSON Object 형식 입니다.

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
      <td style="text-align:left">[optional] <code>LMS</code>,<code>MMS</code> 로 발송하게 되는 경우 필수로 입력되는 제목입니다.</td>
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

