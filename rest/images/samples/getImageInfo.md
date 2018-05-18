{% codetabs name="CURL", type="bash" %}
$ curl -X POST https://solapi.com/images/3/getImageInfo \
    --header "Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{}'
{%- language name="JavaScript", type="javascript" %}
request(
  {
    url: "https://solapi.com/images/3/[imageId]/getImageInfo",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {}
  }
)
{%- language name="Python", type="python" %}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/images/3/getImageInfo",
  json.dumps({}),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" %}
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/images/3/getImageInfo");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode({}));
curl_exec($ch);
curl_close($ch);
{%- endcodetabs %}