# 멤버 권한 목록

각각의 계정에 속해있는 멤버들은 정해진 권한에 따라 계정을 사용할 수 있는 범위가 달라집니다.  
멤버의 권한은 'OWNER', 'DEVELOPER', 'MEMBER'로 정해져있으며 'OWNER'의 경우 계정의 모든 것을 사용할 수 있으며 계정 삭제 또한 가능하니 멤버에게 권한을 줄때 유의해주시길 바랍니다.

아래 표에 있는 'role-'로 작하는 권한 목록은 각각 멤버가 계정을 통해 사용할 수 있는 API 의 사용 권한을 의미하며 'write'의 경우 생성, 수정, 삭제 'read'의 경우 읽기 즉 정보 조회의 뜻을 담고 있습니다.

예를 들어 'role-senderid:read'의 경우 'role'은 멤버전용 권한 'senderid'는 발신번호 'read'는 정보보기이므로 해당 권한을 가진 멤버는 계정의 발신번호 정보를 볼 수 있다는 것을 나타냅니다.

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#xBA64;&#xBC84; &#xAD8C;&#xD55C; &#xBA85;</th>
      <th style="text-align:left">&#xC0AC;&#xC6A9;&#xD560; &#xC218; &#xC788;&#xB294; &#xAD8C;&#xD55C; &#xBAA9;&#xB85D;</th>
      <th
      style="text-align:left">&#xC124;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">OWNER</td>
      <td style="text-align:left">
        <p>role-senderid:read,</p>
        <p>role-senderid:write,</p>
        <p>role-message:write,</p>
        <p>role-message:read,</p>
        <p>role-cash:read,</p>
        <p>role-cash:write,</p>
        <p>role-appstore:read,</p>
        <p>role-appstore:write,</p>
        <p>role-pricing:read,</p>
        <p>role-oauth2:read,</p>
        <p>role-oauth2:write,</p>
        <p>role-notification:read,</p>
        <p>role-notification:write,</p>
        <p>role-coolog:read,</p>
        <p>role-storage:read,</p>
        <p>role-storage:write,</p>
        <p>role-iam:read,</p>
        <p>role-iam:write,</p>
        <p>role-credentials:read,</p>
        <p>role-credentials:write</p>
      </td>
      <td style="text-align:left">&#xD574;&#xB2F9; &#xACC4;&#xC815;&#xC744; &#xD1B5;&#xD55C; &#xBAA8;&#xB4E0;
        &#xD65C;&#xB3D9; &#xAC00;&#xB2A5;</td>
    </tr>
    <tr>
      <td style="text-align:left">DEVELOPER</td>
      <td style="text-align:left">
        <p>role-senderid:read,</p>
        <p>role-message:write,</p>
        <p>role-message:read,</p>
        <p>role-images:read,</p>
        <p>role-images:write,</p>
        <p>role-cash:read,</p>
        <p>role-appstore:read,</p>
        <p>role-appstore:write,</p>
        <p>role-pricing:read,</p>
        <p>role-oauth2:read,</p>
        <p>role-oauth2:write,</p>
        <p>role-notification:read,</p>
        <p>role-coolog:read,</p>
        <p>role-iam:read,</p>
        <p>role-credentials:read,</p>
        <p>role-credentials:write</p>
      </td>
      <td style="text-align:left">
        <p>&#xBC1C;&#xC2E0;&#xBC88;&#xD638; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xBA54;&#xC2DC;&#xC9C0; &#xBC1C;&#xC1A1; &#xBC0F; &#xB0B4;&#xC5ED; &#xC870;&#xD68C;,</p>
        <p>&#xC774;&#xBBF8;&#xC9C0; &#xC5C5;&#xB85C;&#xB4DC; &#xBC0F; &#xC870;&#xD68C;,</p>
        <p>&#xC794;&#xC561; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xC571; &#xC2A4;&#xD1A0;&#xC5B4; &#xB4F1;&#xB85D; &#xBC0F; &#xC870;&#xD68C;,
          <br
          />&#xB2E8;&#xAC00; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>OAuth2 &#xC0AC;&#xC6A9; &#xBC0F; &#xC870;&#xD68C;,</p>
        <p>&#xACC4;&#xC815; &#xC54C;&#xB9BC;&#xB0B4;&#xC5ED; &#xC870;&#xD68C;,</p>
        <p>&#xACC4;&#xC815; &#xD65C;&#xB3D9;&#xB0B4;&#xC5ED; &#xC870;&#xD68C;,</p>
        <p>&#xC778;&#xC99D; &#xD604;&#xD669; &#xC870;&#xD68C;,</p>
        <p>API Key &#xB4F1;&#xB85D; &#xBC0F; &#xC870;&#xD68C;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">MEMBER</td>
      <td style="text-align:left">
        <p>role-senderid:read,</p>
        <p>role-message:write,</p>
        <p>role-message:read,</p>
        <p>role-images:read,</p>
        <p>role-images:write,</p>
        <p>role-cash:read,</p>
        <p>role-appstore:read,</p>
        <p>role-pricing:read,</p>
        <p>role-notification:read</p>
      </td>
      <td style="text-align:left">
        <p>&#xBC1C;&#xC2E0;&#xBC88;&#xD638; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xBA54;&#xC2DC;&#xC9C0; &#xBC1C;&#xC1A1; &#xBC0F; &#xB0B4;&#xC5ED; &#xC870;&#xD68C;,</p>
        <p>&#xC774;&#xBBF8;&#xC9C0; &#xC5C5;&#xB85C;&#xB4DC; &#xBC0F; &#xC870;&#xD68C;,</p>
        <p>&#xC794;&#xC561; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xC571; &#xC2A4;&#xD1A0;&#xC5B4; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xB2E8;&#xAC00; &#xC815;&#xBCF4; &#xC870;&#xD68C;,</p>
        <p>&#xACC4;&#xC815; &#xC54C;&#xB9BC;&#xB0B4;&#xC5ED; &#xC870;&#xD68C;</p>
      </td>
    </tr>
  </tbody>
</table>