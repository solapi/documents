# 전송결과\(SENT\)

**Parameters :** 

* mid - message\_id 
* gid - group\_id
* count - count
* page - page
* s\_rcpt - 수신번호
* s\_start - 검색 시작 날짜
* s\_end - 검색 종료 날짜

**Return :** 아래와 같이 JSONObject 형태로 return

```javascript
{
  'total_count':169,
  'list_count':4,
  'page':1,
  'data':[
    {
      'type':'SMS',
      'accepted_time':'2014-01-07 18:14:54',
      'recipient_number':'01000000000',
      'group_id':'G52CBC596955F0',
      'message_id':'M52CBC59695B31',
      'status':'2',
      'result_code':'58',
      'result_message':'\uc804\uc1a1\uacbd\ub85c \uc5c6\uc74c',
      'sent_time':'201401071814',
      'text':'Test Message'
    },
    {
      'type':'SMS',
      'accepted_time':'2014-01-07 18:14:41',
      'recipient_number':'01000000000',
      'group_id':'G52CBC5897645A',
      'message_id':'M52CBC58976A64',
      'status':'2',
      'result_code':'58',
      'result_message':'\uc804\uc1a1\uacbd\ub85c \uc5c6\uc74c',
      'sent_time':'201401071814',
      'text':'message\nhere'
    }
  ]
}
```

