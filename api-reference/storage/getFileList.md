# 파일 목록 조회

## Request
```
GET https://api.solapi.com/storage/v1/files
```

한 계정이 가지고 있는 파일들의 목록을 조회합니다.

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `storage:read` |  | `ACTIVE` | `ACTIVE` |  |

### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
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
| type | `string` |  | eq | 설명 없음 |
| useDaou | `boolean` |  | eq | 설명 없음 |
| useBiztalk | `boolean` |  | eq | 설명 없음 |

---

## Samples

### getFileList.spec.js

> **Sample Request**

```
http://api.solapi.com/storage/v1/files
```

> **Sample Response**

```json
{
    "fileList": [
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름34",
            "link": null,
            "fileId": "FILEID191113003354359MC8iTyqIIqR",
            "accountId": "19013037529548",
            "name": "파일 이름34",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354359CGTOy67atgM",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354359hCd05HXWxC4"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.360Z",
            "dateUpdated": "2019-11-13T00:33:54.360Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름33",
            "link": null,
            "fileId": "FILEID191113003354354qpyj5aZA59y",
            "accountId": "19013037529548",
            "name": "파일 이름33",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354354mcyr1uDvTll",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354354JWTZ4eNbc5c"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.355Z",
            "dateUpdated": "2019-11-13T00:33:54.355Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름32",
            "link": null,
            "fileId": "FILEID191113003354350o1lwe5NU7cE",
            "accountId": "19013037529548",
            "name": "파일 이름32",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354350AEaz5akIAH9",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354350l924zkpSbr2"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.351Z",
            "dateUpdated": "2019-11-13T00:33:54.351Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름31",
            "link": null,
            "fileId": "FILEID1911130033543441FL78OWjRby",
            "accountId": "19013037529548",
            "name": "파일 이름31",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354345Fz3EPfxGVhY",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354345Z2zo42aQ5gL"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.346Z",
            "dateUpdated": "2019-11-13T00:33:54.346Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름30",
            "link": null,
            "fileId": "FILEID1911130033543404zt4Edu3Pn8",
            "accountId": "19013037529548",
            "name": "파일 이름30",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354340OcqjIWDbE5R",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354340kArDEyTE7y8"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.341Z",
            "dateUpdated": "2019-11-13T00:33:54.341Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름29",
            "link": null,
            "fileId": "FILEID1911130033543341zfwJSQoLIy",
            "accountId": "19013037529548",
            "name": "파일 이름29",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354334kMNerHud9h5",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354334Bur6UXh5Xc6"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.335Z",
            "dateUpdated": "2019-11-13T00:33:54.335Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름28",
            "link": null,
            "fileId": "FILEID191113003354329rjIJimOH7E3",
            "accountId": "19013037529548",
            "name": "파일 이름28",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354329s4mgN8pZo1R",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354329P4qD6dIhp03"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.331Z",
            "dateUpdated": "2019-11-13T00:33:54.331Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름27",
            "link": null,
            "fileId": "FILEID1911130033543242cN3HP8Ljjm",
            "accountId": "19013037529548",
            "name": "파일 이름27",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354324zH17uNvkmvk",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354324zpzuwCoTqSB"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.325Z",
            "dateUpdated": "2019-11-13T00:33:54.325Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름26",
            "link": null,
            "fileId": "FILEID191113003354320zW2x6Giw0RJ",
            "accountId": "19013037529548",
            "name": "파일 이름26",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354320qczlTp5SCev",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51911130033543200AX62wJj3Uz"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.321Z",
            "dateUpdated": "2019-11-13T00:33:54.321Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름25",
            "link": null,
            "fileId": "FILEID191113003354315Z03EZ6hmcrd",
            "accountId": "19013037529548",
            "name": "파일 이름25",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354315CTzKB1BWM60",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354315siAcj3mWPP3"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.316Z",
            "dateUpdated": "2019-11-13T00:33:54.316Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름24",
            "link": null,
            "fileId": "FILEID191113003354309LiTomTe3F6n",
            "accountId": "19013037529548",
            "name": "파일 이름24",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354309ZvaDCKiWUXn",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354309aBwoEXIR3eL"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.310Z",
            "dateUpdated": "2019-11-13T00:33:54.310Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름23",
            "link": null,
            "fileId": "FILEID1911130033543044tqrjzNZ5Ys",
            "accountId": "19013037529548",
            "name": "파일 이름23",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354304OYWoXNX8EfI",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354304kj5ucvruOnM"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.305Z",
            "dateUpdated": "2019-11-13T00:33:54.305Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름22",
            "link": null,
            "fileId": "FILEID191113003354299ZZzIy9Be020",
            "accountId": "19013037529548",
            "name": "파일 이름22",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354300OKll5qpFQ1f",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354300uz2cQWafpgP"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.301Z",
            "dateUpdated": "2019-11-13T00:33:54.301Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름21",
            "link": null,
            "fileId": "FILEID191113003354295MBHSlgpBfW2",
            "accountId": "19013037529548",
            "name": "파일 이름21",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354295xJdFOh6B38T",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354295yxgE7CbMb7K"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.296Z",
            "dateUpdated": "2019-11-13T00:33:54.296Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": null
            },
            "type": "DOCUMENT",
            "originalName": "파일 원본 이름20",
            "link": null,
            "fileId": "FILEID1911130033542918XVmowe8Q3x",
            "accountId": "19013037529548",
            "name": "파일 이름20",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354291aVFY3741qUf",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354291BcvDJJQYnG8"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.292Z",
            "dateUpdated": "2019-11-13T00:33:54.292Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름19",
            "link": null,
            "fileId": "FILEID191113003354286mkpFdO5rvmj",
            "accountId": "19013037529548",
            "name": "파일 이름19",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354286egUoqq5dOAq",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354286c3wvE2S1u2i"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.287Z",
            "dateUpdated": "2019-11-13T00:33:54.287Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름18",
            "link": null,
            "fileId": "FILEID191113003354281giTl0kpln9m",
            "accountId": "19013037529548",
            "name": "파일 이름18",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354281w7IgpwxYfso",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354281f0Q6DRGrMWN"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.283Z",
            "dateUpdated": "2019-11-13T00:33:54.283Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름17",
            "link": null,
            "fileId": "FILEID191113003354276QLFa7LfNrBA",
            "accountId": "19013037529548",
            "name": "파일 이름17",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354276OTmFDFEdPUW",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354276HF65AH0tzoQ"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.277Z",
            "dateUpdated": "2019-11-13T00:33:54.277Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름16",
            "link": null,
            "fileId": "FILEID191113003354272gMnBaizP3Eu",
            "accountId": "19013037529548",
            "name": "파일 이름16",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354272vYI46GeasHA",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID5191113003354272FBoBxMn0T7u"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.273Z",
            "dateUpdated": "2019-11-13T00:33:54.273Z"
        },
        {
            "kakao": {
                "daou": null,
                "biztalk": "https://solapi.com"
            },
            "type": "KAKAO",
            "originalName": "파일 원본 이름15",
            "link": null,
            "fileId": "FILEID191113003354267K6hc7pzC1gT",
            "accountId": "19013037529548",
            "name": "파일 이름15",
            "url": "https://coolsms.co.kr/godori",
            "references": [
                {
                    "handleKey": "REFERE191113003354267P7jfERiIkCp",
                    "category": "SENDERID_APPROVAL",
                    "refId": "REFID51911130033542675hBnT5wxCny"
                }
            ],
            "dateCreated": "2019-11-13T00:33:54.268Z",
            "dateUpdated": "2019-11-13T00:33:54.268Z"
        }
    ],
    "startKey": null,
    "nextKey": "FILEID191113003354262dDhAeWn5Ww3"
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
    Authorization:
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4'
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

url = "http://api.solapi.com/storage/v1/files"
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
  uri := "http://api.solapi.com/storage/v1/files"

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
    String targetUrl = "http://api.solapi.com/storage/v1/files";

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

> 문서 생성일 : 2019-11-13

