# 초대 수락\(회원\)

## Request

```text
POST https://api.solapi.com/users/v1/invitations/:invitationId
```

이미 SOLAPI에 가입된 사용자가 다른 계정으로 부터 온 초대를 승락합니다.

### Path Parameters

| Name | Description |
| :---: | :---: |
| :invitationId | 설명 없음 |

## Samples

### confirmInvitation.spec.js

> **Sample Request**

```javascript
{}
```

> **Sample Response**

```javascript
{
    "status": "ACTIVE",
    "accountId": "19123124878303",
    "name": "test1님의 계정",
    "members": [
        {
            "dateCreated": "2019-12-30T21:54:34.962Z",
            "dateUpdated": "2019-12-30T21:54:34.962Z",
            "memberId": "MEMLYwuz6DSew2",
            "role": "OWNER",
            "name": "test1"
        },
        {
            "dateCreated": "2019-12-30T21:54:34.962Z",
            "dateUpdated": "2019-12-30T21:54:34.962Z",
            "memberId": "MEM4Gefl_pMDHC",
            "name": "test2",
            "role": "MEMBER"
        }
    ],
    "dateCreated": "2019-12-30T21:54:38.355Z",
    "dateUpdated": "2019-12-30T21:54:38.363Z"
}
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm'
};

request(options, function(error, response, body) {
  if (error) throw error;
  console.log('result :', body);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm";

$options = array(
    'http' => array(
        'header'  => ,
        'method'  => 'POST'
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

url = "http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm"

response = requests.post(url)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X POST \
    http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm")

http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Post.new(uri.request_uri, )

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
  uri := "http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm"

  req, err := http.NewRequest("POST", uri, nil)
  if err != nil { panic(err) }

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
    String targetUrl = "http://api.solapi.com/users/v1/invitations/CTbhz0F_j9_OWAVcrA3Gm";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");


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

> 문서 생성일 : 2019-12-30

