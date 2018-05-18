# 메시지 삭제

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

    // group_id, message_ids are mandatory. must be filled
    $group_id = 'GID56CC00E21C4DC'; // ex) '1GCOLS23BDG'
    $message_ids = '2838DFJFE02EI10TM'; // ex) '2838DFJFE02EI10TM','RGGBB11545'

    $result = $rest->deleteMessages($group_id, $message_ids);
    print_r($result);
} catch(CoolsmsException $e) {
    echo $e->getMessage(); // get error message
    echo $e->getCode(); // get error code
}
```

