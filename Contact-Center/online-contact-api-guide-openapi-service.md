## Contact Center > Online Contact > API 가이드 > 서비스 

### 서비스 상세
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/{serviceId}/api/v2/service.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/{serviceId}/api/v2/service.json

|인터페이스 명|프로토콜|호출방식|인코딩|결과 형식|인터페이스 설명|접근제한 여부|
|------------|-------|--------|-----|--------|--------------|------------|
|서비스 상세  |HTTPS  |GET    |UTF-8|JSON    |서비스 ID를 통해 서비스 정보 조회|필요 없음|

#### 요청 파라미터 정의
|명칭	|변수	|데이터 타입	|변수 유형|필수	|설명|
|-------|------|---------------|--------|----|----|
|서비스 ID |serviceId	|String	|path	|O    |서비스 ID，URL PATH 내에 설정한{serviceId}|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|설명|
|-----|----|-----------|------|
|result.content	|serviceId	    |String		|서비스 ID|
|	            |name	        |String		|서비스명|
|	            |profile	    |String		|서비스 배경 이미지|
|	            |language	    |String		|서비스 기본 언어 코드|
|	            |languages	    |Array		|서비스 언어 리스트|
|	            |languages.code	|String		|언어 코드|
|	            |languages.name	|String		|언어 명칭|
|	            |languages.orderNo	|Integer		|언어 노출 순서|
|	            |multiLanguage	|Boolean		|서비스 다국어 여부, 값(true: 다국어, false: 단일 언어)|

#### Response Body
```
{
    "header": {
        "resultCode": 200,
        "resultMessage": "",
        "isSuccessful": true
    },
    "result": {
        "content": {
            "serviceId": "APISample",
            "name": "APISample",
            "profile": {
                "fileUrl": "https://api-storage.cloud.nhncloud.com/v1/AUTH_226f908c769e48b0bad7d32f9a91717f/service_alpha/WopqM8euoYw89B7i/27316eba2a8a4089b72a9cf18a83e144.png"
            },
            "language": "ko",
            "languages": [
                {
                    "code": "ko",
                    "name": "한국어",
                    "orderNo": 0
                },
                {
                    "code": "ja",
                    "name": "日本語",
                    "orderNo": 1
                },
                {
                    "code": "en",
                    "name": "English",
                    "orderNo": 2
                },
                {
                    "code": "zh",
                    "name": "中文",
                    "orderNo": 3
                },
                {
                    "code": "th",
                    "name": "ไทย",
                    "orderNo": 4
                }
            ],
            "multiLanguage": true
        }
    }
}
```