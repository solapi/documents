# 앱 정산내역 조회

## Request

```text
GET https://api.solapi.com/appstore/v2/profits
```

자기가 만든 앱들의 정산내역을 조회할 수 있습니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `appstore:read` | `role-appstore:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| startDate | `string` | O | eq | 검색 날짜 시작 범위 |
| endDate | `string` | O | eq | 검색 날짜 끝 범위 |
| appId | `string` |  | eq | 앱 아이디 |
| offset | `number` |  | eq | 검색 시작 지점 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |

## Samples

### \(성공\) 모든앱 조회

> **Sample Request**

```text
{}
```

> **Sample Response**

```javascript
{
    "expectedProfit": 3,
    "completed": [
        {
            "accountId": "12925149",
            "appId": "ABCDE2345678",
            "dateCreated": "2019-07-26T07:14:45.499Z",
            "dateUpdated": "2019-07-26T07:14:45.499Z",
            "appName": "2345678"
        },
        {
            "accountId": "12925149",
            "appId": "ABCDE1234567",
            "dateCreated": "2019-07-26T07:14:45.498Z",
            "dateUpdated": "2019-07-26T07:14:45.498Z",
            "appName": "1234567"
        }
    ]
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  json: true,
  url:
    'http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59'
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
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'GET',
  url:
    'http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
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

url = "http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X GET \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
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
  uri := "http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59"

  req, err := http.NewRequest("GET", uri, nil)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")

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
    String targetUrl = "http://api.solapi.com/appstore/v2/profits?startDate=2010-01-10%2001:01:01&offset=0&limit=2&endDate=2020-12-31%2023:59:59";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");

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

