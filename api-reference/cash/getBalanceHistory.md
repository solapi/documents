# 잔액 변동내역 조회

## Request
```
GET https://api.solapi.com/cash/v1/balance/history
```

메시지 발송, 출금등으로 변동 된 잔액 내역을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `cash:read` | `role-cash:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| offset | `number` |  | eq | 검색 시작 지점 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| startDate | `string` |  | eq | 검색 날짜 시작 범위 |
| endDate | `string` |  | eq | 검색 날짜 끝 범위 |
| type | `string` |  | eq | 충전 및 차감 타입 |
| groupId | `string` |  | eq | 메시지 그룹 ID |
| rechargeMethod | `string` |  | eq | 결제 수단 (STRIPE | ACCOUNT-TRANSFER) |
| serviceMethod | `string` |  | eq | 사용 서비스 (MT) |
| balanceAmount | `number` |  | eq | 사용 금액 |
| balanceRecharge | `boolean` |  | eq | 잔액 충전 여부 |
| balanceDeduct | `boolean` |  | eq | 잔액 차감 여부 |
| pointRecharge | `boolean` |  | eq | 포인트 충전 여부 |
| pointDeduct | `boolean` |  | eq | 포인트 차감 여부 |

---

## Samples

### getBalanceHistory.spec.js

> **Sample Request**

```
http://api.solapi.com/cash/v1/balance/history
```

> **Sample Response**

```json
[
    {
        "balanceAmount": 0,
        "pointAmount": 100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 0,
        "newPoint": 100,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T10:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543bff6"
    },
    {
        "balanceAmount": 0,
        "pointAmount": 100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 0,
        "newPoint": 100,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T10:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543bfee"
    },
    {
        "balanceAmount": 0,
        "pointAmount": 100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 0,
        "newPoint": 100,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T10:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543bff0"
    },
    {
        "balanceAmount": 0,
        "pointAmount": 100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 0,
        "newPoint": 100,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T10:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543bff2"
    },
    {
        "balanceAmount": 0,
        "pointAmount": 100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 0,
        "newPoint": 100,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T10:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543bff4"
    },
    {
        "balanceAmount": 100,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 100,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T09:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c013"
    },
    {
        "balanceAmount": 100,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 100,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T09:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c01b"
    },
    {
        "balanceAmount": 100,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 100,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T09:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c010"
    },
    {
        "balanceAmount": 100,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 100,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T09:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c00d"
    },
    {
        "balanceAmount": 100,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 100,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T09:00:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c017"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c00f"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c016"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c00c"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c012"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c004"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c002"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c006"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c00a"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c008"
    },
    {
        "balanceAmount": 0,
        "pointAmount": -100,
        "groupId": null,
        "memo": null,
        "rechargeMethod": null,
        "serviceMethod": null,
        "chargedMethod": null,
        "paymentMethod": null,
        "accountId": "19041920726336",
        "oldBalance": 0,
        "newBalance": 0,
        "oldPoint": 300,
        "newPoint": 200,
        "type": "MANUAL",
        "dateCreated": "2018-04-01T08:30:00.000Z",
        "historyId": "5d8dae3efa0c8a4a7543c01a"
    }
]
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/cash/v1/balance/history'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});

```
{% endtab %}

{% tab title="JQUERY" %}

```javascript
var options = {
  headers: {
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
  },
  method: 'GET',
  url: 'http://api.solapi.com/cash/v1/balance/history'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/cash/v1/balance/history";

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n",
        'method'  => 'GET'
    )
);

$context  = stream_context_create($options);
$result = file_get_contents($url, false, $context);

var_dump($result);

```
{% endtab %}

{% tab title="PYTHON" %}

```python
import requests

url = "http://api.solapi.com/cash/v1/balance/history"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/cash/v1/balance/history
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/balance/history")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, headers)

response = http.request(request)
puts response.code
puts response.body

```
{% endtab %}

{% tab title="GO" %}

```go
package main

import (
  "fmt"
  "io/ioutil"
  "net/http"
  "strings"
)

func main() {
  uri := "http://api.solapi.com/cash/v1/balance/history"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")

  client := &http.Client{}
  resp, err := client.Do(req)
  if err != nil { panic(err) }
  defer resp.Body.Close()

  bytes, _ := ioutil.ReadAll(resp.Body)
  str := string(bytes)
  fmt.Println(str)
}

```
{% endtab %}

{% tab title="JAVA" %}

```java
package solapi;

import java.io.BufferedReader;
import java.io.DataOutputStream;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;

public class Request {
  public static void main(String[] args) throws Exception {
    String targetUrl = "http://api.solapi.com/cash/v1/balance/history";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");

    con.setDoOutput(true);
    DataOutputStream wr = new DataOutputStream(con.getOutputStream());
    wr.writeBytes(parameters);
    wr.flush();
    wr.close();

    int responseCode = con.getResponseCode();
    BufferedReader in = new BufferedReader(new InputStreamReader(con.getInputStream()));
    String line;
    StringBuffer response = new StringBuffer();
    while ((line = in.readLine()) != null) {
      response.append(line);
    }
    in.close();

    System.out.println("HTTP response code : " + responseCode);
    System.out.println("HTTP body : " + response.toString());
  }
}

```
{% endtab %}

{% endtabs %}

---

> 문서 생성일 : 2019-09-27

