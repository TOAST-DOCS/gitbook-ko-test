## AI Service > Text To Speech > API 가이드

### 음성 합성 API

#### 요청

- {appKey}와 {secretKey}는 콘솔 상단 **URL & Appkey** 메뉴에서 확인이 가능합니다.

[URI]

| 메서드 | URI |
|---|---|
| POST | https://speech.api.nhncloudservice.com/v1.0/appkeys/{appKey}/tts |

[요청 헤더]

| 이름 | 값 | 설명 |
|---|---|---|
| Authorization | {secretKey} | 콘솔에서 발급받은 보안 키 |
| Content-Type | application/json | |

[요청 본문]
```
{
    "inputText": "입력 텍스트",
    "fileType": "WAV",
    "language: "KO",
    "speaker": "MALE",
    "emotion": "NEUTRAL",
    "pitch": 0,
    "speed": 1,
    "volume": 0
}
```

[필드]

| 이름 | 타입 | 필수 여부 | 기본값 | 유효 범위 | 설명 |
|---|---|---|---|---|---|
| inputText | String | 필수 | | 최대 1000자 | 입력 텍스트 |
| fileType | String | 선택 | MP3 | MP3/WAV | 파일 형식(.mp3, .wav) |
| language | String | 선택 | KO | KO/EN/JA/ZH | 언어(한국어, 영어, 일본어, 중국어) |
| speaker | String | 선택 | FEMALE | MALE/FEMALE | 음성 종류(남성, 여성) |
| emotion | String | 선택 | NEUTRAL | NEUTRAL/DARK/BRIGHT | 음성 감정(기본, 어두운, 밝은) |
| pitch | Float | 선택 | 0 | -12~12| 높낮이 |
| speed | Float | 선택 | 1 | 0.5~4 | 속도 |
| volume | Float | 선택 | 0 | -6~6 | 음량 |

#### 응답

[성공 응답]
* HTTP Status Code: 200
* Content-Type: audio/wav 또는 audio/mpeg
* Body: byte[]

[실패 응답]
* Content-Type: application/json
```
{
    "header": {
        "isSuccessful": false,
        "resultCode": 400,
        "resultMessage": "Bad Request"
    },
    "errorList": [
        {
            "resultCode": 4000001,
            "resultTitle": "Invalid parameter.  (speed)",
            "resultMessage": "Must be equal to or less than  4 "
        },
        {
            "resultCode": 4000001,
            "resultTitle": "Invalid parameter.  (pitch)",
            "resultMessage": "Must be equal to or less than  12 "
        }
    ]
}
```
