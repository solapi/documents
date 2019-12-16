# 국가별 메시지 가격 리스트 가져오기

## Request

```text
GET https://api.solapi.com/pricing/v1/messaging/countries
```

로그인한 계정의 국가별 메시지 가격 리스트를 가져옵니다. \(로그인 안하면 기본 단가\)

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| countryId | `string` |  | eq | 국가 코드 |
| offset | `number` |  | eq | 시작점 |
| limit | `number` |  | eq | 조회할 개수 |

## Samples

### getMessagePriceList.spec.js

> **Sample Request**

```text
http://api.solapi.com/pricing/v1/messaging/countries
```

> **Sample Response**

```javascript
[
    {
        "countryName": "Korea, South",
        "countryId": "82",
        "sms": 20,
        "lms": 50,
        "mms": 200,
        "ata": 19,
        "cta": 13,
        "cti": 20,
        "dateCreated": "2019-10-28T18:03:40.761Z",
        "dateUpdated": "2019-10-28T18:03:40.761Z"
    },
    {
        "countryName": "Lithuania",
        "countryId": "370",
        "sms": 94,
        "lms": 500,
        "mms": 1000,
        "ata": 19,
        "cta": 13,
        "cti": 20,
        "dateCreated": "2019-10-28T18:03:40.760Z",
        "dateUpdated": "2019-10-28T18:03:40.760Z"
    },
    {
        "countryName": "Turkmenistan",
        "countryId": "993",
        "sms": 94,
        "lms": 500,
        "mms": 1000,
        "ata": 19,
        "cta": 13,
        "cti": 20,
        "dateCreated": "2019-10-28T18:03:40.758Z",
        "dateUpdated": "2019-10-28T18:03:40.758Z"
    },
    {
        "countryName": "Sao Tome and Principe",
        "countryId": "239",
        "sms": 271,
        "lms": 500,
        "mms": 1000,
        "ata": 19,
        "cta": 13,
        "cti": 20,
        "dateCreated": "2019-10-28T18:03:40.757Z",
        "dateUpdated": "2019-10-28T18:03:40.757Z"
    },
    {
        "countryName": "East Timor",
        "countryId": "670",
        "sms": 180,
        "lms": 500,
        "mms": 1000,
        "ata": 19,
        "cta": 13,
        "cti": 20,
        "dateCreated": "2019-10-28T18:03:40.755Z",
        "dateUpdated": "2019-10-28T18:03:40.755Z"
    }
]
```

> **Sample Code**

{% tabs %}
{% tab title="NODE" %}
```javascript
var request = require('request');

var options = {
  method: 'GET',
  json: true,
  url: 'http://api.solapi.com/pricing/v1/messaging/countries'
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
  method: 'GET',
  url: 'http://api.solapi.com/pricing/v1/messaging/countries'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/pricing/v1/messaging/countries";

$options = array(
    'http' => array(
        'header'  => ,
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

url = "http://api.solapi.com/pricing/v1/messaging/countries"

response = requests.get(url)
print(response.status_code)
print(response.text)
```
{% endtab %}

{% tab title="CURL" %}
```text
#!/bin/bash
curl -X GET \
    http://api.solapi.com/pricing/v1/messaging/countries
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/pricing/v1/messaging/countries")

http = Net::HTTP.new(uri.host, uri.port)
request = Net::HTTP::Get.new(uri.request_uri, )

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
  uri := "http://api.solapi.com/pricing/v1/messaging/countries"

  req, err := http.NewRequest("GET", uri, nil)
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
    String targetUrl = "http://api.solapi.com/pricing/v1/messaging/countries";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("GET");


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

> 문서 생성일 : 2019-10-28

