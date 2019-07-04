# Operator

### Operator?

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
| gte | 값을 포함하거나 높은 대상을 찾을 떄 사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| lte | 값을 포함하거나 낮은 대상을 찾을 떄 사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| gt | 값보다 높은 대상을 찾을 떄 사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |
| lt | 값보다 낮은 대상을 찾을 떄 사용됩니다. 대부분은 날짜를 검색할 때 사용됩니다. |

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
| https://api.solapi.com/getList |  | 특정 목록을 불러온다 |
| title\[like\]=걸리버 | like | 'title'은 '걸리버'를 포함한다 |
| title\[ne\]=걸리버여행기 | ne | 'title'은 '걸리버여행기'가 아니다 |
| author=스위프트 | eq | 'author'는 '스위프트'이다. |
| dateCreated\[gte\]=2017-06-24 | gte | 'dateCreated'는 2017년 6월 24일 이후 \(당일 포함\) |
| dateCreated\[lt\]=2017-07-12 | lt | 'dateCreated'는 2017년 7월 12일 이전 \(당일 미포함\) |
| dateUpdated\[gt\]=2018-02-19 | gt | 'dateUpdated'는 2018년 2월 19일 이후 \(당일 미포함\) |
| dateUpdated\[lte\]=2018-03-20 | lte | 'dateUpdated'는 2018년 3월 20일 이전 \(당일 포함\) |

