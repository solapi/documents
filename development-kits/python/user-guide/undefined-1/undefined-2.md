# 그룹 삭제

```python
import sys
from sdk.api.group_message import GroupMessage
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to delete sms group through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # group_ids is mandatory
    group_ids = "GID57A82D462CBBFF" # Group IDs "GID57A82D462CBBFF,GID98A82D462CDBFF ..."

    cool = GroupMessage(api_key, api_secret)

    try:
        response = cool.delete_groups(group_ids)
        print("Success Count : %s" % response['success_count'])
        print("Error Count : %s" % response['error_count'])

        if "error_list" in response:
            print("Error List : %s" % response['error_list'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

