# 권한\(Scope\) 목록

OAuth2 에서 사용가능한 권한은 '앱에서 사용가능 여부'에 'O'표시된 권한들만 사용이 가능하며, 앞에 'role'이 붙은 권한들은 사용하지 않습니다.

'role'이 붙은 권한들은 계정에 대한 멤버들의 권한을 나타내는 것으로써 해당 권한을 가진 멤버들만이 계정을 통해 권한에 맞는 API를 호출 할 수 있습니다.  
예를들어 발신번호에 해당하는 권한인 'role-senderid:read' 를 갖고 있지 않은 멤버가 OAuth2를 통해 다른 어플리케이션에 'senderid:read'의 권한허용을 하였다고 하더라도 발신번호 API를 이용하지 못합니다.

| Scope 명 | Scope 설명 | 접근 가능 APIs | 앱에서 사용가능 여부 |
| :--- | :--- | :--- | :--- |
| users:read | 캐쉬 정보를 포함한 사용자의 정보를 가져옵니다. | userinfo | O |
| senderid:read | 발신번호 조회 | senderid | O |
| role-senderid:read | 발신번호 조회\(멤버권한\) | senderid |  |
| senderid:write | 발신번호 등록 / 갱신 / 삭제 | senderid | O |
| role-senderid:write | 발신번호 등록 / 갱신 / 삭제\(멤버권한\) | senderid |  |
| message:write | 메시지 발송 | messages | O |
| role-message:write | 메시지 발송\(멤버권한\) | messages |  |
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
| accounts:read | 계정 정보 조회 | users | O |
| images:read | 이미지 조회 | images | O |
| role-images:read | 이미지 조회\(멤버권한\) | images |  |
| images:write | 이미지 업로드 | images | O |
| role-images:write | 이미지 업로드\(멤버권한\) | images |  |

