## Application Service > ShortURL > API 가이드

### 기본 정보
```http
API Endpoint: https://api-shorturl.nhncloudservice.com
```

## 단축 URL

### 1. 생성
- 단축 URL을 생성합니다.

[URL]

```http
POST /open-api/v1.0/appkeys/{appKey}/urls
Content-Type: application/json
```

#### 요청

[Path Variables]

| 이름 | 타입 | 필수 여부 | 설명 |
|---|---|---|---|
| appKey | String | O | 서비스 Appkey(**서비스 관리** 탭에서 확인 가능) |

[Request Body]

| 이름 | 타입 | 필수 여부 | 설명 |
|---|---|---|---|
| url | String | O | 원본 URL |
| domain | String | X | 단축 URL에 사용할 도메인(없을 경우 nh.nu로 생성) |
| backHalf | String | X | 단축 URL ID(https://nh.nu/example 에서 example을 가리키며, 없을 경우 랜덤 생성) |
| description | String | X | 단축 URL 설명 |
| campaigns | List<String> | X | 소속될 캠페인 ID 목록 |
| startDateTime | String | X | shortUrl 사용 시작 일시 |
| endDateTime | String | X | shortUrl 사용 만료 일시 |

* **startDateTime** 및 **endDateTime**을 추가할 때 **DateTimeFormatter.ISO_OFFSET_DATE_TIME** 포맷을 사용해 주세요.
* **startDateTime**을 별도로 지정하지 않으면 현재 시점으로 설정되며, **endDateTime**을 별도로 지정하지 않으면 **startDateTime**의 3개월 이후로 설정됩니다.

```json
{
   "url": "https://nhn.com",
   "domain": "nh.nu",
   "campaigns": [1,2],
   "backHalf": "example",
   "description": "test",
   "startDateTime" : "2022-11-10T02:58Z",
   "endDateTime": "2100-02-10T02:58Z"
}
```

#### 응답
```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    },
    "body": {
        "shortUrl": "http://nh.nu/example",
        "originUrl": "https://nhn.com",
        "status": "ACTIVE",
        "backHalfType": "CUSTOM",
        "description": "test",
        "startDateTime" : "2022-11-10T02:58Z",
        "endDateTime": "2100-02-10T02:58Z"
    }
}
```

| 이름 | 타입 | 설명 |
|---|---|---|
| header.isSuccessful | Boolean | 성공 여부 |
| header.resultCode | Integer | 결과 코드 |
| header.resultMessage | String | 실패 메시지 |
| body.shortUrl | String | 단축된 URL |
| body.originUrl | String | 원본 URL |
| body.status | String | 단축 URL 상태 |
| body.backHalfType | String | 단축 URL 생성 방식 |
| body.description | String | 단축 URL 설명 |
| body.startDateTime | String | 단축 URL 사용 시작 일시 |
| body.endDateTime | String | 단축 URL 사용 종료 일시 |

* 만들어진 단축 URL을 통해 원본 URL을 접근할 경우 원본 URL을 ASCII(7) 문자열로 변경하여 Location 헤더에 추가합니다.
* 이때 + 문자는 별도의 인코딩 없이 그대로 쓰입니다.
  * 예를 들어 `https://nhn.com?query=안+녕`은 `https://nhn.com?query=%EC%95%88+%EB%85%95`로 변환되며 `+`문자를 따로 `%2B`로 인코딩 하지 않습니다.

### 2. 검색
- 단축 URL을 검색합니다.

[URL]

```http
GET /open-api/v1.0/appkeys/{appKey}/domains/{domain}/urls/{backHalf}
```

#### 요청

[Path Variables]

| 이름 | 타입 | 필수 여부 | 설명 |
|---|---|---|---|
| appKey | String | O | 서비스 Appkey(**서비스 관리** 탭에서 확인 가능) |
| domain | String | O | 도메인 이름 |
| backHalf | String | O | 단축 URL path ID |


#### 응답
```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    },
    "body": {
        "shortUrl": "http://nh.nu/a",
        "originUrl": "https://nhn.com",
        "status": "ACTIVE",
        "backHalfType": "AUTO",
        "description": "test",
        "startDateTime": "2021-03-26T03:35+0000",
        "endDateTime": "9999-12-31T00:00+0000"
    }
}
```

| 이름 | 타입 | 설명 |
|---|---|---|
| header.isSuccessful | Boolean | 성공 여부 |
| header.resultCode | Integer | 결과 코드 |
| header.resultMessage | String | 실패 메시지 |
| body.shortUrl | String | 단축된 URL |
| body.originUrl | String | 원본 URL |
| body.status | String | 단축 URL 상태 |
| body.backHalfType | String | 단축 URL 생성 방식 |
| body.description | String | 단축 URL 설명 |
| body.startDateTime | String | 단축 URL 사용 시작 일시 |
| body.endDateTime | String | 단축 URL 사용 종료 일시 |



### 3. QR 코드 검색
- 단축 URL의 QR코드를 검색합니다.

[URL]

```http
GET /open-api/v1.0/appkeys/{appKey}/domains/{domain}/urls/{backHalf}/qrcode
```

#### 요청

[Path Variables]

| 이름 | 타입 | 필수 여부 | 설명 |
|---|---|---|---|
| appKey | String | O | 서비스 Appkey(**서비스 관리** 탭에서 확인 가능) |
| domain | String | O | 도메인 이름 |
| backHalf | String | O | 단축 URL path ID |

#### 응답
```json
{
    "header": {
        "isSuccessful": true,
        "resultCode": 0,
        "resultMessage": "SUCCESS"
    },
    "body": "iVBORw0KGgoAAAANSUhEUgAAAIIAAACCAQAAAACieC1QAAAA+0lEQVR4Xu3UsZHEIAwFUO0QkO024BnaIKMlbwNnuwHTkjO3wYwasDMCBp18wbHrxFJ6t4rMCzTigwE61QIf+ZOSAGizNILRCFIuj0yRPzQyeqoeZ9AKVjB6ScN66nMtlGmD0y4uhfPB2eN7Ypdy1JSPpUbSsHTPTNXqBEL6CtCDU8kdMC4urm0XAqGJuA+N9jcfiZS7L73FqaUqkfRcu4HMTk4jPHDpvdvbzCKpgcd2fIgq2Xx342w9aeSnlcWqk+OOcThzS1UifJ95aWpoO5UI/6ezB3h5E2TCb0J5vKQqExoD7rnNLBHK6ZaRUSNHPnExcVXJW33kX8g3k5xLHpTtgoMAAAAASUVORK5CYII="
}
```

| 이름 | 타입 | 설명 |
|---|---|---|
| header.isSuccessful | Boolean | 성공 여부 |
| header.resultCode | Integer | 실패 코드(0은 정상) |
| header.resultMessage | String | 실패 메시지 |
| body | String | Base64로 인코딩된 PNG 이미지 |
