# 그룹 삭제

생성된 그룹을 삭제하며 해당 그룹에 등록된 모든 메시지도 함께 제거됩니다.

## Resource URL

`https://solapi.com/GroupMessage/3/deleteGroups`

## Request Syntax

```text
{
  "groups": [
    {
      "groupId": "String"
    },
    ...
  ],
}
```

## Request Sample

$ curl -X POST [https://solapi.com/GroupMessage/3/deleteGroups](https://solapi.com/GroupMessage/3/deleteGroups)  --header "Authorization : HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]"  -d '{ "groups" : \[ { "groupId": "\[GROUP\_ID\]" } \] }'

request\( { url: "[https://solapi.com/GroupMessage/3/deleteGroups](https://solapi.com/GroupMessage/3/deleteGroups)", method: 'post', headers: { 'Authorization': `HMAC-SHA256 ApiKey=NCSGMRA9DY2DUXYH, Date=[DATE], Salt=[UNIQID], Signature=[SIGNATURE]` }, json: { "groups" : \[ { "groupId": "\[GROUP\_ID\]" } \] } } \)

conn = HTTPSConnection\('solapi.com', '443'\) conn.request\( "POST", "/GroupMessage/3/deleteGroups", json.dumps\( { "groups" : \[ { "groupId": "G311123918RABMQZZF9EFO6MX" } \] } \), {"Authorization":"HMAC-SHA256 ApiKey=NCSGMRA9DY2DUXYH, Date="+timestamp+", Salt="+salt+", Signature="+signature.hexdigest\(\)+""}\) conn.close\(\)

&lt;?php $ch = curl\_init\(\); curl\_setopt\($ch, CURLOPT\_URL,"[https://solapi.com/GroupMessage/3/deleteGroups](https://solapi.com/GroupMessage/3/deleteGroups)"\); curl\_setopt\($ch, CURLOPT\_POST, 1\); curl\_setopt\($ch, CURLOPT\_HTTPHEADER, array\( 'Authorization: HMAC-SHA256 ApiKey=\[API\_KEY\], Date=\[DATE\], Salt=\[UNIQID\], Signature=\[SIGNATURE\]' \)\); curl\_setopt\($ch, CURLOPT\_POSTFIELDS, json\_encode\( '{ "groups" : \[ { "groupId": "\[GROUP\_ID\]" } \] }' \)\); curl\_exec\($ch\); curl\_close\($ch\); ?&gt;

## Required Parameters

## Optional Parameters

옵션사항이 없습니다

## Limits

하나의 요청에 삭제할 수 있는 그룹 수는 최대 10개 입니다.

## Response Syntax

```text
{
  "errorCount": Number,
  "resultList": [
    {
      "groupId": "String",
      "resultCode": "String"
    }
  ]
}
```

## Response Sample

```javascript
{
    "errorCount": 0,
    "resultList": [
        {
            "groupId": "G3V201709120949162NQOITCYLRGVCUK",
            "resultCode": "Success"
        }
    ]
}
```

errorCount

* 오류 발생 건수
* TooManyGroups
  * 입력 가능한 그룹 수 10개를 초과하였습니다.
  * HTTP Status Code: 413

