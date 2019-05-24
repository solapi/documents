# 발신번호 리스트 가져오기

```python
import sys
from sdk.api.sender_id import SenderID 
from sdk.exceptions import SolapiException

##  @brief This sample code demonstrate how to check sender number list through CoolSMS Rest API
if __name__ == "__main__":

    # set api key, api secret
    api_key = "#ENTER_YOUR_OWN#"
    api_secret = "#ENTER_YOUR_OWN#"

    # site_id is optional.
    site_id = "user_id"

    cool = SenderID(api_key, api_secret)

    try:
        response = cool.get_list() # or cool.get_list(site_user)

        for data in response:
            print("Idno : %s" % data['idno'])
            print("Phone Number : %s" % data['phone_number'])
            print("Flag Default : %s" % data['flag_default'])
            print("Updatetime : %s" % data['updatetime'])
            print("Regdate : %s" % data['regdate'])

    except SolapiException as e:
        print("Error Code : %s" % e.code)
        print("Error Message : %s" % e.msg)

    sys.exit()
```

