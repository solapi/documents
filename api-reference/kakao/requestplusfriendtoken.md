# 플러스 친구 연동 토큰 신청

## Request

```text
POST https://api.solapi.com/kakao/v1/plus-friends/token
```

**Authorization 인증 필요**

플러스 친구 연동을 위해 카카오톡으로 토큰을 발급 받을 수 있도록 요청합니다.

```javascript
{
    "searchId": "string",
    "phoneNumber": "string"
}
```

## Body Params

| Name | Type | Required | Description |
| :--- | :---: | :---: | :--- |
| searchId | `string` | O | 플러스 친구 검색용 아이디 |
| phoneNumber | `string` | O | 핸드폰 번호 |

## Sample Request

```javascript
{
    "searchId": "NURIGO",
    "phoneNumber": "01055555555"
}
```

## Sample Response

```javascript
{
    "success": true
}
```

## Sample Code

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  body: {
    searchId: 'NURIGO',
    phoneNumber: '01055555555'
  },
  method: 'POST',
  url: 'http://api.solapi.com/kakao/v1/plus-friends/token'
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
  body: {
    searchId: 'NURIGO',
    phoneNumber: '01055555555'
  },
  method: 'POST',
  url: 'http://api.solapi.com/kakao/v1/plus-friends/token'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
$url = "http://api.solapi.com/kakao/v1/plus-friends/token";
$data = array("searchId" => "NURIGO", "phoneNumber" => "01055555555");

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
        'method'  => 'GET',
        'content' => http_build_query($data)
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

url = "http://api.solapi.com/kakao/v1/plus-friends/token"
headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
data = {"searchId":"NURIGO","phoneNumber":"01055555555"}

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
curl -X POST \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    -d searchId=NURIGO \
    -d phoneNumber=01055555555 \
    http://api.solapi.com/kakao/v1/plus-friends/token
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/plus-friends/token")

headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
data = {"searchId":"NURIGO","phoneNumber":"01055555555"}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Post.new(uri.request_uri, headers)
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
  uri := "http://api.solapi.com/kakao/v1/plus-friends/token"
  data := strings.NewReader(`{"searchId":"NURIGO","phoneNumber":"01055555555"}`)

  req, err := http.NewRequest("POST", uri, data)
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
    String targetUrl = "http://api.solapi.com/kakao/v1/plus-friends/token";
    String parameters = "searchId=NURIGO&phoneNumber=01055555555";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

    con.setRequestProperty("x-is-admin", "true");

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

