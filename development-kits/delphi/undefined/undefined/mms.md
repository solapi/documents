# MMS발송

type을 mms로 바꿔준뒤 전송할 이미지 파일 정보를 입력합니다.

```text
uses
  System.Json, coolsms in '..\..\coolsms.pas', https in '..\..\https.pas', System.SysUtils, Classes;
var
  coolsms: resource;
  jsonObject: TJSONObject;
  data: TStringList;
begin
  try
    // api_key, api_secret 설정
    coolsms := resource.Create('NCS55882FB7DE511A', '4FB5FF82B9AB7D0E0AEB840D403DE0F74');
    // parameters
    data := TStringList.create;
    data.Values['to'] := '01000000000'; // 수신번호
    * 10월 16일 이후로 발신번호 사전등록제로 인해 등록된 발신번호로만 문자를 보내실 수 있습니다. 바로가기
    data.Values['from'] := '029302266'; // 발신번호
    data.Values['text'] := 'test'; // 문자내용
    data.Values['type'] := 'mms';  // 문자타입 sms, mms, lms
    data.Values['image'] := '..\..\test.jpg'; // IMAGE 파일 (MMS일경우)
    // send Messages
    jsonObject := coolsms.send(data);
    if strToBool(jsonObject.GetValue('status').ToString) = TRUE then
    begin
      Writeln('성공');
      Writeln('group_id : ' + jsonObject.Get('group_id').JsonValue.ToString);
      Writeln('success_count : ' + jsonObject.Get('success_count').JsonValue.ToString);
      Writeln('error_count : ' + jsonObject.Get('error_count').JsonValue.ToString);
      Writeln('result_code : ' + jsonObject.Get('result_code').JsonValue.ToString);
      Writeln('result_message : ' + jsonObject.Get('result_message').JsonValue.ToString);
    end
    else
    begin
      Writeln('실패');
      if jsonObject.Get('code').Equals(Nil) = FALSE then Writeln('code : ' + jsonObject.Get('code').JsonValue.ToString);
      if jsonObject.Get('message').Equals(Nil) = FALSE then Writeln('message : ' + jsonObject.Get('message').JsonValue.ToString);
    end;
    jsonObject.Free;
    Writeln('-----------------------------------------');
    Writeln('Press <enter> to quit...');
    Readln;
  except
    on E: Exception do
      Writeln(E.ClassName, ': ', E.Message);
  end;
end.
```

