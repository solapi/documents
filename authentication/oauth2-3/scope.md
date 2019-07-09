# 권한\(Scope\) 목록

| Scope 명 | Scope 설명 | 접근 가능 APIs | 앱에서 사용가능 여부 |
| :--- | :--- | :--- | :--- |
| users:read | 캐쉬 정보를 포함한 사용자의 정보를 가져옵니다. | userinfo | O |
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
| accounts:read | 계정 정보 조회 | users | O |
| images:read | 이미지 조회 | images | O |
| role-images:read | 이미지 조회\(멤버권한\) | images |  |
| images:write | 이미지 업로드 | images | O |
| role-images:write | 이미지 업로드\(멤버권한\) | images |  |
| kakao:read | 카카오톡 정보 조회 | kakao | O |
| kakao:write | 카카오톡 정보 추가 및 수정 | kakao | O |
| role-kakao:read | 카카오톡 정보 조회\(멤버권한\) | kakao |  |
| role-kakao:write | 카카오톡 정보 추가 및 수정\(멤버권한\) | kakao |  |

