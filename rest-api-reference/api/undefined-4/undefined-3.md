# 이미지 목록

업로드된 이미지의 목록을 리턴합니다.

## Resource URL

`https://solapi.com/images/3/getImageList`

## Request Syntax

```javascript
{
  "offset": Number,
  "limit": Number
}
```

## Required Parameters

필수 입력 사항이 없습니다.

## Optional Parameters

### Sample Request

## Response Syntax

```javascript
{
  "totalCount": Number,
  "offset": Number,
  "limit": Number,
  "imageList": {
    "imageId": {
      "imageType": "String",
      "fileSize": Number,
      "width": Number,
      "height": Number
    },
    ...
  }
}
```

### Sample Response

* `totalCount` - 레코드 전체 갯수
* `offset` - 가져올 레코드 시작 위치
* `limit` - 가져올 레코드의 수
* `imageList` - Map 형식의 이미지 목록이 리턴됩니다.
  * imageType - 이미지의 형식, 업로드 할 때 서버에서 자동으로 jpeg 형식으로 변환됩니다.
  * fileSize - 바이트 단위의 파일 크기
  * width - 이미지의 픽셀 단위 가로 크기
  * height - 이미지의 픽셀 단위 세로 크기

```javascript
{
  "totalCount": 1,
  "offset": 0,
  "limit": 20,
  "imageList": {
    "IMG587C220F0734A" : {
      "imageType": "jpeg",
      "fileSize": 245000,
      "width": 800,
      "height": 600
    }
  }
}
```

## Errors

공통적으로 일어날 수 있는 오류 코드를 확인하시려면 오류코드 를 참고하세요.

