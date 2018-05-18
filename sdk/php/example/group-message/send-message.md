{% include "../../../fragments/group-message/send-message.md" %}





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

    // group_id are mandatory. must be filled
    $group_id = 'GID56CC00E21C4DC'; // ex) '1GCOLS23BDG'

    $result = $rest->sendGroupMessage($group_id);
    print_r($result);
} catch(CoolsmsException $e) {
    echo $e->getMessage(); // get error message
    echo $e->getCode(); // get error code
}
```