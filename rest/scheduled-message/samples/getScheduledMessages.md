{% codetabs name="CURL", type="bash" -%}
$ curl -X POST https://solapi.com/SimpleMessage/3/getScheduledMessages \
    --header "Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{
          "offset": 0,
          "limit": 20
        }'
{%- language name="JavaScript", type="javascript" -%}
request(
  {
    url: "https://solapi.com/SimpleMessage/3/getScheduledMessages",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "offset": 0,
      "limit": 20
    }
  }
)
{%- language name="Python", type="python" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/SimpleMessage/3/getScheduledMessages",
  json.dumps(
    {
      "offset": 0,
      "limit": 20
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/SimpleMessage/3/getScheduledMessages");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
  {
    "offset": 0,
    "limit": 20
  }
));
curl_exec($ch);
curl_close($ch);
{%- endcodetabs %}