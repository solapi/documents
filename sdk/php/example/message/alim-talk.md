{% include "../../../fragments/message/alim-talk.md" %}

.

```php
use Nurigo\Api\Message;
use Nurigo\Exceptions\CoolsmsException;

require_once __DIR__ . "/../../vendor/autoload.php";

// api_key and api_secret can be obtained from www.coolsms.co.kr/credentials
$api_key = '#ENTER_YOUR_OWN#';
$api_secret = '#ENTER_YOUR_OWN#';

try {
    // initiate rest api sdk object
    $rest = new Message($api_key, $api_secret);

    // 4 options(to, from, type, text) are mandatory. must be filled
    $options = new stdClass();
    $options->to = '01000000000';
    $options->from = '01000000000';
    $options->type = 'ATA';
    $options->text = '메시지 내용은 template_code의 내용과 같아야 하며 내용중 변수 부분만 다르게 바꿀 수 있습니다.'; // 변수 예) {홍길동} -> 이하이
    $options->sender_key = '55540253a3e61072...'; // 알림톡 사용을 위해 필요합니다. 신청방법 : http://www.coolsms.co.kr/AboutAlimTalk
    $options->template_code = 'C004';             // 알림톡 template code 입니다. 자세한 설명은 http://www.coolsms.co.kr/AboutAlimTalk을 참조해주세요.

    $result = $rest->send($options);
    print_r($result);
} catch(CoolsmsException $e) {
    echo $e->getMessage(); // get error message
    echo $e->getResponseCode(); // get 'api.coolsms.co.kr' response code
}
```