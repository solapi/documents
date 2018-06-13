# Errors

## InternalError

서버 내부 오류

HTTP Status Code: 500

## InvalidAPIKey

유효한 API Key가 아님

HTTP Status Code: 403

## SignatureDoesNotMatch

생성한 Signature가 일치하지 않음

HTTP Status Code: 403

## NotEnoughBalance

잔액이 부족함

HTTP Status Code: 402

## RequestTimeTooSkewed

시간 값이 서버 시간을 15분 이상 벗어남

HTTP Status Code: 403

## DuplicatedSignature

15분 안에 동일한 signature 값

HTTP Status Code: 403

## FileSizeTooBig

이미지파일 사이즈 300KB 초과

HTTP Status Code: 413

## ImageResolutionSizeTooBig

이미지의 해상도가 너무 큼, 2048 x 2048 이하

HTTP Status Code: 413

## MissingRequiredParameter

필수입력 파라메터 미입력

HTTP Status Code: 400

