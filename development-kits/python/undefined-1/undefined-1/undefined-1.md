# 그룹 리스트 보기

```python
import sys
from sdk.api.group_message import GroupMessage
from sdk.exceptions import CoolsmsException


##  @brief This sample code demonstrate how to check group list through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    cool = GroupMessage(api_key, api_secret)

    try:
        response = cool.get_group_list()
        print("Group List : %s" % response['list'])

    except CoolsmsException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

