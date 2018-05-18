### 리스트보기(LIST)
**Parameters : **
 - site_user - 사이트 유저 아이디 입력, 미입력시 __private__ 으로 설정됩니다. 예) admin
 
**Return : **아래와 같이 JSONObject 형태로 return
```json
{
  "data":
  [
     {
       "regdate":"2015-08-07 12:21:33",
       "phone_number":"01000000001",
       "updatetime":"2015-08-21 18:09:10",
       "idno":"SID55C4FFFDDA2",
       "flag_default":"Y"
     },
     {
       "regdate":"2015-08-21 14:45:01",
       "phone_number":"01000000002",
       "updatetime":"2015-08-21 15:09:43",
       "idno":"SID55SSSD9FAB6",
       "flag_default":"N"
      }
  ,"status":true
}
```