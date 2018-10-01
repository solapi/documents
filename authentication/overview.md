# Overview

Message V4 에서는 [API Key 인증방식](api-key.md) 과 [OAuth2 인증방식](oauth2.md) 두가지 인증방식을 제공합니다.

HTTP 헤더에 Authorization 을 추가하여 인증정보를 서버에 전달 할 수 있습니다.

아래는 API Key 인증방식과 OAuth2  인증방식의 예입니다.

#### API Key 인증방식

`Authorization : HMAC-SHA256 apiKey=NCSGX2TG8G6ONABL, date=2018-07-04T00:06:38Z, salt=jqskl8jj6d3xwj, signature=7ceff00b74f9c242e8593c3be851d3431a00739c61d53f45e23e38d5fa6aa70e`

#### OAuth2 인증방식

`Authorization : Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXCVJ9.eyJhY2NvdW40SWQiOiI0ODYiLCJjbGllbnTJZCI6IkNJRE5VUklHT0NPT0xTTVMiLCJzY29wZSI6InVzZXBzlnByb2ZpbGU6cmVhCZIsImlhdCI6MTUzDMU5NTYxMywiZXhwIjoxNTMwNjgyMDEzfQ.1BKMHPzyyw_Lt0Hh7GoeGh0pyz4muFRfLnTX6d2bB` 



