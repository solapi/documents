# 알림톡 발송

```java
package net.nurigo.java_sdk.examples.Message;

import java.util.HashMap;
import org.json.simple.JSONObject;
import net.nurigo.java_sdk.api.Message;
import net.nurigo.java_sdk.exceptions.CoolsmsException;

/**
 * @class ExampleSend
 * @brief This sample code demonstrate how to send sms through CoolSMS Rest API PHP
 */
public class ExampleSend {
  public static void main(String[] args) {
    String api_key = "#ENTER_YOUR_OWN#";
    String api_secret = "#ENTER_YOUR_OWN#";
    Message coolsms = new Message(api_key, api_secret);

    // 4 params(to, from, type, text) are mandatory. must be filled
    HashMap<String, String> params = new HashMap<String, String>();
    params.put("to", "01000000000"); // 수신번호
    params.put("from", "01000000000"); // 발신번호
    params.put("type", "ATA"); // Message type ( SMS, LMS, MMS, ATA )
    params.put("text", "Test Message"); // 알림톡 사용시 해당 template_code의 메시지 내용과 동일해야하며 "{}"로 둘러쌓여있는 변수는 다른 내용으로 변경 가능합니다.
    params.put("app_version", "JAVA SDK v1.2"); // application name and version
    params.put("sender_key", "55540253a3e61072f57ed5d4cc2ecf965e15bb64"); // 알림톡 사용을 위해 필요합니다. 신청방법 : http://www.coolsms.co.kr/AboutAlimTalk
    params.put("template_code", "C004"); // 알림톡 template code 입니다. 자세한 설명은 http://www.coolsms.co.kr/AboutAlimTalk을 참조해주세요. 
    params.put("button_name", "바로가기"); // 알림톡 버튼이름 입니다.
    params.put("button_url", "http://www.coolsms.co.kr"); // 알림톡 버튼URL 입니다.

    try {
      JSONObject obj = (JSONObject) coolsms.send(params);
      System.out.println(obj.toString());
    } catch (CoolsmsException e) {
      System.out.println(e.getMessage());
      System.out.println(e.getCode());
    }
  }
}
```

