# 메시지 조회

## Request

```text
GET https://api.solapi.com/messages/v4/list
```

메시지의 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview#authorization)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| criteria | `string` |  | eq | 검색 조건에 사용되는 필드명 criteria 의 값은 'key1,key2,key3' 과 같이 ,\(콤마\) 로 구분되며 cond, value 와 함께 사용됩니다. - messageId - 메시지 아이디 입니다. - groupId - 그룹 아이디 입니다. - to - 수신 번호 입니다. - from - 발신 번호 입니다. - type - 문자 메시지의 타입 입니다.  \(SMS, LMS, MMS, ATA, CTA, CTI\) - dateCreated - 그룹 생성일 입니다. - dateUpdated - 그룹 정보를 변경한 마지막 시각 입니다. - replacement - 대체 발송 여부 입니다. \(true, false\) - statusCode - 문자 메시지의 상태 코드 입니다. |
| cond | `string` |  | eq | 검색 조건에 사용되는 연산자 criteria 와 같이 'cond1,cond2' 와 같이 ,\(콤마\)로 구분되며, criteria,value 와 함께 사용됩니다. - eq - 같음 \(=\) - ne - 같지 않음 \(!=\) - gt - 보다 큼 \(&gt;\) - gte - 보다 크거나 같음 \(&gt;=\) - lt - 보다 작음 \(&lt;\) - lte - 보다 작거나 같음 \(&lt;=\) |
| value | `string` |  | eq | 검색 값 criteria , cond 값에 대응하는 value 입니다. criteria='messageId,statusCode' cond='eq,eq' 일 경우 groupId 에 대응하는 value 값을 찾고 status 에 대응하는 값을 찾는 조건 입니다. e.g - value='메시지아이디,2000' |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| dateType | `string` |  | eq | 설명 없음 |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

## Samples

### /messages/v4/list \(메시지 조회\)

> **Sample Request**

```text
http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```

> **Sample Response**

```javascript
{
    "startKey": null,
    "limit": 20,
    "messageList": {
        "M4V20180307110044DTYYJBBYLPQZIB1": {
            "_id": "M4V20180307110044DTYYJBBYLPQZIB1",
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
            "statusCode": "TEST1000",
            "networkCode": null,
            "log": [],
            "replacement": false,
            "autoTypeDetect": true,
            "routedQueue": null,
            "messageId": "M4V20180307110044DTYYJBBYLPQZIB1",
            "groupId": "G4V20180307105937H3PTASXMNJG2JIO",
            "accountId": "12925149",
            "text": "text",
            "from": "01000000000",
            "to": "01000000000",
            "customFields": {},
            "dateCreated": "2020-09-09T05:23:20.686Z",
            "dateUpdated": "2020-09-09T05:23:20.686Z",
            "reason": null,
            "networkName": "ETC"
        }
    }
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
  url:
    'http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq'
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
$url = "http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

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

url = "http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"
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
    http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq")

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
  uri := "http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq"

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
    String targetUrl = "http://api.solapi.com/messages/v4/list?criteria=messageId&value=M4V20180307110044DTYYJBBYLPQZIB1&cond=eq";

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

> 문서 생성일 : 2020-09-09

