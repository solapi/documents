# 발신번호 개수 증가 요청

#### Request
```
POST https://api.solapi.com/senderid/v1/papers/limitation
```

발신번호 개수를 더 사용할 수 있도록 관리자에게 요청합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `senderid:write` | `role-senderid:write` | `ACTIVE` |  | O |

##### Request Structure
```json
{
    "documents": [
        "string"
    ],
    "limit": "number"
}
```

##### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| documents | `Array` | O | 문서 ID 목록 |
| limit | `number` | O | 한 페이지에 불러옥 목록 개수 |



---

#### Samples

##### 문서 하나

> **Sample Request**

```json
{
    "documents": [
        "DOC20181030105615MMXDST163SYMMX3"
    ],
    "limit": 10
}
```

> **Sample Response**

```json
{
    "limit": 2,
    "accountId": "12925149",
    "senderIds": [
        {
            "unlockDuplicate": {
                "duplicateId": null,
                "reason": null,
                "reasonForRequested": null,
                "name": null,
                "status": null,
                "dateCreated": null,
                "dateUpdated": null
            },
            "status": "PENDING",
            "expireAt": null,
            "method": null,
            "log": [],
            "dateCreated": "2019-07-26T07:26:23.814Z",
            "dateUpdated": "2019-07-26T07:26:23.815Z",
            "approvalDocuments": [],
            "handleKey": "SED20181030105615MMXDST163SYMMX2",
            "phoneNumber": "01000000000"
        }
    ],
    "limitationDocuments": [
        {
            "documents": [
                "DOC20181030105615MMXDST163SYMMX3"
            ],
            "reason": null,
            "status": "PENDING",
            "dateCreated": "2019-07-26T07:26:23.832Z",
            "dateUpdated": "2019-07-26T07:26:23.832Z",
            "limitationId": "LID201907261626231JXLPC9M57O3MO6",
            "limitRequested": 10,
            "limitBeforeRequest": 2
        }
    ],
    "dateCreated": "2019-07-26T07:26:23.815Z",
    "dateUpdated": "2019-07-26T07:26:23.831Z"
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
    documents: 'DOC20181030105615MMXDST163S...',
    limit: 10
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/senderid/v1/papers/limitation'
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
    documents: 'DOC20181030105615MMXDST163S...',
    limit: 10
  },
  method: 'POST',
  url: 'http://api.solapi.com/senderid/v1/papers/limitation'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/senderid/v1/papers/limitation";
$data = '{"documents":"DOC20181030105615MMXDST163S...","limit":10}';

$options = array(
    'http' => array(
        'header'  => "Authorization: Bearer eyJhbGciOiJI...\r\n" . "Content-Type: application/json\r\n",
        'content' => $data,
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

url = "http://api.solapi.com/senderid/v1/papers/limitation"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = '{"documents":"DOC20181030105615MMXDST163S...","limit":10}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	-H 'Content-Type: application/json' \
	-d '{"documents":"DOC20181030105615MMXDST163S...","limit":10}' \
	http://api.solapi.com/senderid/v1/papers/limitation
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/senderid/v1/papers/limitation")

headers = {
  "Authorization": "Bearer eyJhbGciOiJI...",
  "Content-Type": "application/json"
}
data = {
  "documents": "DOC20181030105615MMXDST163S...",
  "limit": 10
}
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
  uri := "http://api.solapi.com/senderid/v1/papers/limitation"
  data := strings.NewReader(`{"documents":"DOC20181030105615MMXDST163S...","limit":10}`)

  req, err := http.NewRequest("POST", uri, data)
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
    String targetUrl = "http://api.solapi.com/senderid/v1/papers/limitation";
    String parameters = "{\"documents\":\"DOC20181030105615MMXDST163S...\",\"limit\":10}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

