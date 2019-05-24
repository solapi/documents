# 메시지 전송

```python
import sys
from sdk.api.group_message import GroupMessage
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to check group info through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # group_id mandatory. must be filled
    group_id = "GID57A82D462CBBF" # Group ID

    cool = GroupMessage(api_key, api_secret)

    try:
        response = cool.send(group_id)
        print("Group ID : %s" % response['group_id'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

