---
weight: 200
title: 잔액정보 가져오기
---

# 잔액정보

이 API는 Authentication Info를 제외한 Parameters가 필요 없습니다.

유저의 잔액정보를 가져옵니다.

### Request Parameters

필수 입력 파라메터가 없습니다.

### Response Parameters

```json
{
  "data": {
    "member_srl": "382492",
    "user_id": "testsy1",
    "cash": "0",
    "point": "98843",
  }
}
```
Parameter | Default | Description
--------- | ------- | -----------
member_srl| - | 사용자 번호(AccountId와 동일)
user_id   | - | 사용자 아이디
cash      | - | 남은 캐쉬
point     | - | 남은 포인트


### Error 처리
```json
{
  "errorMessage": "parameter is empty"
}
```
Http Status Code가 200일 경우 성공 아니라면 'errorMessage'값을 확인한다.


