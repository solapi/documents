# 통계 조회

## Request
```
GET https://api.solapi.com/messages/v4/statistics
```

통계를 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` | O |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

---

## Samples

### getStatistics.spec.js

> **Sample Request**

```
http://api.solapi.com/messages/v4/statistics
```

> **Sample Response**

```json
{
    "balance": 1,
    "point": 1,
    "monthlyBalanceAvg": 1,
    "monthlyPointAvg": 1,
    "monthPeriod": [
        {
            "date": "2019/10",
            "balance": 1,
            "balanceAvg": 1,
            "point": 1,
            "pointAvg": 1,
            "dayPeriod": [
                {
                    "_id": "2019-10-29T19:12:05.355Z",
                    "month": "2019/10",
                    "date": "2019/10/30",
                    "balance": 1,
                    "point": 1,
                    "statusCode": {
                        "4000": {
                            "sms": 1,
                            "lms": 1,
                            "mms": 1,
                            "ata": 1,
                            "cta": 1
                        }
                    },
                    "refund": {
                        "balance": 100,
                        "point": 10
                    },
                    "total": {
                        "total": 5,
                        "sms": 1,
                        "lms": 1,
                        "mms": 1,
                        "ata": 1,
                        "cta": 1,
                        "cti": 0
                    },
                    "successed": {
                        "total": 5,
                        "sms": 1,
                        "lms": 1,
                        "mms": 1,
                        "ata": 1,
                        "cta": 1,
                        "cti": 0
                    },
                    "failed": {
                        "total": 0,
                        "sms": 0,
                        "lms": 0,
                        "mms": 0,
                        "ata": 0,
                        "cta": 0,
                        "cti": 0
                    }
                }
            ],
            "refund": {
                "balance": 100,
                "balanceAvg": 100,
                "point": 10,
                "pointAvg": 10
            },
            "total": {
                "total": 5,
                "sms": 1,
                "lms": 1,
                "mms": 1,
                "ata": 1,
                "cta": 1,
                "cti": 0
            },
            "successed": {
                "total": 5,
                "sms": 1,
                "lms": 1,
                "mms": 1,
                "ata": 1,
                "cta": 1,
                "cti": 0
            },
            "failed": {
                "total": 0,
                "sms": 0,
                "lms": 0,
                "mms": 0,
                "ata": 0,
                "cta": 0,
                "cti": 0
            }
        }
    ],
    "refund": {
        "balance": 100,
        "balanceAvg": 100,
        "point": 10,
        "pointAvg": 10
    },
    "dayPeriod": [
        {
            "_id": "2019-10-29T19:12:05.355Z",
            "month": "2019/10",
            "date": "2019/10/30",
            "balance": 1,
            "point": 1,
            "statusCode": {
                "4000": {
                    "sms": 1,
                    "lms": 1,
                    "mms": 1,
                    "ata": 1,
                    "cta": 1
                }
            },
            "refund": {
                "balance": 100,
                "point": 10
            },
            "total": {
                "total": 5,
                "sms": 1,
                "lms": 1,
                "mms": 1,
                "ata": 1,
                "cta": 1,
                "cti": 0
            },
            "successed": {
                "total": 5,
                "sms": 1,
                "lms": 1,
                "mms": 1,
                "ata": 1,
                "cta": 1,
                "cti": 0
            },
            "failed": {
                "total": 0,
                "sms": 0,
                "lms": 0,
                "mms": 0,
                "ata": 0,
                "cta": 0,
                "cti": 0
            }
        }
    ],
    "total": {
        "total": 5,
        "sms": 1,
        "lms": 1,
        "mms": 1,
        "ata": 1,
        "cta": 1,
        "cti": 0
    },
    "successed": {
        "total": 5,
        "sms": 1,
        "lms": 1,
        "mms": 1,
        "ata": 1,
        "cta": 1,
        "cti": 0
    },
    "failed": {
        "total": 0,
        "sms": 0,
        "lms": 0,
        "mms": 0,
        "ata": 0,
        "cta": 0,
        "cti": 0
    },
    "dailyBalanceAvg": 1,
    "dailyPointAvg": 1,
    "dailyTotalCountAvg": 5,
    "dailyFailedCountAvg": 0,
    "dailySuccessedCountAvg": 5
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
  url: 'http://api.solapi.com/messages/v4/statistics'
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
  url: 'http://api.solapi.com/messages/v4/statistics'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/statistics";

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

url = "http://api.solapi.com/messages/v4/statistics"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4"
}

response = requests.get(url, headers=headers)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X GET \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	http://api.solapi.com/messages/v4/statistics
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/statistics")

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
  uri := "http://api.solapi.com/messages/v4/statistics"

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
    String targetUrl = "http://api.solapi.com/messages/v4/statistics";

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

---

> 문서 생성일 : 2019-10-29

