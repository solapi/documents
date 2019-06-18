# 템플릿 정보 조회

## Request

```text
GET https://api.solapi.com/kakao/v1/templates/:templateId
```

**Authorization 인증 필요**

템플릿의 아이디로 템플릿 정보를 조회합니다.

## Sample Request

```javascript
{}
```

## Sample Response

```javascript
{
    "status": "APPROVED",
    "accountId": "12925149",
    "templateId": "TP01ID190612085958172bYBzUbXyRXq",
    "name": "A10",
    "pfId": "PF01ID190612085958172MdEkdmdqY8k",
    "content": "testMessage",
    "dateCreated": "2019-06-12T07:59:58.172Z",
    "dateUpdated": "2019-06-12T07:59:58.172Z",
    "buttons": [],
    "comments": []
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
  method: 'GET',
  url:
    'http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq'
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
    'http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
$url = "http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq";
$data = array();

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

url = "http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq"
headers = {"Authorization":"Bearer eyJhbGciOiJI..."}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
curl -X GET \
    -H 'Authorization: Bearer eyJhbGciOiJI...' \
    http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq")

headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
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
  uri := "http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/TP01ID190612085958172bYBzUbXyRXq";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");

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

