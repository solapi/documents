# 템플릿을 삭제

#### Request
```
DELETE https://api.solapi.com/kakao/v1/templates/:templateId
```

**Authorization 인증 필요**

템플릿을 삭제합니다.

---

#### Sample Request

```json
{}
```

#### Sample Response

```json
{
    "status": "DELETED",
    "accountId": "12925149",
    "templateId": "KA01TP1906120709591341rexL5GUGmq",
    "name": "A0",
    "pfId": "PF01ID190612070959128JbQ7kvmhEJ0",
    "content": "#{홍길동}님 회원가입을 환영 합니다.",
    "dateCreated": "2019-06-12T06:09:59.493Z",
    "dateUpdated": "2019-06-12T06:09:59.493Z",
    "buttons": [],
    "comments": []
}
```

#### Sample Code

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    Authorization: 'Bearer eyJhbGciOiJI...'
  },
  method: 'DELETE',
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq'
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
  method: 'DELETE',
  url:
    'http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
$url = "http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq";
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

url = "http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq"
headers = {"Authorization":"Bearer eyJhbGciOiJI..."}

response = requests.delete(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
curl -X DELETE \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq")

headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Delete.new(uri.request_uri, headers)

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
  uri := "http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq"

  req, err := http.NewRequest("DELETE", uri, nil)
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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/KA01TP1906120709591341rexL5GUGmq";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("DELETE");

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

---

