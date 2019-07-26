# 등록된 결제수단의 우선순위를 변경

#### Request
```
PUT https://api.solapi.com/cash/v1/payment
```

등록된 결제수단의 우선순위를 변경합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `cash:write` | `role-cash:write` | `ACTIVE` |  | O |

##### Request Structure
```json
{
    "paymentIds": [
        "string"
    ],
    "minimumCash": "number",
    "rechargeTo": "number"
}
```

##### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| paymentIds | `array` | O | 결제 ID |
| minimumCash | `number` | O | 충전 기준 금액 |
| rechargeTo | `number` | O | 충전 목표 금액 |



---

#### Samples

##### 우선순위 변경 (정상)

> **Sample Request**

```json
{
    "paymentIds": [
        "7343657161927503001564122326067",
        "7347421754106775001564122326067"
    ],
    "minimumCash": 1000,
    "rechargeTo": 100000
}
```

> **Sample Response**

```json
{
    "paymentIds": [
        "7343657161927503001564122326067",
        "7347421754106775001564122326067"
    ],
    "minimumCash": 1000,
    "rechargeTo": 100000
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    paymentIds: '734365716192750300156412232...',
    minimumCash: 1000,
    rechargeTo: 100000
  },
  method: 'PUT',
  json: true,
  url: 'http://api.solapi.com/cash/v1/payment'
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
    Authorization: 'Bearer eyJhbGciOiJI...',
    'Content-Type': 'application/json'
  },
  body: {
    paymentIds: '734365716192750300156412232...',
    minimumCash: 1000,
    rechargeTo: 100000
  },
  method: 'PUT',
  url: 'http://api.solapi.com/cash/v1/payment'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/cash/v1/payment";
$data = '{"paymentIds":"734365716192750300156412232...","minimumCash":1000,"rechargeTo":100000}';

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n" . "Content-Type: application/json\r\n",
        'content' => $data,
        'method'  => 'PUT'
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

url = "http://api.solapi.com/cash/v1/payment"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"paymentIds":"734365716192750300156412232...","minimumCash":1000,"rechargeTo":100000}'

response = requests.put(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X PUT \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-H 'Content-Type: application/json' \
	-d '{"paymentIds":"734365716192750300156412232...","minimumCash":1000,"rechargeTo":100000}' \
	http://api.solapi.com/cash/v1/payment
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/cash/v1/payment")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "paymentIds": "734365716192750300156412232...",
  "minimumCash": 1000,
  "rechargeTo": 100000
}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Put.new(uri.request_uri, headers)
request.body = data.to_json

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
  uri := "http://api.solapi.com/cash/v1/payment"
  data := strings.NewReader(`{"paymentIds":"734365716192750300156412232...","minimumCash":1000,"rechargeTo":100000}`)

  req, err := http.NewRequest("PUT", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "Bearer eyJhbGciOiJI...")
  req.Header.Set("Content-Type", "application/json")

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
    String targetUrl = "http://api.solapi.com/cash/v1/payment";
    String parameters = "{\"paymentIds\":\"734365716192750300156412232...\",\"minimumCash\":1000,\"rechargeTo\":100000}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("PUT");

    con.setRequestProperty("Authorization", "Bearer eyJhbGciOiJI...");
    con.setRequestProperty("Content-Type", "application/json");

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

