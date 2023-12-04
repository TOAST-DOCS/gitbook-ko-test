## AI Service > Pose Estimation > API 가이드


### 포즈 인식 API

#### 요청

- {appKey}와 {secretKey}는 콘솔 상단 **URL & Appkey** 메뉴에서 확인이 가능합니다.

[URI]

| 메서드 | URI                                                                        |
|---|----------------------------------------------------------------------------|
| POST | https://pose-estimation.api.nhncloudservice.com/v1.0/appkeys/{appKey}/pose |

[요청 헤더]

| 이름 | 값 | 설명              |
|---|---|-----------------|
| Authorization | {secretKey} | 콘솔에서 발급 받은 보안 키 |

[Path Variable]

| 이름 | 값 | 설명              |
| --- | --- |-----------------|
| appKey | {appKey} | 통합 Appkey 또는 서비스 Appkey |

[요청 본문]

- 이미지 파일의 Binary Data를 넣습니다.

```
curl -X POST 'https://pose-estimation.api.nhncloudservice.com/v1.0/appkeys/{appKey}/pose' \
-F 'image=@sample.png' \
-H 'Authorization: ${secretKey}'
```

[필드]

| 이름 | 타입 | 설명 |
|---|---|---|
| image | multipart/form–data | 이미지 파일 |

#### 응답

[응답 본문]

```json
{
  "header": {
    "isSuccessful": true,
    "resultCode": 0,
    "resultMessage": "SUCCESS"
  },
  "result": {
    "fileType": "png",
    "numberOfPerson": 5,
    "keyPointList": [
      {
        "personId": "0",
        "inferKeypointList": [
          {
            "name": "nose",
            "part": "body",
            "x": 367.151489,
            "y": 79.552887,
            "score": 0.976
          },
          {
            "name": "left_eye",
            "part": "body",
            "x": 373.819214,
            "y": 73.5605469,
            "score": 0.985
          },
          ...
        ]
      },
      ...
      {
        "personId": 2,
        "inferKeypoints": [
          {
            "name": "nose",
            "part": "body",
            "x": 98.7361755,
            "y": 68.2939758,
            "score": 0.979
          },
          {
            "name": "left_eye",
            "part": "body",
            "x": 110.171448,
            "y": 56.0753479,
            "score": 0.983
          },
          ...
        ]
      },
    ]
  }
}
```

[헤더]

| 이름 | 타입 | 설명                            |
|---|---|-------------------------------|
| isSuccessful | Boolean | 인식 API 성공 여부                  |
| resultCode | Integer | 결과 코드                         |
| resultMessage | String | 결과 메시지(성공 시 success, 실패 시 오류 내용) |

[필드]

| 이름                                         | 타입      | 설명                                      |
|--------------------------------------------|---------|-----------------------------------------|
| fileType                                   | String  | 파일 확장자(.jpg, .png)                      |
| numberOfPerson                             | Integer | 인식 결과 인원 수                              |
| keyPointList[0].personId                   | String  | 인식 결과 구분을 위해 부여된 ID                     |
| keyPointList[0].inferKeypointList[0].name  | String  | 신체 부위 이름                                |
| keyPointList[0].inferKeypointList[0].part  | String  | 신체 부위가 속한 부분 이름(body, foot, face, hand) |
| keyPointList[0].inferKeypointList[0].x     | Double  | 키포인트 x 좌표                               |
| keyPointList[0].inferKeypointList[0].y     | Double  | 키포인트 y 좌표                               |
| keyPointList[0].inferKeypointList[0].score | Double  | 키포인트 인식 결과 신뢰도                          |



