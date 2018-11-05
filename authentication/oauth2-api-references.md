# OAuth2 API References

### Index

* [사용자 인증](oauth2-api-references.md#사용자-인-oauth2v1authorize)
* [토큰 발급받기](oauth2-api-references.md#토큰발급받기-oauth2v1accesstoken)

## 사용자 인증 \(/oauth2/v1/authorize\)

oAuth2.0 의 인증을 시작하는 API 로써 사용자에 대한 로그인 확인 및 처리를 진행하며, 인증이 완료된 후에는 Client 에서 필요로 하는 Scope에 대하여 사용자로부터 확인 및 인가를 받습니다.

#### Request

GET https://rest.coolsms.co.kr/oauth2/v1/authorize?{client\_id}&{scope}&{state}&{redirect\_uri}&{response\_type}

curl https://rest.coolsms.co.kr/oauth2/v1/authorize?client\_id={K00002ACVCC}&scope={users.profile:read}&state={kl3j81881929cvk}&redirect\_uri={https%3A%2F%2Fmytestapp.co.kr%2Fcallback}&response\_type={code}

 **Required query parameters** 

* `client_id` - client 등록시에 발급받은 `client_id`
* `state` - client 에서 `/oauth2/v1/authorize` 요청에 대한 `redirect_uri` 에서 구분을 할 수 있는 random string 값 \([자세히 알아보기](https://docs.coolsms.co.kr/oauth2/getting-started.html#state-값에-대한-사용방법)\)
* `redirect_uri` - 인증과 인가가 끝난후에 결과값인 `code` 와 `state` 를 받을 client의 callback uri
* `response_type` - `code` 값을 입력하면 됩니다. 
* `scope` - access token 으로 사용할 권한들 \([자세히 알아보기](https://docs.coolsms.co.kr/oauth2/how-to-use-scope.html)\)

#### Redirect

사용자에 대한 인증과 권한 인가가 완료된다면 인증시 입력하였던 `redirect_uri`로 결과값을 전송합니다. 예를 들어, `redirect_uri`가 `https://www.mytestsite.com/oauth2/callback` 이라면 결과값은 아래와 같습니다.

```text
https://www.mytestsite.com/oauth2/callback?code=l23kj16sdgal1236kn1236s1l236g123k6d126nlaskdnglkandglknsagd&state=alskdnglnl2k36j
```

* `code` - 인증 서버로 부터 발급받는 코드이며, 약 300초 동안만 유효
* `state` - 사용자로부터 받은 state 값이며, 이 값을 통하여 client 에서 어떤 요청에 대한 응답인지 구분한다. 

#### Errors

* `ValidationError(400)` - 잘못된 parameter 값이 왔을경우
* `InvalidScope(400)` - CoolSMS 에서 제공되는 scope 목록에서 없는 경우 
* `InvalidHostName(400)` - redirect 할 uri 의 host 와 클라이언트 등록할 때 등록한 uri 의 호스특가 다른 경
* `InvalidClientId(400)` - 잘못된 client id 를 입력한 경
* `InactiveClient(400)` - 클라이언트가 inactive 인 경우
* `InternalError(500)` - 서버 오류

## 토큰발급받기 \(/oauth2/v1/access\_token\)

oAuth2.0 인증 과정에서 토큰 발급을 담당하는 API 로써 `grant_type` 에 인증 방법이 달라지며 인증이 완료된 경우에 access token을 발급한다.

#### Request

POST https://rest.coolsms.co.kr/oauth2/v1/access\_token

curl -X POST https://rest.coolsms.co.kr/oauth2/v1/access\_token -H "Content-Type: application/json" -d '{"client\_id": "K0000DAV49C", "client\_secret": "skjf8190221lcmzza18j9woiq0", "redirect\_uri": "https://mytestapp.co.kr/callback", "grant\_type": "authorization\_code", "code": "SAMPLECODE" }'

 **Required body parameters** 

* `grant_type` - `access_token`발급을 위한 인증 방식. \(유효 값: `authorization_code`, `refresh_token`, `client_credentials`\)

 **Conditional required body parameters** 

* `client_id` - client 등록시에 발급받은 `client_id` \(header `Authorization`에 클라이언트 정보가 없는경우 필수\)
* `client_secret` - client 등록시에 발급받은 `client_secret` \(header `Authorization`에 클라이언트 정보가 없는경우 필수\)
* `redirect_uri` - client 발급 시 입력한 `redirect_uri` \(`grant_type`이 `authorization_code` 인 경우 필수\)
* `code` - 사용자인증\(/oauth2/v1/authorize\)에서 발급 받은 `code`값. \(`grant_type`이 `authorization_code` 인 경우 필수\)
* `refresh_token` - 기존에 토큰발급\('/access\_token'\)을 통하여 발급된 `refresh_token`. 만료기간이 없고 해당 사용자가 클라이언트에 대한 권한을 Revoke시 파기. \(`grant_type` 이 `refresh_token` 인 경우 필수\)
* `username` - coolSMS 의 userId. \(`grant_type` 이 `password` 인 경우 필수\)
* `password` - coolSMS 의 password. \(`grant_type` 이 `password` 인 경우 필수\)

#### grantType 에 대한 정리

* `authorization_code` - `authorization_code` grant flow를 통해 발급 받은 코드를 이용하여 `access_token`과 최초 1회 `refresh_token`발급
* `refresh_token` - 발급받은 `refresh_token` 을 사용한 `access_token`재발급
* `client_credentials` - 클라이언트 정보를 통한 `access_token`발급

#### Response

{ "access\_token": "String", "refresh\_token": "String", "token\_type": "String" }

{ "access\_token": "eyUnR5cCI6IkpXVCJ9.eyJleHBpcmVBdCI6IuyYJ9.MJ4CxRIuiuHxFscCHGgio", "refresh\_token": "asdglkj153lk.j15kljskdangb.as236dhfasdf125", "token\_type": "Bearer" }

* `access_token` - CoolSMS 리소스 서버\(각 마이크로서비스 서버\)에 접근하여 데이터 요청 시 인증을 위한 토큰. 만료기간은 24시간.
* `refresh_token` - `access_token`을 재발급 하기 위한 토큰. 사용자가 클라이언트를 Revoke 하지 않으면 영구적으로 사용가능.
* `token_type` - 리턴 받은 token의 타입

#### Errors

* `ValidationError(400)` - 유효하지 않은 파라미터 혹은 필수 파라미터 누락
* `InvalidGrant(403)` - 유효하지 않은 인증정보
* `InvalidClient(400)` - 유효하지 않은 클라이언트
* `InvalidRefreshToken(400)` - 유효하지 않은 refresh\_token 파라미터
* `InternalError(500)` - 서버 내부 오류

