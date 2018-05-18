{% codetabs name="CURL", type="bash" -%}
$ curl -X POST https://solapi.com/images/3/uploadImage \
    --header "Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{
          "imageType": "JPG",
          "base64EncodedImage": "YXNmYXNkZ3dlZnNkZ3NkZnNkZnNkZmFzZGY="
        }'
{%- language name="JavaScript", type="javascript" -%}
request(
  {
    url: "https://solapi.com/images/3/uploadImage",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "imageType": "JPG",
      "base64EncodedImage": "YXNmYXNkZ3dlZnNkZ3NkZnNkZnNkZmFzZGY="
    }
  }
)
{%- language name="Python", type="python" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/images/3/uploadImage",
  json.dumps(
    {
      "imageType": "JPG",
      "base64EncodedImage": "YXNmYXNkZ3dlZnNkZ3NkZnNkZnNkZmFzZGY="
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/images/3/uploadImage");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
  {
    "imageType": "JPG",
    "base64EncodedImage": "YXNmYXNkZ3dlZnNkZ3NkZnNkZnNkZmFzZGY="
  }
));
curl_exec($ch);
curl_close($ch);
{%- endcodetabs %}
