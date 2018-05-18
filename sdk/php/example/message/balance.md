{% include "../../../fragments/message/balance.md" %}

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

    $result = $rest->getBalance(); // cancel does not return any.
    print_r($result);
} catch (CoolsmsException $e) {
    echo $e->getMessage(); // get error message
    echo $e->getCode(); // get response code
}
```
