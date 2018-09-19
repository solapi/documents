# OAuth2 Scope 사용하기

## Index

* [Scope 사용방법](oauth2-scope.md#scope-사용방법)
* [Scope 에러처리하기](oauth2-scope.md#scope-에러처리하기)
* [Scope 목록](oauth2-scope.md#scope-목록)

## Scope 사용방법

클라이언트에서 필요한 API 를 [Scope 목록](oauth2-scope.md#scope-목록)에서 확인한 후, 해당 scope 들을 ' '\(공백\) 으로 붙여서 사용합니다. 예를 들어, 클라이언트에서 필요할 권한들이 `users:read`, `message:read`, `message:write` 라고 한다면 해당 권한들을 빈칸으로 붙여서 `users:read message:read message:write`로 만들어서 사용자 인증 요청\(/oauth2/v1/authorize\) 시에 `scope` 필드에 입력하면 됩니다.

```text
curl -X GET https://rest.coolsms.co.kr/oauth2/v1/authorize?scope=`users:read message:read message:write`&client_id......
```

## Scope 에러처리하기

oAuth2.0 인증시 클라이언트에서 요구하는 권한과 실제로 사용자가 인가한 권한이 다른경우에 액세스 토큰을 사용하는 client 에서 권한에 대한 에러가 나올수 있습니다. 이에 대한 적절한 에러 처리를 해주셔야 클라이언트에서 문제없이 서비스 운영이 가능합니다.

예를 들어서, 클라이언트에서 필요한 권한이 `users.profile:read sms:read` 이라고 가정하고, 인증을 하였는데 사용자가 인가한 권한이 `users.profile:read` 일때 클라이언트에서 `sms:read`에 대한 API 를 접근하려고 하면 `Unauthorized` 에러가 발생하여 문제가 발생합니다.

이런 문제가 발생하지 않도록 클라이언트에서는 이에 대한 에러 처리를 하거나 사용자로 하여금 권한 부족으로 서비스 사용에 문제가 있을수 있다는 메시지를 적절히 알려주어야 합니다.

## Scope 목록

쿨에스엠에스에서 제공하는 oAuth2.0 Scope 목록은 아래와 같습니다.

| Scope 명 | Scope 설명 | 접근 가능 APIs |
| :--- | :--- | :--- |
| users:read | 캐쉬 정보를 포함한 사용자의 정보를 가져옵니다. | userinfo |
| users.profile:read | 사용자의 간단한 프로필 정보를 가져옵니다. | userprofile |
| message:read |  |  |
| message:write |  |  |
| message:history |  |  |
| recharge:read |  |  |
| recharge:write |  |  |
| senderid:read |  |  |
| senderid:write |  |  |
| apps:read |  |  |
| apps:write |  |  |
| settings:read |  |  |
| settings:write |  |  |
| resale:read |  |  |
| resale:write |  |  |

