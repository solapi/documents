> 문서 생성일 : 2019-08-07

# 일별 통계 내역 조회

#### Request
```
GET https://api.solapi.com/messages/v4/statistics/daily
```

일별 통계 내역을 조회합니다.

##### Authorization 인증 필요 [[?]](https://docs.solapi.com/authentication/authentication)

| 계정 권한 | 회원 권한 | 계정 상태 | 회원 상태 | 계정 인증 |
| :- | :- | :- | :- | :-: |
| `message:read` | `role-message:read` | `ACTIVE` | `ACTIVE` | O |

##### Query Params
| Name | Type | Required | Allowed Operator [[?]](https://docs.solapi.com/api-reference/api-reference#operator) | Description |
| :--- | :--: | :------: | :--------------: | :---------- |
| offset | `number` |  | eq | 검색 시작점 |
| limit | `number` |  | eq | 한 페이지에 불러옥 목록 개수 |
| taxIssued | `boolean` |  | eq | 세금 계산서 발행 여부 |
| profitSettlement | `boolean` |  | eq | 수익 정산 여부 |
| startDate | `date` |  | eq | 검색 시작 날짜 |
| endDate | `date` |  | eq | 검색 끝 날짜 |

---

#### Samples

##### 내역 가져오기

> **Sample Request**

```
http://api.solapi.com/messages/v4/statistics/daily
```

> **Sample Response**

```json
[
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-15T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-14T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-13T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-12T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-11T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-10T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-09T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-08T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-07T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-06T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-05T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-04T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-03T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-02T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-07-01T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-06-30T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-06-29T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-06-28T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": false,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-06-27T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    },
    {
        "refund": {
            "balance": 0,
            "point": 0
        },
        "appId": null,
        "balance": 10,
        "point": 100,
        "taxIssued": false,
        "profitSettlement": true,
        "profit": 0,
        "accountId": "12925149",
        "date": "2019-06-26T15:00:00.000Z",
        "count": {
            "4000": {
                "sms": 10
            }
        }
    }
]
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
  url: 'http://api.solapi.com/messages/v4/statistics/daily'
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
  url: 'http://api.solapi.com/messages/v4/statistics/daily'
};

$.ajax(options).done(function(response) {
  console.log(response);
});

```
{% endtab %}

{% tab title="PHP" %}

```php
<?php
$url = "http://api.solapi.com/messages/v4/statistics/daily";

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

url = "http://api.solapi.com/messages/v4/statistics/daily"
headers = {
  "Authorization": "Bearer eyJhbGciOiJI..."
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
	-H 'Authorization: Bearer eyJhbGciOiJI...' \
	http://api.solapi.com/messages/v4/statistics/daily
```
{% endtab %}

{% tab title="RUBY" %}

```ruby
require 'net/http'
require 'uri'
require 'json'

uri = URI.parse("http://api.solapi.com/messages/v4/statistics/daily")

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
  uri := "http://api.solapi.com/messages/v4/statistics/daily"

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
    String targetUrl = "http://api.solapi.com/messages/v4/statistics/daily";

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

---

