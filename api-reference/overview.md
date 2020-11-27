# Overview

솔라피의 REST API Reference 내용을 담고 있습니다.

_참고_ REST는 Representational State Transfer의 약자로 API 연동 규격을 명확하게 정의되고 쉽게 구현 할 수 있습니다. [https://ko.wikipedia.org/wiki/REST](https://ko.wikipedia.org/wiki/REST)

쿨에스엠에스 SMS REST API 서버로 Request를 보내기 위해서 인증을 거쳐야 합니다.  
[API Key 를 이용한 방법](../authentication/api-key.md)과 소셜로그인으로 불리우는 [OAuth 2.0](../authentication/oauth2-3/oauth2.md) 을 지원하고 있습니다.

## Resource URL 구성

`https://api.solapi.com/<ServiceName>/<Version>/<ResourcePath>`

`<ServiceName>`

* [메시지](messages/)
* [잔액](https://github.com/solapi/documents/tree/62adac8b2800927921e6dafd5d6f95441e784571/api-reference/cash/README.md)
* [이미지](images/)

`<Version>`

* 서비스 버전

`<ResourcePath>`

* 필요시 특정 리소스 경로를 나타냅니다

## API 요청

API Request 시 파라메터 값과 Response 의 데이터 값은 JSON 형식으로 합니다. 모든 Request 에 Content-type 을 application/json 으로 설정하여 주세요.

## Operator

Operator\(이하 오퍼레이터\)는 SOLAPI에서 제공하는 고급 기능으로써 특정 정보를 검색하고자 URL Query Parameter를 사용할 때 자세하고 질 높은 Query를 작성할 수 있도록 도와줍니다. 또한 API를 통해 SOLAPI 서비스를 이용하고자 할 경우 숙지해야 될 기능입니다.

### 오퍼레이터의 종류와 예시

#### 종류

오퍼레이터는 `eq`, `ne`, `like`, `gte`, `lte`, `gt`, `lt` 총 7가지 종류가 있습니다.

| 이름 | 설명 |
| :---: | :--- |
|  | 어떤 오퍼레이터도 사용하지 않았다면 eq를 사용했을 때와 같은 일을 수행합니다. |
| eq | **Eqaul**의 약자입니다. 값과 동일한 대상을 찾을 때 사용됩니다. |
| ne | **Not Eqaul**의 약자입니다. 값과 동일하지 않은 대상을 찾을 때 사용됩니다. |
| like | 값을 포함하는 대상을 찾을 때 사용됩니다. |
| gte | 값을 포함하거나 높은 대상을 찾을 때 사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| lte | 값을 포함하거나 낮은 대상을 찾을  사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| gt | 값보다 높은 대상을 찾을  사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| lt | 값보다 낮은 대상을 찾을  사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| in | 값과 동일한 대상 여러개를 찾을 때 사용됩니다. |

{% hint style="danger" %}
eq 오퍼레이터가 사용 불가능 하다면 아무 오퍼레이터를 쓰지 않는 것도 불가능합니다.
{% endhint %}

#### 예시

```text
https://api.solapi.com/getList?title[like]=걸리버&title[ne]=걸리버여행기&author=스위프트&dateCreated[gte]=2017-06-24&dateCreated[lt]=2017-07-12&dateUpdated[gt]=2018-02-19&dateUpdated[lte]=2018-03-20&
```

위의 내용을 요약하자면 아래와 같습니다.

| URL & Query | Operator | 설명 |
| :--- | :---: | :--- |
| [https://api.solapi.com/getList](https://api.solapi.com/getList) |  | 특정 목록을 불러온다 |
| title\[like\]=걸리버 | like | 'title'은 '걸리버'를 포함한다 |
| title\[ne\]=걸리버여행기 | ne | 'title'은 '걸리버여행기'가 아니다 |
| author=스위프트 | eq | 'author'는 '스위프트'이다. |
| dateCreated\[gte\]=2017-06-24 | gte | 'dateCreated'는 2017년 6월 24일 이후 \(당일 포함\) |
| dateCreated\[lt\]=2017-07-12 | lt | 'dateCreated'는 2017년 7월 12일 이전 \(당일 미포함\) |
| dateUpdated\[gt\]=2018-02-19 | gt | 'dateUpdated'는 2018년 2월 19일 이후 \(당일 미포함\) |
| dateUpdated\[lte\]=2018-03-20 | lte | 'dateUpdated'는 2018년 3월 20일 이전 \(당일 포함\) |
| type\[in\]=\["SMS", "LMS"\] | in | 'type'이 SMS 혹은 LMS인 경우 |

## 오류 핸들링

Response 의 HTTP Status Code 값이 200 일 때 API 는 정상적으로 호출되었고 Response 의 Body 에 적절한 데이터가 리턴됩니다.

HTTP Status Code 200 이외의 값의 경우 오류로써 보통의 경우 errorCode 와 errorMessage 이 함께 리턴됩니다. 각 API 마다 정의된 오류코드는 다르지만 공통적으로 리턴될 수 있는 코드는 [Message Status Codes](message-status-codes.md) 를 참고하세요.

