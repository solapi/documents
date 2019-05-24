# 기본 발신번호 설정

```python
import sys
from sdk.api.sender_id import SenderID 
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to set default sender number through CoolSMS Rest API PHP
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # handle_key is mandatory.
    handle_key = "SID567A2B2258CF9"

    cool = SenderID(api_key, api_secret)

    try:
        response = cool.set_default(handle_key)
        if response == None:
            print("Set Default Success")

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

