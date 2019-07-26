# 이미지 삭제

#### Request
```
DELETE https://api.solapi.com/images/v4/images/:imageId
```

계정의 이미지를 삭제합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `images:write` | `role-images:write` | `ACTIVE` |  |  |

##### Path Parameters

| Name | Description |
| :--: | :---------: |
| :imageId | 이미지 ID |

---

#### Samples

##### 정상적인 삭제

> **Sample Request**

```
{}
```

> **Sample Response**

```json
{
    "result": "SUCCESS"
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
  method: 'DELETE',
  json: true,
  url: 'http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0'
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
  url: 'http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
        'method'  => 'DELETE'
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

url = "http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.delete(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X DELETE \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}
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
  uri := "http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0"

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
    String targetUrl = "http://api.solapi.com/images/v4/images/M4V20190726154041GXJXBQ7FSZLMUF0";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("DELETE");

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

---

##### 정상 삭제

> **Sample Request**

```
{}
```

> **Sample Response**

```json
{
    "result": "SUCCESS"
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
  method: 'DELETE',
  json: true,
  url: 'http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z'
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
  url: 'http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z";

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n",
        'method'  => 'DELETE'
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

url = "http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}

response = requests.delete(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X DELETE \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
}
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
  uri := "http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z"

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
    String targetUrl = "http://api.solapi.com/images/v4/images/M4V20190726154041PWKRQUNBBNUYM5Z";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("DELETE");

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

---

