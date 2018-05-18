## 그룹메시지 발송
그룹메시지를 발송을 요청합니다. Response의 리턴값은 발송이 아니라 요청에 대한 성공여부를 뜻합니다.

### Resource URL
`https://solapi.com/GroupMessage/3/group/{groupId}/sendMessages`

### Request Syntax

```syntax
{
  //입력 사항이 없습니다. 
}
```

### Request Sample

{% codetabs name="CURL", type="curl" -%}
test
{%- language name="JavaScript", type="js" -%}

{%- language name="Python", type="py" -%}

{%- language name="PHP", type="php" -%}

{%- endcodetabs %}


### Requird Parameters
필수 입력 사항이 없습니다.

### Optional Parameters
선택 입력 사항이 없습니다.

### Response Syntax

```syntax
{
  "resultCode": "String"
}
```

### Response Sample

```json
{
  resultCode: "Success"
}
```
## resultCode
  - 아래 코드 중 하나가 리턴됩니다.
    - `Success`
      - 성공
    - `InternalError`
      - 내부 서부 오류로 인해 정상처리 되지 않았습니다.

{% include "../fragments/errors.md" %}

ResourceNotFound
  - 존재하지 않는 그룹,
  - 이미 TTL 시간이 만료되었거나 올바르지 않은 그룹아이디를 입력
  - HTTP Status Code: 404

NotEnoughBalance
  - 잔액이 없습니다.
  - HTTP Status Code: 402

NothingToSend
  - 보낼 메시지가 없습니다.
  - HTTP Status Code: 404

