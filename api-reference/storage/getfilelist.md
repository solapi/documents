# 파일 목록 조회

## Request

```text
GET https://api.solapi.com/storage/v1/files
```

한 계정이 가지고 있는 파일들의 목록을 조회합니다.

### Authorization 인증 필요 [\[?\]](https://docs.solapi.com/authentication/overview)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :--- | :--- | :--- | :--- | :---: |
| `storage:read` |  | `ACTIVE` | `ACTIVE` |  |

### Query Params

| Name | Type | Required | Allowed Operator [\[?\]](https://docs.solapi.com/api-reference/overview#operator) | Description |
| :--- | :---: | :---: | :---: | :--- |
| fileId | `string` |  | eq | 파일 고유 아이디 |
| name | `string` |  | eq | 이름 |
| url | `string` |  | eq | 파일 주소 |
| originalName | `string` |  | eq | 파일 이름 |
| handleKey | `string` |  | eq | 참조의 핸들키 |
| category | `string` |  | eq | 참조 이름 |
| refId | `string` |  | eq | 참조 대상의 리소스 아이디 |
| dateCreated | `date` |  | eq | 최초 생성 날짜 |
| dateUpdated | `date` |  | eq | 최초 생성 날짜 |
| startKey | `string` |  | eq | 현재 목록을 불러올 기준이 되는 키 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |

## Samples

### 리스트 가져오기

> **Sample Request**

```text
{}
```

> **Sample Response**

```javascript
{
    "fileList": [
        {
            "originalName": "파일 원본 이름34",
            "fileId": "FILEID190726085541739xMsgTkFXMZN",
            "accountId": "19013037529548",
            "name": "파일 이름34",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541740ffqAVtTyQxM",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541740ohdnedMmggd"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.740Z",
            "dateUpdated": "2019-07-26T07:55:41.740Z"
        },
        {
            "originalName": "파일 원본 이름33",
            "fileId": "FILEID190726085541732lflmAuobyrh",
            "accountId": "19013037529548",
            "name": "파일 이름33",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541733iV8qurGlGBZ",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541733SZagjBv5tzm"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.736Z",
            "dateUpdated": "2019-07-26T07:55:41.736Z"
        },
        {
            "originalName": "파일 원본 이름32",
            "fileId": "FILEID190726085541729kKGnIPS0o8u",
            "accountId": "19013037529548",
            "name": "파일 이름32",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541729JlLNfu894eY",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541729VkS4IlKiNTX"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.730Z",
            "dateUpdated": "2019-07-26T07:55:41.730Z"
        },
        {
            "originalName": "파일 원본 이름31",
            "fileId": "FILEID190726085541726bmUb3B2lLOw",
            "accountId": "19013037529548",
            "name": "파일 이름31",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541726kORZ9zWHMpz",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541726dwEdIiDlzgT"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.726Z",
            "dateUpdated": "2019-07-26T07:55:41.726Z"
        },
        {
            "originalName": "파일 원본 이름30",
            "fileId": "FILEID190726085541722iUP1StQfjDV",
            "accountId": "19013037529548",
            "name": "파일 이름30",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE1907260855417225gzlmKxvKCD",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541722iBYpB30xcbw"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.723Z",
            "dateUpdated": "2019-07-26T07:55:41.723Z"
        },
        {
            "originalName": "파일 원본 이름29",
            "fileId": "FILEID190726085541719ZUoYLZ59cCh",
            "accountId": "19013037529548",
            "name": "파일 이름29",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541719tD3QezBzP0H",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541719WOSmxCUWXHT"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.720Z",
            "dateUpdated": "2019-07-26T07:55:41.720Z"
        },
        {
            "originalName": "파일 원본 이름28",
            "fileId": "FILEID190726085541715NQzvGU5hbRg",
            "accountId": "19013037529548",
            "name": "파일 이름28",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541715NUs5Zduxu3f",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541715EnNBqpKU9Ho"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.716Z",
            "dateUpdated": "2019-07-26T07:55:41.716Z"
        },
        {
            "originalName": "파일 원본 이름27",
            "fileId": "FILEID1907260855417112vaBSsxWKIc",
            "accountId": "19013037529548",
            "name": "파일 이름27",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541711SRxyNLWdCmf",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541711NZSRXTA2R2t"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.712Z",
            "dateUpdated": "2019-07-26T07:55:41.712Z"
        },
        {
            "originalName": "파일 원본 이름26",
            "fileId": "FILEID190726085541707QX4j3zMBxUe",
            "accountId": "19013037529548",
            "name": "파일 이름26",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541707gdFbBY6y2Jc",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541707HlTe6HjMXbS"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.708Z",
            "dateUpdated": "2019-07-26T07:55:41.708Z"
        },
        {
            "originalName": "파일 원본 이름25",
            "fileId": "FILEID190726085541702U1r7rohMerF",
            "accountId": "19013037529548",
            "name": "파일 이름25",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE19072608554170272hVSwxcxJQ",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541702a2DBSXajBNp"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.703Z",
            "dateUpdated": "2019-07-26T07:55:41.703Z"
        },
        {
            "originalName": "파일 원본 이름24",
            "fileId": "FILEID190726085541698fosT3IcExnq",
            "accountId": "19013037529548",
            "name": "파일 이름24",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541698ZwhLvxIuOCa",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID519072608554169971XcxO5pLZR"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.699Z",
            "dateUpdated": "2019-07-26T07:55:41.699Z"
        },
        {
            "originalName": "파일 원본 이름23",
            "fileId": "FILEID190726085541694iJjUouOU8wU",
            "accountId": "19013037529548",
            "name": "파일 이름23",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541694K1gYNzPH0GS",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51907260855416943WvElLdnIvQ"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.695Z",
            "dateUpdated": "2019-07-26T07:55:41.695Z"
        },
        {
            "originalName": "파일 원본 이름22",
            "fileId": "FILEID190726085541690HSCqbXLUNS9",
            "accountId": "19013037529548",
            "name": "파일 이름22",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541691itSaLd4Qo4L",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541691yN1OXR7UO9k"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.691Z",
            "dateUpdated": "2019-07-26T07:55:41.691Z"
        },
        {
            "originalName": "파일 원본 이름21",
            "fileId": "FILEID190726085541687li0chkUPUYr",
            "accountId": "19013037529548",
            "name": "파일 이름21",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE1907260855416871gJICDrCWdR",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541687AvLRlITM1dB"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.688Z",
            "dateUpdated": "2019-07-26T07:55:41.688Z"
        },
        {
            "originalName": "파일 원본 이름20",
            "fileId": "FILEID190726085541683RAUXULtzHA6",
            "accountId": "19013037529548",
            "name": "파일 이름20",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541684OD4VxAIyNgW",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541684VOYVbFNAfyC"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.684Z",
            "dateUpdated": "2019-07-26T07:55:41.684Z"
        },
        {
            "originalName": "파일 원본 이름19",
            "fileId": "FILEID1907260855416803sJVwFZnEfj",
            "accountId": "19013037529548",
            "name": "파일 이름19",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541680JaUUCFTVpxo",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541680vWC0iBWE6Kk"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.681Z",
            "dateUpdated": "2019-07-26T07:55:41.681Z"
        },
        {
            "originalName": "파일 원본 이름18",
            "fileId": "FILEID190726085541676sTW5LkBTQBa",
            "accountId": "19013037529548",
            "name": "파일 이름18",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541676gelpu8zx0Ph",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541677XYvXp2roySS"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.677Z",
            "dateUpdated": "2019-07-26T07:55:41.677Z"
        },
        {
            "originalName": "파일 원본 이름17",
            "fileId": "FILEID190726085541673OBDiBmhRx1c",
            "accountId": "19013037529548",
            "name": "파일 이름17",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541673jxoFdsImCKk",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541673tqbGi06NAko"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.674Z",
            "dateUpdated": "2019-07-26T07:55:41.674Z"
        },
        {
            "originalName": "파일 원본 이름16",
            "fileId": "FILEID190726085541669yxwcSHjDvdS",
            "accountId": "19013037529548",
            "name": "파일 이름16",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541669KktbtPZUx4M",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541669nKOK4Fqk5DX"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.670Z",
            "dateUpdated": "2019-07-26T07:55:41.670Z"
        },
        {
            "originalName": "파일 원본 이름15",
            "fileId": "FILEID190726085541665eNpv6aG3Dc7",
            "accountId": "19013037529548",
            "name": "파일 이름15",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE190726085541665LtH40JzjgtP",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5190726085541665ReNg4Og1HiN"
                }
            ],
            "dateCreated": "2019-07-26T07:55:41.666Z",
            "dateUpdated": "2019-07-26T07:55:41.666Z"
        }
    ],
    "startKey": null,
    "nextKey": "FILEID190726085541661RnK4lcNPCHH"
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
  url: 'http://api.solapi.com/storage/v1/files'
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
  url: 'http://api.solapi.com/storage/v1/files'
};

$.ajax(options).done(function(response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="PHP" %}
```php
<?php
$url = "http://api.solapi.com/storage/v1/files";

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

url = "http://api.solapi.com/storage/v1/files"
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
    http://api.solapi.com/storage/v1/files
```
{% endtab %}

{% tab title="RUBY" %}
```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/storage/v1/files")

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
  uri := "http://api.solapi.com/storage/v1/files"

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
    String targetUrl = "http://api.solapi.com/storage/v1/files";

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

