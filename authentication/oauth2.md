# OAuth2 시작하기

oAuth2.0 은 개발자가 새롭게 만든 서비스나 웹 사이트에 기존 쿨에스엠에스 사용자의 비밀번호와 같은 민감한 정보를 노출하지 않고도 사용자의 권한을 대신 접근할수 있는 인증 프로토콜입니다.

등록된 서비스에서 적절한 권한&lt;권한목록링크&gt;들을 설정함으로써 쿨에스엠에스에서 제공하는 API &lt;API목록링크&gt;에 사용자의 허가하에 액세스 토큰을 발급받아서 접근 할수 있습니다.

우선 시작하기에 앞서, 이미 개발된 서비스나 [앱을 등록 절차](oauth2.md)를 하셔야 합니다. &lt;등록하러가기\|링크&gt; 등록이 정상적으로 완료된다면, 클라이언트의 아이디와 클라이언트의 비밀번호를 사용하여 인증 절차를 시작하실수 있습니다. 클라이언트 비밀번호는 노출되지 않도록 유의하여 주세요.

## 인증 흐름 알아보기

![](../.gitbook/assets/flow1%20%281%29.jpg)

## Step 1. 사용자 인증하기

개발하신 웹사이트 또는 서비스에서 아래의 링크와 쿼리 값을 추가하여 리다이렉트하여야 합니다.

```text
GET https://rest.coolsms.co.kr/oauth2/v1/authorize
```

필요한 GET 파라미터는 아래와 같으며 필드에 따라서 필수항목과 옵션항목들이 있습니다.

* `client_id` - **필수**. 서비스 또는 웹 등록시 발급받은 클라이언트 아이디
* `response_type` - **필수**. 값은 code 로 고정
* `scope` - **필수**. 서비스에서 필요한 사용자의 권한목록&lt;권한목록 링크 추가&gt; 
* `redirect_uri` - **필수**. 사용자 인증이 끝나면 돌아갈 url 주소
* `state` - **필수**. 서비스에서 해당 요청에 대하여 알아볼수 있는 랜덤 값

 **/oauth2/authorize**  에 대한 자세한 설명은 [여기에서 참고](https://docs.coolsms.co.kr/oauth2/api-reference.html#사용자-인-oauth2v1authorize)하세요.

`scope` 필드는 [권한 목록](https://docs.coolsms.co.kr/oauth2/how-to-use-scope.html#scope-목)을 참고하신후 빈칸으로 연결하여 사용하세요. 만약에 필요한 권한들이 `users:read` 와 `users.profile:read` 이라면 `users:read users.profile:read` 처럼 공백으로 연결하여 요청하시면 됩니다. [scope 에 관하여 자세히 알아보기](https://docs.coolsms.co.kr/oauth2/how-to-use-scope.html)

`state` 필드 값은 사용자 요청에서 정상적으로 사용자의 인증이 끝난후에 `redirect_uri`서 돌아가는 부분에서 악의적인 다른 접근을 차단하는 역활을 하는 값입니다. `redirect_uri`가 만약에 비어있다면, 서비스 등록시 입력한 `callback_uri` 로 대체됩니다.

정상적으로 사용자의 인증이 끝났다면, 아래와 같은 형태의 json 데이터를 `redirect_uri` 에서 수신받습니다.

```text
{
    code: 'ADFKVJCK19JDFKL2KFJLS3388',
    state: '사용자가 보내왔던 state값'
}
```

사용자 인증 요청시 보냈던 `state` 값을 다시 받음으로써, 해당 요청이 어떤 사용자에 대한 요청인지 인지 할수 있습니다.

## Step 2. 토큰 발급받기

사용자 인증이 정상적으로 완료후에 발급받은후에 발급받은 `code`를 사용하여 액세스 토큰을 발급받을 수 있습니다. 우선 토큰을 발급받기 위해서는 아래의 링크로 요청을 하여야 합니다.

```text
POST https://rest.coolsms.co.kr/oauth2/v1/access_token
```

필요한 POST body 파라미터는 아래와 같으며 필드에 따라서 필수항목과 옵션항목들이 있습니다.

* `grant_type` - 해당 필드는 인증서버에서 인증방법을 구분하는 필드로서 'authorization\_code' 값을 넣어야 합니다.
* `code` - Step 1 사용자 인증 후에 발급받은 `code` 값을 입력하면 됩니다.
* `client_id` - 서비스 또는 앱 등록시 발급받은 클라이언트 아이디
* `client_secret` - 서비스 또는 앱 등록시 발급받은 클라이언트 비밀번호
* `redirect_uri` -  토큰 발급에서 모든 인증이 정상적으로 마친후 돌아갈 callback uri

Step 1. 사용자 인증 단계에서는 사용자에 대한 인증을 확인하는 단계라면, Step 2. 토큰 발급받기에서는 사용자의 권한을 사용하려는 클라이언트를 클라이언트의 아이디와 비밀번호를 이용하여 클라이언트에 대한 인증을 확인합니다.

Step 1 의 사용자 인증 Step 2 의 클라이언트를 정상적으로 인증 확인이 됐다면, 액세스 토큰을 아래와 같이 jwt 형식으로 발급합니다.

```text
{
    access_token: 'eyGciOiNiIsIkpXVCJ9.eyJ0NTY3ODkwIiwibWRtaW4iOnRydWV9.TJVHrcEfxjoYZgeFONFh7HgQ',
    refresh_token: 'ciOiJIUzI1NkpXVCJ9.dWIiOiIxMjM0Y3ODIiwibmFtZSIkpv4gR.HrHDcEfxjoYZgeFONFh7HgQ'
}
```

발급받은 액세스 토큰을 사용하여 쿨에스엠에스의 API 를 접근할수 있습니다. 해당 액세스 토큰에 대한 권한은 ........ 아래와 같은 방법으로 확인 할수 있습니다. &lt;현재 사용자가 허가한 scope 를 알 방법이 jwt 를 decode 하는 방법밖에 없는듯...?&gt;

## Step 3. 토큰을 사용하여 API 접근하기

Step 1 과 Step 2 를 마친 후에 발급받은 access token 을 사용하여 쿨에스엠에스 API 를 이용할 수 있습니다.

```text
curl -X (GET|POST) https://rest.coolsms.co.kr/<접근하려는 API url>
-H 'Authorization: bearer <Access Token>'
```

위의 나타난 방법처럼 요청하려는 http request 의 header 에 authorization 에 액세스 토큰값을 넣어서 요청합니다. 예를 들어 요청하려는 API 가 userprofile API 라고 한다면 아래와 같이 합니다.

```text
curl -X GET https://rest.coolsms.co.kr/oauth2/v1/userprofile
-H 'authorization: bearer eyGciOiNiIsIkpXVCJ9.eyJ0NTY3ODkwIiwibWRtaW4iOnRydWV9.TJVHrcEfxjoYZgeFONFh7HgQ'
```

정상적으로 API 를 접근하였다면 해당 사용자의 profile 데이터를 가져왔을것입니다.

## oAuth2.0 인증 요약

1. 개발한 서비스나 앱을 등록하여 클라이언트의 아이디와 비밀번호를 발급받습니다. 
2. 개발한 서비스에 step1 사용자 인증을 하도록 연동합니다. 
3. 현재 사용자에 대한 쿨에스엠에스 계정 인증을 합니다.
4. 개발한 서비스에서 필요한 권한에 대한 사용자의 인가를 받습니다.
5. 인가된 권한이 포함된 액세스 토큰을 발급받습니다.
6. 발급받은 액세스 토큰을 header에 넣어 쿨에스엠에스 API 를 접근합니다.

## Refresh token \(재사용 토큰\) 사용하기

이미 발급받은 엑세스 토큰에 대한 유효시간이 만료된 경우, 액세스 토큰과 같이 발급받았던 재사용 토큰을 사용하여 다시액세스 토큰을 발급받을 수 있습니다. 재사용 토큰을 사용하여 `/oauth2/v1/access_token` 에 아래와 같이 http request 요청합니다.

```text
curl -X POST https://rest.coolsms.co.kr/oauth2/v1/access_token
-H 'Content-Type: application/json'
-d '{
    'grant_type': 'refresh_token',
    'refresh_token': 'eyGciOiNiIsIkpXVCJ9.eyJ0NTYDkwIwibWaW4iOnRydWV9.TVEfxjoYZgeFONFh7HgQ'
}'
```

* grant\_type - 기존의 'token' 값이 아닌 'refresh\_token'을 입력합니다.
* refresh\_token - 기존에 액세스 토큰과 함께 발급받은 재사용 토큰값을 입력합니다. 

## State 값에 대한 사용방법

사용자 인증시 입력하는 `state` 는 [CSRF 공격](https://en.wikipedia.org/wiki/Cross-site_request_forgery)에 대해 방지할수 있습니다.  
 `state` 값은 인증과정에서 `nonce` 역할을 합니다.   
 `nonce` 란 어떤 요청 중에 일시적인 `key` 역할을 하는 단어를 말합니다.   
 아래의 이미지에서는 `state`값에 대한 역할을 보여주고 있습니다. ![state&#xC5ED;&#xD560;](../.gitbook/assets/state-flow.png)

