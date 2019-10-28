# 출금 요청 상태 조회

## Request
```
GET https://api.solapi.com/cash/v1/withdraw
```

출금 요청 상태를 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `cash:read` | `role-cash:read` |  |  |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| withdrawId | `string` |  | eq | 출금 ID |
| status | `string` |  | eq | 상태값 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| startDate | `string` |  | eq | 검색 날짜 시작 범위 |
| endDate | `string` |  | eq | 검색 날짜 끝 범위 |

---

## Samples

### getWithdraw.spec.js

> **Sample Request**

```
http://api.solapi.com/cash/v1/withdraw
```

> **Sample Response**

```json
{
    "data": [
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": "A",
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "2960263173653180598136622655504",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.513Z",
            "dateUpdated": "2019-10-28T17:43:54.513Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "2960263173653180598136622655503",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.505Z",
            "dateUpdated": "2019-10-28T17:43:54.505Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "2960263173653180598136622655502",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.503Z",
            "dateUpdated": "2019-10-28T17:43:54.503Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "2960263173653180598136622655501",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.498Z",
            "dateUpdated": "2019-10-28T17:43:54.498Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1940263173653180598136622655500",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.487Z",
            "dateUpdated": "2019-10-28T17:43:54.487Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": "D",
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1840263173653180598136622655500",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.486Z",
            "dateUpdated": "2019-10-28T17:43:54.486Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655529",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.492Z",
            "dateUpdated": "2019-10-28T17:43:54.492Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655528",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.489Z",
            "dateUpdated": "2019-10-28T17:43:54.491Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655527",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.489Z",
            "dateUpdated": "2019-10-28T17:43:54.489Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655526",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.489Z",
            "dateUpdated": "2019-10-28T17:43:54.489Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655525",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655524",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655523",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655522",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655521",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655520",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655519",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655518",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655517",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        },
        {
            "bankCode": "012",
            "accountNumber": "******7890",
            "holderName": "홍길동",
            "status": "PENDING",
            "isProcessing": false,
            "confirmedCount": 0,
            "memo": null,
            "transactionId": null,
            "transactionDate": null,
            "accountId": "19041920726336",
            "amount": 9000,
            "fee": 1000,
            "totalAmount": 10000,
            "withdrawId": "1540263173653180598136622655516",
            "dateConfirmed": "2019-10-28T17:43:54.000Z",
            "dateCreated": "2019-10-28T17:43:54.488Z",
            "dateUpdated": "2019-10-28T17:43:54.488Z"
        }
    ],
    "nextKey": "1540263173653180598136622655515"
}
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
  url: 'http://api.solapi.com/cash/v1/withdraw'
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
  url: 'http://api.solapi.com/cash/v1/withdraw'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/cash/v1/withdraw";

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

url = "http://api.solapi.com/cash/v1/withdraw"
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
	http://api.solapi.com/cash/v1/withdraw
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/withdraw")

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
  uri := "http://api.solapi.com/cash/v1/withdraw"

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
    String targetUrl = "http://api.solapi.com/cash/v1/withdraw";

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

> 문서 생성일 : 2019-10-28

