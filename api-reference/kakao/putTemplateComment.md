# 템플릿 댓글 추가

#### Request
```
POST https://api.solapi.com/kakao/v1/templates/:templateId/comment
```

**Authorization 인증 필요**

템플릿에 댓글을 추가합니다.

```json
{
    "comment": "string"
}
```

#### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| comment | `string` | O | 템플릿에 다는 댓글 |


---

#### Sample Request

```json
{
    "comment": "템플릿 등록 문의드립니다."
}
```

#### Sample Response

```json
{
    "status": "REJECTED",
    "accountId": "12925149",
    "templateId": "TP01ID190612070959151vxKNHplgsnf",
    "name": "A10",
    "pfId": "PF01ID190612070959151Ef7gxwKkkby",
    "content": "testMessage",
    "dateCreated": "2019-06-12T06:09:59.151Z",
    "dateUpdated": "2019-06-12T06:10:00.360Z",
    "buttons": [],
    "comments": [
        {
            "isAdmin": false,
            "dateCreated": "2019-06-12T06:10:00.361Z",
            "memberId": "18010100001000",
            "content": "템플릿 등록 문의드립니다."
        }
    ]
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
  body: {
    comment: '템플릿 등록 문의드립니다.'
  },
  method: 'POST',
  url:
    'http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment'
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
    comment: '템플릿 등록 문의드립니다.'
  },
  method: 'POST',
  url:
    'http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
$url = "http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment";
$data = array("comment" => "템플릿 등록 문의드립니다.");

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

url = "http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment"
headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
data = {"comment":"템플릿 등록 문의드립니다."}

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
curl -X POST \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-d comment=템플릿 등록 문의드립니다. \
	http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment")

headers = {"Authorization":"Bearer eyJhbGciOiJI..."}
data = {"comment":"템플릿 등록 문의드립니다."}
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
  uri := "http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment"
  data := strings.NewReader(`{"comment":"템플릿 등록 문의드립니다."}`)

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates/TP01ID190612070959151vxKNHplgsnf/comment";
    String parameters = "comment=템플릿 등록 문의드립니다.";

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

---

