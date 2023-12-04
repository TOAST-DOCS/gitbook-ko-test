## AI Service > OCR > Vehicle Plate OCR > API 가이드

### 차량 번호판 분석 API

#### 요청

- {appKey}와 {secretKey}는 콘솔 상단 **URL & Appkey** 메뉴에서 확인이 가능합니다.

[URI]

| 메서드 | URI |
|---|---|
| POST | https://ocr.api.nhncloudservice.com/v1.0/appkeys/{appKey}/vehicle-plate |

[요청 헤더]

| 이름 | 값 | 설명 |
|---|---|---|
| Authorization | {secretKey} | 콘솔에서 발급 받은 보안 키 |

[요청 본문]

- 이미지 파일의 바이너리 데이터를 넣습니다.

```
curl -X POST 'https://ocr.api.nhncloudservice.com/v1.0/appkeys/{appKey}/vehicle-plate' \
-F 'image=@sample.png' \
-H 'Authorization: ${secretKey}'
```

[필드]

| 이름 | 타입 | 설명 |
|---|---|---|
| image | multipart/form–data | 이미지 파일 |

#### 응답

[응답 본문]

```
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    },
    "result": {
        "fileType": "png",
        "values": [
            {
                "value":"123가4567",
                "conf":0.93
            }
        ],
        "boxes": [
            {
                "x1": 340,
                "y1": 3231,
                "x2": 523,
                "y2": 3231,
                "x3": 523,
                "y3": 3297,
                "x4": 340,
                "y4": 3297
            }
        ],
        "resolution": "normal"
    }
}
```

[헤더]

| 이름 | 타입 | 설명 |
|---|---|---|
| isSuccessful | Boolean | 분석 API 성공 여부 |
| resultCode | Integer | 결과 코드 |
| resultMessage | String | 결과 메시지(성공 시 success, 실패 시 오류 내용) |

[필드]

| 이름 | 타입 | 설명 |
|---|---|---|
| fileType | String | 파일 확장자(jpg, png) |
| values | List | 인식 결과 목록 |
| values[0].value | String | 인식 내용 |
| values[0].conf | Double | 인식 결과 신뢰도 |
| resolution | String | 권장 해상도(HD 1280*720px) 이상이면 normal, 권장 해상도 미만은 low |
| boxes | List | 인식 영역(Bounding box) 좌표 목록 |
| boxes[0] | Object  | 인식 영역 좌표 { x1, y1, x2, y2, x3, y3, x4, y4 } |

* boxes[0]
 
    ![Bounding box](http://static.toastoven.net/prod_ocr/bbox.png)

