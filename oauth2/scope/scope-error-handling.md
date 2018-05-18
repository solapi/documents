# 권한 에러 처리하기

oAuth2.0 인증시 client 에서 요구하는 권한과 실제로 사용자가 인가한 권한이 다른경우에 access token 을 사용하는 client 에서 권한에 대한 에러가 나올수 있습니다. 이에 대한 적절한 에러 핸들링을 해주셔야 client 에서 문제없이 서비스 운영이 가능합니다. 

예를 들어서, client 에서 필요한 권한이 `user.profile:read sms:read` 이라고 가정하고, 인증을 하였는데 사용자가 인가한 권한이 `user.profile:read` 일때 client 에서 `sms:read`에 대한 API 를 접근하려고 하면 `Unauthorized` 에러가 발생하여 문제가 발생합니다. 

이런 문제가 발생하지 않도록 client 에서는 이에 대한 에러 핸들링을 하거나 사용자로 하여금 권한 부족으로 서비스 사용에 문제가 있을수 있다는 메시지를 적절히 알려주어야 합니다. 
