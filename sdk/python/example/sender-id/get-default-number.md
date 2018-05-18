{% include "../../../fragments/sender-id/get-default-number.md" %}



```python
import sys
from sdk.api.sender_id import SenderID 
from sdk.exceptions import CoolsmsException

##  @brief This sample code demonstrate how to get default sender number through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    cool = SenderID(api_key, api_secret)

    try:
        response = cool.get_default()
        print("Handle Key : %s " % response['handle_key'])
        print("Phone Number : %s " % response['phone_number'])

    except CoolsmsException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit() 
```
