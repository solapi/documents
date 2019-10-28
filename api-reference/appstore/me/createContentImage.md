# 컨텐츠 이미지 업로드

## Request
```
POST https://api.solapi.com/appstore/v2/me/apps/:appId/images/screenshots
```

800x600 사이즈의 PNG, JPG, GIF 포맷의 컨텐츠 이미지 업로드

### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `appstore:write` | `role-appstore:write` | `ACTIVE` | `ACTIVE` | O |

### Path Parameters

| Name | Description |
| :--: | :---------: |
| :appId | 앱 아이디 |

### Request Structure
```json
{
    "image": "string",
    "name": "string"
}
```

### Body Params
| Name | Type | Required | Description |
| :--- | :--: | :------: | :---------- |
| image | `string` | O | 800x600 사이즈의 PNG, JPG, GIF 포맷의 컨텐츠 이미지 |
| name | `string` |  | 사진 이름 |


---

## Samples

### (Private) 컨텐츠 이미지 업로드

> **Sample Request**

```json
{
    "image": "iVBORw0KGgoAAAANSUhEUgAAAyAAAAJYBAMAAABoWJ9DAAAAG1BMVEXm2Ur////p3WDv543y7KT49dH7+uj18Lvs4nczyFreAAAACXBIWXMAAA7EAAAOxAGVKw4bAAAKfklEQVR4nO3dy38bxR0AcCH5oWPVEtOjHcDJEZe2cIz7KY9jVQjpMWpJ4FgBoT3aBfJ3d1f73nnYwb6s/f1eUHYt/X47szOzj9llNgMAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAuGfmD49Tq9Jr5g9vN4U3D5PObdLe/WSzWq1e/nARWfWqWHX0ZWTN/KOvii+9+Px2Ulh+VqbwIkwhEyad28T9adX473jVL/WKo7+M1yzX9aqvj28hhUebJoUvhz+XCZPObeLOV51/DVf90q35brimLajV6p3jG6fwfi+FB9cMk85t4l6Xm/Ti2X9e7bb97/1Vh7sCevZ0t/t+MPjWtlz09FXZnax+d9MU9nY7+tNXu0BH1wuTyW3aysJ45w+7j++WVXLRrZoX/36wW/Vzsdlv979V7tJfHBcflp8Wn57cLIUyzlE1SPz046BC0mEyuU3cttdPzYve6/fdqtNimy+qj4tiq//drZkX//xH/fnPRYXeLIXXXZzZ7L2X1wqTzm3i9ga7V7nfXbT/2vT6gsPB3x30O5DtDZvIcrM66oLO5tcKk85t4i4HnVRZP8+bz8V2/rNbc9bvqbero+P2H4sbjiKno5Grkw6TyW3iNqPCPO92trN+cZTl8dve515xlOXR+8M3tk51eZkw6dwmbjnufve7QXXTH0/KqmrL7SBoVjfoww+T386ESec2cUVpDBfM29a/Nxoa9rviOR/12eth8byZy+GZR086TCa3iTsIdq11sxueDM8Ieo1p3htodi5vsoOuB/1STyZMOrepOwn27fPV35oPo6F623TUe+Mx9PAGg8giOSBnwqRzm7rLYEMum91yM9o/i8qre5CD0f5Z7stPfm0G+8keKxMmndvUXa5+M1pyUi9ZBntuO95fBoe563EBvUkGqfEnHSaT29TFKuT57r9hN7RoRs6wfzj79aP6tukiI2tSYTK5Td1Jsss6CLqStsfYBGV4gx4jfU6XDpPJberCQf2sLoaT8PR7Xa2ah2UYGwjmx2G4cNEi2ddkwqRzm7yDYNfe1rvaWXjccl71b4vwmGpvfDpTOA2PZg/Dju0wecScCZPObfIOI0cyF7sP23Ccrsff4Du7UfZitGi+6V/cmNW/Of6rYo9IjT6ZMOncJi84XmmLIdIHvFX1FLH+Kexe9lbBCV8xFge/GR5VNDJh0rlN3/g8uT3WjIyS9Wn9W5ERfBOeKQ8u1SaWdENWKBMmndv0ja4kzZtDm8iQWuzhu7+NDKmxg9fDcRMJFlRffFJ9ePzhXz/8X39NOkwmt+kbXak9bXbiyKhQ/O2uO4t11+eRM8Nxg4g1kGKf35Xtz9Wsk296MdNhMrndAevVg+P2H8v2snbkGKdcVv4ncoxTLAuHglGLiDaQ2S7M/NNm/sjRk95PpsJkcrsD9vv31Lftvhc7kF1WBRE7wgyvic3GTSLaQOa7ML2JSEdtZ5QOk8ntLth2EwmKgvm2/hjrAuquItY9RY86B20i3kCWZZhyItKzjx8+/OnHVW8mQzpMJre7YNFMC1xue8URGyTrc5TY1afwjH82GzaKaAMpgj8od/hm8uF7q67a0mEyud0Jj8oZZ98/LifXdrNxEhtddijxkoqdBvRaRbyBFJXxoGgKXT9V5NLUWzpMJre74VE7W/OiXRa9TVFtdOyyUeK8bNsr3lgDKa+cLAZTQV+3J4/pMJnc7ohFddDZO9wqNjpyotVUSHi7NFEhbbtINJCyQi4HJ4DFiVAdOB0mk9vdsGyOOqu5mTu3UyFtw0g0kCLM25thSZ42g8H9rZBd+zh6NZxHntjoJ7NUScVviNQtI9VAyoPu0TeXzdSGdJhMbnfBXjmYf14+GdOvkVuqkLpppBpIOfVqPFRs68Z2XyukODlvHoYpj3ubhn9LXVbVNpINZFchx8NFJ/WQfV+7rN554W72e72tt1Uhu8aRbCBlhYzj7NVVdE8r5LA7OZ9V106qHuR2DnurAC+SDaSskPE1l+b2+D097B3NdC46sGpjb+XEcKfsB1MNpKyQ4MfqmrifJ4aH47HwtF4QuYHaXTp5HqyKXzppQiQbSFkhT8bL6quK6TCZ3CbvbHx0NK8vwCcu4B3PUlf90lM5N5myOoisq38rHSaT2+SFc5/qW4ix+wv1fYjYvY/YzYtatoXsR8qxbm3pMJncpi4+1eYivuZNb1DVsmNIrELqA4R7eYMqnJZVdsbl4eYt3MKtFA3km3QTCZ5PmbUVci9v4YYzSZvBNHbUsp+e5JCeOJg/D9mLtpC382EyuU3dWWTHrruKTXKqTaRZxaYBVa44U4/1PnULyYRJ5zZ120g51mPqTSfKtRGy17Jivc/VYe7uRLl15IpcvWmROQaXzRFx0O8n72hfdbU31vvUfVUmTDq3qctUSOSRj26y9cVoTWweyM5V90NivU9dtpkw6dymLlMhkUc+uscRxt9KDalX3jGM9T71IJYJk85t6jIVEpZxW0Lhxqce2LnynnqxZ0eeLHh+RZhMbhOXGdTDA9J2SViIkWItXT3rJPIgYXvElg6TyW3iYudzyR6jfZAsbA/hFZidq+dlxZ9O++CKMJncJi52TXDb9hjPx39cF1DwyOsy3mFcY+ZiufhiuKTd2TNh0rlNXORW+LyZDh9cCF43tbcYl3/sitTsWnN7u3CtdmfPhEnnNnGRVzC0u+zBaF2vfDajzQ/Kp/mlq2e/h+9J6d7SkA6TyW3aIu8IuWw6isVo3WlXCGfD6xTzcclVrvV8SBev+bHuDSfpMJncJm49PsiZdy/QGq1bd81gf3h+vR/dP6/3BFX55UHZ9m5ZZcKkc5u4k/Gli9PuJvfwZXOHvXfzLAevZix3/chPX+8Zw7JFDAqzd5M/Eyad28QtVsEkh7bQ9gav7tv2e4Xzfj0eRt/nds2ncHcvius1kff7ZZsOk8lt4s4HL08upwF1W73tFdX7gxI47NVj+eLMyKXe+TrynHr/ZZeN8vGQdvFi029FmTDp3CZu0bwZt1ROXRyWR/PM36PR24qLP/y6+lTWYbQ49iNvcvg28nflb7VvfF0P21U6TCa3iSufJ3vw+XHxafnRZvRq6/J2+PcXs9njT8Yvli5nLrzzcVFOP6+TxXF8rUXVq5yPygwefzR6JiIXJp3bxM231cOWL6tnRAYvf6+eGzkKHh6Z7d5rXKi+k3jJ67W9XnVhRpWbDpPJbeLqGql8PVzXPlvVe+os+NboBf6/wqddAqP36mfCpHObvPZ/V3EU/O8q3ltXax4E2zz/pP7SF7eYQe+JoavDpHObvPkfX3318sWz3UgSrirXxL717mdfvXz6w8WtZLD87Ombh8nkBgAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAHAz/wd5PtJ683iH3gAAAABJRU5ErkJggg=="
}
```

> **Sample Response**

```json
{
    "appId": "dMuHVUkTfoqL",
    "imageName": "HHV6MdklBGIQCn0.png",
    "imageUrl": "https://coolsms-apps-test.s3.ap-northeast-2.amazonaws.com/dMuHVUkTfoqL/screenshots/HHV6MdklBGIQCn0.png",
    "originalName": "HHV6MdklBGIQCn0.png"
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    image: 'iVBORw0KGgoAAAANSUhEUgAAAyA...'
  },
  method: 'POST',
  json: true,
  url:
    'http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots'
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
      'HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4',
    'Content-Type': 'application/json'
  },
  body: {
    image: 'iVBORw0KGgoAAAANSUhEUgAAAyA...'
  },
  method: 'POST',
  url:
    'http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots";
$data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA..."}';

$options = array(
    'http' => array(
        'header'  => "Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4\r\n" . "Content-Type: application/json\r\n",
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

url = "http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots"
headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA..."}'

response = requests.post(url, headers=headers, data=data)
print(response.status_code)
print(response.text)

```
{% endtab %}

{% tab title="CURL" %}

```curl
#!/bin/bash
curl -X POST \
	-H 'Authorization: HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4' \
	-H 'Content-Type: application/json' \
	-d '{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA..."}' \
	http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots")

headers = {
  "Authorization": "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4",
  "Content-Type": "application/json"
}
data = {
  "image": "iVBORw0KGgoAAAANSUhEUgAAAyA..."
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
  uri := "http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots"
  data := strings.NewReader(`{"image":"iVBORw0KGgoAAAANSUhEUgAAAyA..."}`)

  req, err := http.NewRequest("POST", uri, data)
  if err != nil { panic(err) }

  req.Header.Set("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4")
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
    String targetUrl = "http://api.solapi.com/appstore/v2/me/apps/dMuHVUkTfoqL/images/screenshots";
    String parameters = "{\"image\":\"iVBORw0KGgoAAAANSUhEUgAAAyA...\"}";

    URL url = new URL(targetUrl);
    HttpURLConnection con = (HttpURLConnection) url.openConnection();

    con.setRequestMethod("POST");

    con.setRequestProperty("Authorization", "HMAC-SHA256 apiKey=NCSAYU7YDBXYORXC, date=2019-07-01T00:41:48Z, salt=jqsba2jxjnrjor, signature=1779eac71a24cbeeadfa7263cb84b7ea0af1714f5c0270aa30ffd34600e363b4");
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

> 문서 생성일 : 2019-10-28

