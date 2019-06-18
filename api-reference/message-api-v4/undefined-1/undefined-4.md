# 그룹 메시지 추가

{% api-method method="put" host="https://api.solapi.com" path="/messages/v4/groups/:groupId/messages" %}
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
message 객체를 담고 있는 array 형식으로 입력합니다.message 객체는 아래를 참고하세요.
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


| kakaoOptions | Object | \[optional\] `ATA`, `CTA` 일 때, 입력이 필요한 값 입니다. 아래의 설명을 참고해주세요. |
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
</table>| Key | Type | Value |
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

[\[JavaScript\] add\_group\_message.js](https://github.com/solapi/examples/blob/master/javascript/add_group_message.js)

[\[Python\] add\_group\_message.js](https://github.com/solapi/examples/blob/master/python/group/)

[\[Java\] add\_group\_message.java](https://github.com/solapi/examples/tree/master/java)

[\[PHP\] add\_group\_message.php](https://github.com/solapi/examples/blob/master/php/add_group_message.php)

[\[Ruby\] add\_group\_message.rb](https://github.com/solapi/examples/blob/master/ruby/add_group_message.rb)

