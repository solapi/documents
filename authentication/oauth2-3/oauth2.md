# 적용하기

OAuth 2는 개발자가 새롭게 만든 어플리케이션 이나 웹 사이트에서 사용자의 비밀번호와 같은 민감한 정보를 넘기지 않고 사용자가 허용한 권한 만큼의 기능만을 접근할 수 있는 인증 방식입니다.

우선 시작하기에 앞서, 이미 개발된 서비스나 [앱을 솔라피 앱스토어에 등록](oauth2.md)을 하셔야 합니다.  
등록이 정상적으로 완료된다면, 클라이언트의 아이디와 클라이언트의 시크릿 코드를 사용하여 인증 절차를 시작하실수 있습니다.  
클라이언트 시크릿 코드는 처음 생성시에만 보이니 보관 및 노출에 유의하여 주세요.

실제로 솔라피의 OAuth2를 사용하여 웹 어플리케이션을 개발한 예가 있으니 아래 링크를 참고하시면 보다 쉽게 OAuth2를 적용하실 수 있으실 겁니다.

* [OAuth2를 이용한 웹 어플리케이션 제작 바로가기](https://medium.com/nurigo/솔라피-oauth2-연동-node-express를-이용하여-앱-만들기-ca02dc2f4231)

## 인증 흐름 알아보기

![](../../.gitbook/assets/flow1.jpg)

## Step 1. 사용자 인증하기

개발하신 웹 사이트 또는 어플리케이션 에서 솔라피 로그인을 호출하기 위해 아래의 링크와 쿼리 파라미터 값을 추가하여 호출해주셔야 합니다.

보다 자세한 API References는 [OAuth2 API Document](https://docs.solapi.com/rest-api-reference/oauth2-api) 를 참고 부탁드립니다.

```text
GET https://api.solapi.com/oauth2/v1/authorize
```

필요한 GET 쿼리 파라미터는 아래와 같으며 필드에 따라서 필수항목과 옵션 항목들이 있습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Desc</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">client_id</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left">&#xC571; &#xC0DD;&#xC131;&#xC2DC; &#xBC1C;&#xAE09;&#xBC1B;&#xC740; Client
        ID</td>
    </tr>
    <tr>
      <td style="text-align:left">response_type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left">
        <p>Access Token &#xAC12;&#xC744; &#xBC14;&#xB85C; &#xBC1C;&#xAE09;&#xBC1B;&#xC744;
          &#xC218; &#xC788;&#xB294; &apos;token&apos;</p>
        <p>Authorization Code &#xAC12;&#xC744; &#xBC1C;&#xAE09;&#xBC1B;&#xC744; &#xC218;
          &#xC788;&#xB294; &apos;code&apos;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">state</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left">OAuth2 &#xC11C;&#xBC84;&#xC5D0;&#xC11C; &#xAC01;&#xAC01;&#xC758; &#xC694;&#xCCAD;&#xC744;
        &#xAD6C;&#xBD84;&#xC9D3;&#xB294; &#xAD6C;&#xBCC4; &#xD0A4;</td>
    </tr>
  </tbody>
</table>

```text
// rseponse_type이 code일 경우
{
    code: 'ADFKVJCK19JDFKL2KFJLS3388',
    state: '사용자가 보내왔던 state값'
}

// rseponse_type이 token일 경우
{
    access_token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.ZwUymzWAUiTxQ...',
    refresh_token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.ZwUymzWAUiTxQ...'
}
```

요청시 보냈던 `state` 값이 Response 값에 포함이되어 해당 요청이 어떤 사용자에 대한 요청인지 인지 확인할수 있습니다.

access\_token과 refresh\_token의 경우 아래에서 설명하도록 하겠습니다.

## Step 2. 엑세스 토큰 발급받기

사용자 인증이 정상적으로 완료후에 발급받은후에 발급받은 `code`를 사용하여 액세스 토큰을 발급받을 수 있습니다. \(response\_type이 token일 경우 제외\)  
우선 토큰을 발급받기 위해서는 아래의 링크로 요청을 하여야 합니다.

```text
POST https://api.solapi.com/oauth2/v1/access_token
```

필요한 POST body 파라미터는 아래와 같으며 필드에 따라서 필수항목과 옵션항목들이 있습니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Desc</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">grant_type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">true</td>
      <td style="text-align:left">
        <p>&apos;authorization_code&apos;, &apos;refresh_token&apos; &#xAC12;&#xC774;
          &#xC788;&#xC73C;&#xBA70;</p>
        <p>&#xD1A0;&#xD070;&#xC744; &#xBC1C;&#xAE09;&#xBC1B;&#xC744; &#xBC29;&#xBC95;&#xC5D0;
          &#xB9DE;&#xAC8C; &#xC124;&#xC815;&#xAC00;&#xB2A5;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">code</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">
        <p>grant_type&#xC774; &apos;authorization_code&apos;&#xC77C; &#xB54C; &#xD544;&#xC218;&#xAC12;&#xC73C;&#xB85C;</p>
        <p>Step 1&#xC5D0;&#xC11C; &#xBC1C;&#xAE09;&#xBC1B;&#xC740; authorization_code
          &#xAC12;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">client_id</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">
        <p>grant_type&#xC774; &apos;authorization_code&apos;&#xC77C; &#xB54C; &#xD544;&#xC218;&#xAC12;&#xC73C;&#xB85C;</p>
        <p>&#xC571; &#xC0DD;&#xC131;&#xC2DC; &#xBC1C;&#xAE09;&#xBC1B;&#xC740; Client
          ID &#xAC12;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">client_secret</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">
        <p>grant_type&#xC774; &apos;authorization_code&apos;&#xC77C; &#xB54C; &#xD544;&#xC218;&#xAC12;&#xC73C;&#xB85C;</p>
        <p>&#xC571; &#xC0DD;&#xC131;&#xC2DC; &#xBC1C;&#xAE09;&#xBC1B;&#xC740; Client
          Secret &#xAC12;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">redirect_uri</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">
        <p>grant_type&#xC774; &apos;authorization_code&apos;&#xC77C; &#xB54C; &#xD544;&#xC218;&#xAC12;&#xC73C;&#xB85C;</p>
        <p>&#xC571; &#xC0DD;&#xC131;&#xC2DC; &#xC785;&#xB825;&#xD558;&#xC600;&#xB358;
          Redirect URI &#xAC12;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">refresh_token</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">false</td>
      <td style="text-align:left">
        <p>grant_type&#xC774; &apos;refresh_token&apos;&#xC77C; &#xACBD;&#xC6B0;
          &#xD544;&#xC218;&#xAC12;&#xC73C;&#xB85C;</p>
        <p>&#xCCAB; Access Token &#xBC1C;&#xAE09; &#xC2DC; &#xBC1B;&#xC558;&#xB358;
          &#xAC12;</p>
      </td>
    </tr>
  </tbody>
</table>

또한 발급받은 액세스 토큰의 경우 24시간 사용이 가능하며, Refresh Token을 통해 좀 더 간단하게 재발급이 가능합니다.  
Refresh Token의 경우 만료기한이 없으며, **가장 처음 엑세스 토큰을 발급받을 때만 볼 수 있으니 이 점 유의 부탁드립니다.**

## Step 3. 엑세스 토큰을 사용하여 API 접근하기

위에서 발급받은 엑세스 토큰을 사용하여 아래와 같이 솔라피의 API를 이용할 수 있습니다.

```text
curl -X (GET|POST) https://api.solapi.com/<접근하려는 API url>
-H 'Authorization: bearer <Access Token>'
```

위의 예제처럼 요청하려는 HTTP Request 의 Header 에 Authorization 값을 넣어주면 됩니다.  
예를 들어 요청하려는 API 가 간단한 유저정보를 가져오는 API 라고 한다면 아래와 같이 할 수 있습니다.

```text
curl -X GET https://api.solapi.com/users/v1/member
-H 'authorization: bearer eyGciOiNiIsIkpXVCJ9.eyJ0NTY3ODkwIiwibWRtaW4iOnRydWV9.TJVHrcEfxjoYZgeFONFh7HgQ'
```

정상적으로 결과가 온다면 해당 멤버 정보 데이터를 가져왔을것입니다.  
[API Documents](https://docs.solapi.com/rest-api-reference/overview) 를 통해 사용가능한 API 를 확인할 수 있습니다.

## OAuth2.0 인증 요약

1. 개발한 서비스나 앱을 등록하여 클라이언트의 아이디와 비밀번호를 발급받습니다. 
2. 개발한 서비스에 Step1 사용자 인증을 하도록 연동합니다. 
3. 로그인을 통한 솔라피 계정 인증을 합니다.
4. 개발한 서비스에서 필요한 권한에 대한 사용자의 인가를 받습니다.
5. 인가된 권한이 포함된 액세스 토큰을 발급받습니다.
6. 발급받은 액세스 토큰을 Request Header에 넣어 솔라피 API 를 호출합니다.

## Refresh token \(재사용 토큰\) 사용하기

이미 발급받은 엑세스 토큰에 대한 유효시간이 만료된 경우, 액세스 토큰과 같이 발급받았던 재사용 토큰을 사용하여 다시액세스 토큰을 발급받을 수 있습니다. 재사용 토큰을 사용하여 `/oauth2/v1/access_token` 에 아래와 같이 http request 요청합니다.

```text
curl -X POST https://api.solapi.com/oauth2/v1/access_token
-H 'Content-Type: application/json'
-d '{
    'grant_type': 'refresh_token',
    'refresh_token': 'eyGciOiNiIsIkpXVCJ9.eyJ0NTYDkwIwibWaW4iOnRydWV9.TVEfxjoYZgeFONFh7HgQ'
}'
```

## State 값에 대하여

사용자 인증시 입력하는 `state` 는 [CSRF 공격](https://en.wikipedia.org/wiki/Cross-site_request_forgery)에 대해 방지할수 있습니다.  
`state` 값은 인증과정에서 `nonce` 역할을 합니다.  
`nonce` 란 어떤 요청 중에 일시적인 `key` 역할을 하는 단어를 말합니다.  
아래의 이미지에서는 `state`값에 대한 역할을 보여주고 있습니다.

![state&#xC5ED;&#xD560;](../../.gitbook/assets/state-flow.png)

## 권한\(Scope\) 에러처리

OAuth2 인증시 어플리케이션에서 요구하는 권한과 실제로 사용자가 인가한 권한이 다른경우에 액세스 토큰을 사용할 경우 권한에 대한 에러가 나올수 있습니다.  
이에 대한 적절한 에러 처리를 해주셔야 어플리케이션에서 문제없이 서비스 운영이 가능합니다.

예를 들어서, 어플리케이션에서 필요한 권한이 `accounts:read users:read` 이라고 가정하고, 인증을 하였는데 사용자가 인가한 권한이 `accounts:read` 일때 클라이언트에서 `users:read`에 대한 API 를 접근하려고 하면 `Unauthorized` 에러가 발생하여 문제가 발생합니다.

이런 문제가 발생하지 않도록 어플리케이션에서는 이에 대한 에러 처리를 하거나 사용자로 하여금 권한 부족으로 서비스 사용에 문제가 있을수 있다는 메시지를 적절히 알려주어야 합니다.

