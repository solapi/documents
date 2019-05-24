# 예약문자 취소

```python
import sys
from sdk.api.message import Message
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to cancel reserved sms through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    params = dict()
    params['message_id'] = 'MID57A423F131F01'
    # params['group_id'] = 'GID57A423F131C0F'

    cool = Message(api_key, api_secret)
    try:
        response = cool.cancel(params)
        print("Response : %s" % response)
    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

