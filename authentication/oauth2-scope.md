# OAuth2 Scope 사용하기

## Index

* [Scope 사용방법](oauth2-scope.md#scope-사용방법)
* [Scope 에러처리하기](oauth2-scope.md#scope-에러처리하기)
* [Scope 목록](oauth2-scope.md#scope-목록)

## Scope 사용방법

클라이언트에서 필요한 API 를 [Scope 목록](oauth2-scope.md#scope-목록)에서 확인한 후, 해당 scope 들을 ' '\(공백\) 으로 붙여서 사용합니다. 예를 들어, 클라이언트에서 필요할 권한들이 `users:read`, `users.profile:read` 라고 한다면 해당 권한들을 빈칸으로 붙여서 `users:read users.profile:read`로 만들어서 사용자 인증 요청\(/oauth2/v1/authorize\) 시에 `scope` 필드에 입력하면 됩니다.

```text
curl -X GET https://rest.coolsms.co.kr/oauth2/v1/authorize?scope=`users:read users.profile:read`&client_id......
```

## Scope 에러처리하기

oAuth2.0 인증시 클라이언트에서 요구하는 권한과 실제로 사용자가 인가한 권한이 다른경우에 액세스 토큰을 사용하는 client 에서 권한에 대한 에러가 나올수 있습니다. 이에 대한 적절한 에러 처리를 해주셔야 클라이언트에서 문제없이 서비스 운영이 가능합니다.

예를 들어서, 클라이언트에서 필요한 권한이 `users.profile:read users:read` 이라고 가정하고, 인증을 하였는데 사용자가 인가한 권한이 `users.profile:read` 일때 클라이언트에서 `users:read`에 대한 API 를 접근하려고 하면 `Unauthorized` 에러가 발생하여 문제가 발생합니다.

이런 문제가 발생하지 않도록 클라이언트에서는 이에 대한 에러 처리를 하거나 사용자로 하여금 권한 부족으로 서비스 사용에 문제가 있을수 있다는 메시지를 적절히 알려주어야 합니다.

## Scope 목록

쿨에스엠에스에서 제공하는 oAuth2.0 Scope 목록은 아래와 같습니다.

| Scope 명 | Scope 설명 | 접근 가능 APIs | 앱에서 사용가능 여부 |
| :--- | :--- | :--- | :--- |
| users:read | 캐쉬 정보를 포함한 사용자의 정보를 가져옵니다. | userinfo | O |
| users.profile:read | 사용자의 간단한 프로필 정보를 가져옵니다. | userprofile | O |
| senderid:read | 발신번호 조회 | senderid | O |
| role-senderid:read | 발신번호 조회\(멤버권한\) | senderid |  |
| senderid:write | 발신번호 등록 / 갱신 / 삭제 | senderid | O |
| role-senderid:write | 발신번호 등록 / 갱신 / 삭제\(멤버권한\) |  |  |
| message:write | 메시지 발송 | messages | O |
| role-message:write | 메시지 발송\(멤버권한\) |  |  |
| message:read | 메시지 상태 및 통계 조회 | messages | O |
| role-message:read | 메시지 상태 및 통계 조회\(멤버 권한\) | messages |  |
| cash:read | 신용카드 정보, 출금 계좌, 잔액 조회 | cash | O |
| role-cash:read | 신용카드 정보, 출금 계좌, 잔액 조회\(멤버권한\) | cash |  |
| cash:write | 신용카드 등록, 출금 계좌 등록, 충전 | cash | O |
| role-cash:write | 신용카드 등록, 출금 계좌 등록, 충전\(멤버\) | cash |  |
| role-appstore:read | 앱 조회\(멤버권한\) | appstore |  |
| role-appstore:write | 앱 등록 / 수정 / 삭제\(멤버권한\) | appstore |  |
| pricing:read | 계정 단가 조회 | pricing | O |
| role-pricing:read | 계정 단가 조회\(멤버권한\) | pricing |  |
| role-oauth2:read | Client 정보 조회\(멤버권한\) | oauth2 |  |
| role-oauth2:write | Redirect URI 등 Client 정보 업데이트\(멤버권한\) | oauth2 |  |
| role-credentials:read | API Key 조회\(멤버권한\) | credentials |  |
| role-credentials:write | API Key 발급\(멤버권한\) | credentials |  |
| notification:read | 알림 내역 조회 | notification | O |
| role-notification:read | 알림 내역 조회\(멤버권한\) | notification |  |
| role-notification:write | 알림 차단\(멤버권한\) | notification |  |
| coolog:read | 계정 로그 조회 | coolog | O |
| role-coolog:read | 계정 로그 조회\(멤버권한\) | coolog |  |
| storage:read | 계정 파일 조회 | storage | O |
| role-storage:read | 계정 파일 조회\(멤버권한\) | storage |  |
| storage:write | 계정 파일 업로드 | storage | O |
| role-storage:write | 계정 파일 업로드\(멤버권한\) | storage |  |
| iam:read | 계정 인증정보 조회 | iam | O |
| role-iam:read | 계정 인증정보 조회\(멤버권한\) | iam |  |
| iam:write | 계정 인증정보 추가 | iam | O |
| role-iam:write | 계정 인증정보 추가\(멤버권한\) | iam |  |
| account:read | 계정 정보 조회 | users | O |
| images:read | 이미지 조회 | images | O |
| role-images:read | 이미지 조회\(멤버권한\) | images |  |
| images:write | 이미지 업로드 | images | O |
| role-images:write | 이미지 업로드\(멤버권한\) | images |  |

