# 발신번호 등록 확인

register에서 받은 ars\_number로 전화를 거신후 handle\_key로 postRequest\('verify', data, 'senderid'\)를 호출하시면 발신번호 등록이 완료됩니다.

```text
uses
  System.Json, coolsms in '..\..\coolsms.pas', https in '..\..\https.pas', System.SysUtils, Classes;
var
  coolsms: resource;
  data: TStringList;
  jsonObject: TJSONObject;
begin
  try
    // http://www.coolsms.co.kr/SenderID_API#POSTverify 참조
    // api_key, api_secret 설정
    coolsms := resource.Create('NCS55882FB7DE511A', '4FB5FF82B9AB7D0E0AEB840D403DE0F74');
    // parameters
    data := TStringList.create;
    data.Values['handle_key'] := 'SID5FFFF7614ED3'; // register 호출 후 리턴받은 핸들값
    // 발신번호등록확인 요청
    jsonObject := coolsms.verify(data);
    if strToBool(jsonObject.GetValue('status').ToString) = TRUE then
    begin
      Writeln('성공');
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

