# 해외 문자 리포트 처리

## Request
```
POST https://api.solapi.com/messages/v4/overseas/report
```

해외 문자 리포트 처리를 담당합니다.

### Request Structure
```json
{
    "msisdn": "any",
    "to": "string",
    "messageId": "any",
    "price": "any",
    "status": "string",
    "scts": "any",
    "network-code": "any",
    "err-code": "any",
    "api-key": "string",
    "message-timestamp": "any"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| msisdn | `any` |  | 설명 없음 |
| to | `string` |  | 수신번호 |
| messageId | `any` |  | 메시지 아이디 |
| price | `any` |  | 설명 없음 |
| status | `string` |  | 상태값 |
| scts | `any` |  | 설명 없음 |
| network-code | `any` |  | 설명 없음 |
| err-code | `any` |  | 설명 없음 |
| api-key | `string` |  | 설명 없음 |
| message-timestamp | `any` |  | 설명 없음 |


---

## Samples

### overseas/report.spec.js

> **Sample Request**

```json
{
    "msisdn": "447700900000",
    "to": "AcmeInc",
    "network-code": "12345",
    "messageId": "0A0000001234567B",
    "price": "0.03330000",
    "status": "delivered",
    "scts": "2001011400",
    "err-code": "0",
    "message-timestamp": "2020-01-01T12:00:00.000+00:00"
}
```

> **Sample Response**

```json
{
    "_id": "M4V201FFFFFFFFFAAAAAAAAAAAAAZIB0",
    "kakaoOptions": {
        "senderKey": null,
        "templateCode": null,
        "buttonName": null,
        "buttonUrl": null,
        "pfId": null,
        "templateId": null,
        "imageId": null,
        "disableSms": false,
        "buttons": []
    },
    "type": null,
    "country": "82",
    "subject": null,
    "imageId": null,
    "dateProcessed": null,
    "dateReported": null,
    "dateReceived": null,
    "statusCode": "4000",
    "networkCode": null,
    "log": [],
    "replacement": false,
    "autoTypeDetect": true,
    "routedQueue": null,
    "messageId": "M4V201FFFFFFFFFAAAAAAAAAAAAAZIB0",
    "groupId": "G4V20180307TTTTTTTTAAATTTTTTTTTT",
    "accountId": "12925149",
    "text": "text",
    "from": "01000000000",
    "to": "01000000000",
    "customFields": {},
    "hint": {},
    "dateCreated": "2020-09-09T04:20:26.941Z",
    "dateUpdated": "2020-09-09T04:20:26.948Z"
}
```

> **Sample Code**

{% tabs %}

{% tab title="NODE" %}

```javascript
var request = require('request');

var options = {
  headers: {
    'Content-Type': 'application/json'
  },
  body: {
    msisdn: '447700900000',
    to: 'AcmeInc',
    'network-code': '12345',
    messageId: '0A0000001234567B',
    price: '0.03330000',
    status: 'delivered',
    scts: '2001011400',
    'err-code': '0',
    'message-timestamp': '2020-01-01T12:00:00.000+00:00'
  },
  method: 'POST',
  json: true,
  url: 'http://api.solapi.com/messages/v4/overseas/report'
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
$url = "http://api.solapi.com/messages/v4/overseas/report";
$data = '{"msisdn":"447700900000","to":"AcmeInc","network-code":"12345","messageId":"0A0000001234567B","price":"0.03330000","status":"delivered","scts":"2001011400","err-code":"0","message-timestamp":"2020-01-01T12:00:00.000+00:00"}';

$options = array(
    'http' => array(
        'header'  => "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/messages/v4/overseas/report"
headers = {
  "Content-Type": "application/json"
}
data = '{"msisdn":"447700900000","to":"AcmeInc","network-code":"12345","messageId":"0A0000001234567B","price":"0.03330000","status":"delivered","scts":"2001011400","err-code":"0","message-timestamp":"2020-01-01T12:00:00.000+00:00"}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Content-Type: application/json' \
	-d '{"msisdn":"447700900000","to":"AcmeInc","network-code":"12345","messageId":"0A0000001234567B","price":"0.03330000","status":"delivered","scts":"2001011400","err-code":"0","message-timestamp":"2020-01-01T12:00:00.000+00:00"}' \
	http://api.solapi.com/messages/v4/overseas/report
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/overseas/report")

headers = {
  "Content-Type": "application/json"
}
data = {
  "msisdn": "447700900000",
  "to": "AcmeInc",
  "network-code": "12345",
  "messageId": "0A0000001234567B",
  "price": "0.03330000",
  "status": "delivered",
  "scts": "2001011400",
  "err-code": "0",
  "message-timestamp": "2020-01-01T12:00:00.000+00:00"
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
  uri := "http://api.solapi.com/messages/v4/overseas/report"
  data := strings.NewReader(`{"msisdn":"447700900000","to":"AcmeInc","network-code":"12345","messageId":"0A0000001234567B","price":"0.03330000","status":"delivered","scts":"2001011400","err-code":"0","message-timestamp":"2020-01-01T12:00:00.000+00:00"}`)

  req, err := http.NewRequest("POST", uri, data)
  if err != nil { panic(err) }

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
    String targetUrl = "http://api.solapi.com/messages/v4/overseas/report";
    String parameters = "{\"msisdn\":\"447700900000\",\"to\":\"AcmeInc\",\"network-code\":\"12345\",\"messageId\":\"0A0000001234567B\",\"price\":\"0.03330000\",\"status\":\"delivered\",\"scts\":\"2001011400\",\"err-code\":\"0\",\"message-timestamp\":\"2020-01-01T12:00:00.000+00:00\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

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

> 문서 생성일 : 2020-09-09

