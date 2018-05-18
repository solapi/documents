{% include "../../../fragments/group-message/create-group.md" %}




```php
use Nurigo\Api\GroupMessage;
use Nurigo\Exceptions\CoolsmsException;

require_once __DIR__ . "/../../vendor/autoload.php";

// api_key and api_secret can be obtained from www.coolsms.co.kr/credentials
$api_key = '#ENTER_YOUR_OWN#';
$api_secret = '#ENTER_YOUR_OWN#';

try {
    // initiate rest api sdk object
    $rest = new GroupMessage($api_key, $api_secret);

    // Optional parameters for your own needs
    $options = new stcClass();
    // $options->charset = 'utf8';  // utf8, euckr default value is utf8
    // $options->srk = ''; // Solution key
    // $options->mode = 'test'; // If 'test' value. refund cash to point
    // $options->delay = 10; // '0~20' delay messages
    // $options->force_sms = true; // 'true or false' always send sms
    // $options->app_version = ''; // App version

    $result = $rest->newGroup($options);
    print_r($result);
} catch(CoolsmsException $e) {
    echo $e->getMessage(); // get error message
    echo $e->getCode(); // get error code
}
```