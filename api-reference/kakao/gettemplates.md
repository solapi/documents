# 템플릿 목록 조회

## Request

```text
GET https://api.solapi.com/kakao/v1/templates
```

템플릿의 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `kakao:read` | `role-kakao:read` |  |  |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
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

### getTemplates.spec.js

> **Sample Request**

```text
http://api.solapi.com/kakao/v1/templates
```

> **Sample Response**

```javascript
{
    "limit": 20,
    "templateList": [
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848w20Wf9atNAK",
            "name": "A26",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848tlROAHBFDJF",
            "name": "A30",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848nz6rj9jdBs2",
            "name": "A27",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848kQEkSaodF3U",
            "name": "A34",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848k2JWDpe2H0Q",
            "name": "A32",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848fkqw86P3sK5",
            "name": "A33",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848eYohlsj396H",
            "name": "A31",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848c4YeMQTxbBG",
            "name": "A23",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848KWdgsqcGJtv",
            "name": "A29",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848HNvhc1ERabk",
            "name": "A25",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848H0p8f999xlH",
            "name": "A22",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543848Fmxxlay4k1R",
            "name": "A28",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID1908200455438484eNRLt9wgU7",
            "name": "A24",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543847UdOFtAubDQY",
            "name": "A21",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.848Z",
            "dateUpdated": "2019-08-20T03:55:43.848Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846tw8gtYU7EPT",
            "name": "A14",
            "pfId": "PF01ID190820045543275IAX79Ey80Wp",
            "content": "testMessage",
            "dateCreated": "2019-08-30T03:55:43.274Z",
            "dateUpdated": "2019-08-30T03:55:43.274Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846sNzPG7ZFxh2",
            "name": "A17",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.846Z",
            "dateUpdated": "2019-08-20T03:55:43.846Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846o8qheMveb8Q",
            "name": "A8",
            "pfId": "PF01ID190820045543275IAX79Ey80Wp",
            "content": "testMessage",
            "dateCreated": "2019-08-30T03:55:43.274Z",
            "dateUpdated": "2019-08-30T03:55:43.274Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "INSPECTING",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846jMqIcgBX7Qh",
            "name": "A9",
            "pfId": "PF01ID190820045543275IAX79Ey80Wp",
            "content": "testMessage",
            "dateCreated": "2019-08-30T03:55:43.274Z",
            "dateUpdated": "2019-08-30T03:55:43.274Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846gbuEgzXN8Yx",
            "name": "A16",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.846Z",
            "dateUpdated": "2019-08-20T03:55:43.846Z",
            "buttons": [],
            "comments": []
        },
        {
            "status": "APPROVED",
            "accountId": "12925149",
            "templateId": "TP01ID190820045543846bxYrd5TesBy",
            "name": "A20",
            "pfId": "PF01ID190820045543275mpZANryR46w",
            "content": "testMessage",
            "dateCreated": "2019-08-20T03:55:43.847Z",
            "dateUpdated": "2019-08-20T03:55:43.847Z",
            "buttons": [],
            "comments": []
        }
    ],
    "startKey": "TP01ID190820045543848w20Wf9atNAK",
    "nextKey": "TP01ID190820045543846Tgf2dMr23dw"
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
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
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

url = "http://api.solapi.com/kakao/v1/templates"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
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
    -H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
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
  uri := "http://api.solapi.com/kakao/v1/templates"

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
    String targetUrl = "http://api.solapi.com/kakao/v1/templates";

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

> 문서 생성일 : 2019-08-20

