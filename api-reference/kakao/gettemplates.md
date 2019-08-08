# 템플릿 목록 조회

## Request

```text
GET https://api.solapi.com/kakao/v1/templates
```

템플릿의 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `kakao:read` | `role-kakao:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| name | `string` |  | eq, ne, like | 이름 |
| pfId | `string` |  | eq | 플러스 친구 고유 아이디 |
| templateId | `string` |  | eq | 템플릿 고유 아이디 |
| status | `string` |  | eq | 상태값 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateCreated | `date` |  | eq, gte, lte, gt, lt | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq, gte, lte, gt, lt | 최초 생성 날짜 |

## Samples

### 정상

> **Sample Request**

```text
{}
```

> **Sample Response**

```javascript
{
    "limit": 20,
    "templateList": [
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522zH0ftFM53Ih",
            "name": "A28",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522hJosu7c8SuD",
            "name": "A31",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522d9WcSalZaPI",
            "name": "A32",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522XiROyIcp0Q5",
            "name": "A29",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522Wwn5xMp0sFW",
            "name": "A30",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522NIvD7shzPJq",
            "name": "A34",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522E25tP9ebdmx",
            "name": "A33",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551522AEYpUS1UK10",
            "name": "A27",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.522Z",
            "dateUpdated": "2019-07-26T06:45:51.522Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521rjrHjpjeFa5",
            "name": "A11",
            "pfId": "PF01ID190726074551012zAnx0XXSioZ",
            "content": "testMessage",
            "dateCreated": "2019-08-05T06:45:51.012Z",
            "dateUpdated": "2019-08-05T06:45:51.012Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521r5fvJftrJX6",
            "name": "A13",
            "pfId": "PF01ID190726074551012zAnx0XXSioZ",
            "content": "testMessage",
            "dateCreated": "2019-08-05T06:45:51.012Z",
            "dateUpdated": "2019-08-05T06:45:51.012Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521nnqmA1PvMtJ",
            "name": "A20",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521mtVeTkyGGmd",
            "name": "A16",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521lBhXTEYcLiS",
            "name": "A17",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521i9Q6OKJHzCu",
            "name": "A18",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521dIBJMu10I0D",
            "name": "A14",
            "pfId": "PF01ID190726074551012zAnx0XXSioZ",
            "content": "testMessage",
            "dateCreated": "2019-08-05T06:45:51.012Z",
            "dateUpdated": "2019-08-05T06:45:51.012Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521YwUO1Pish2K",
            "name": "A23",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521Y4lgsxt7AbJ",
            "name": "A12",
            "pfId": "PF01ID190726074551012zAnx0XXSioZ",
            "content": "testMessage",
            "dateCreated": "2019-08-05T06:45:51.012Z",
            "dateUpdated": "2019-08-05T06:45:51.012Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521VUrnRng3Nov",
            "name": "A22",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521UCLWy8Ml2Th",
            "name": "A19",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190726074551521EM0INTow466",
            "name": "A15",
            "pfId": "PF01ID190726074551012P4wqsnZTojy",
            "content": "testMessage",
            "dateCreated": "2019-07-26T06:45:51.521Z",
            "dateUpdated": "2019-07-26T06:45:51.521Z",
            "buttons": [],
            "comments": []
        }
    ],
    "startKey": "TP01ID190726074551522zH0ftFM53Ih",
    "nextKey": "TP01ID190726074551521EFe59yMLOUR"
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
  url: 'http://api.solapi.com/kakao/v1/templates'
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
  url: 'http://api.solapi.com/kakao/v1/templates'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/kakao/v1/templates";

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

url = "http://api.solapi.com/kakao/v1/templates"
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
    http://api.solapi.com/kakao/v1/templates
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/kakao/v1/templates")

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
  uri := "http://api.solapi.com/kakao/v1/templates"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates";

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

