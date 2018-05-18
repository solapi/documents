{% codetabs name="CURL", type="bash" -%}
$ curl -X POST https://solapi.com/ScheduledMessage/3/cancelScheduledGroups \
    --header "Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]" \
    -d '{
          "groups": [
            {
              "groupId": "[GROUP-ID]"
            }
          ]
        }'
{%- language name="JavaScript", type="javascript" -%}
request(
  {
    url: "https://solapi.com/ScheduledMessage/3/cancelScheduledGroups",
    method: 'post',
    headers: {
      'Authorization': `HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]`
    },
    json: {
      "groups": [
        {
          "groupId": "[GROUP-ID]"
        }
      ]
    }
  }
)
{%- language name="Python", type="python" -%}
conn = HTTPSConnection('solapi.com', '443')
conn.request(
  "POST",
  "/ScheduledMessage/3/cancelScheduledGroups",
  json.dumps(
    {
      "groups": [
        {
          "groupId": "[GROUP-ID]"
        }
      ]
    }
  ),
  {"Authorization":"HMAC-SHA256 ApiKey=[API_KEY], Date=[DATE], Salt=[SALT], Signature=[SIGNATURE]"})
conn.close()
{%- language name="PHP", type="php" -%}
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL,"https://solapi.com/ScheduledMessage/3/cancelScheduledGroups");
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Authorization: HMAC-SHA256 ApiKey=[API_KEY], Date=[DATA], Salt=[SALT], Signature=[SIGNATURE])');
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode(
  {
    "groups": [
      {
        "groupId": "[GROUP-ID]"
      }
    ]
  }
));
curl_exec($ch);
curl_close($ch);
{%- endcodetabs %}