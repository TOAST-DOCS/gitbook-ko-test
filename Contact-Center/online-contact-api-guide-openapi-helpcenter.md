## Contact Center > Online Contact > API 가이드 > 헬프센터
### 헬프센터 지정 데이터 추가
#### 인터페이스 설명
- URL: https://{domain}.oc.toast.com/{serviceId}/hc/openapi/v1/addition.json
- URL(개발): https://{domain}.alpha-oc.toast.com/{serviceId}/hc/openapi/v1/addition.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|헬프센터에 지정 데이터 추가|HTTPS  |POST    |UTF-8|JSON    |추가로 필요한 고객정보를 DB에 저장|

#### 요청 파라미터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|----|-----------|-----|----|
|서비스 ID	    |serviceId	|String	|O	|URL PATH 내에 설정한{serviceId}|
|추가 고객정보  |content	  |String	|O	|추가 고객정보. request body 형식으로 전송, token 생성 시 인코딩 필요없음|
|노출 여부      |visible    |int    |X  |문의 내용에 노출 여부. 1: 노출, 0: 노출하지 않음. 기본 값: 0|

#### 결과 데이터
|명칭	|변수	|데이터 타입	|필수	|설명|
|-----|-----|-----------|----|----|
|result.content	|additionId	|String	|O	|생성된 ID|

#### Response Body
```
{
  "header": {
    "resultCode": 200,
    "resultMessage": "",
    "isSuccessful": true
  },
  "result": {
    "content": "ef1bd9560xxxxx"      // 해당 값은 additionId, 문의 페이지 호출 시 해당 값을 파라미터 - additionId 값으로 지정
  }
}
```
#### 문의 페이지 URL 예시
https://nhn-cs.alpha-oc.toast.com/hangame/hc/ticket/?additionId=ef1bd9560xxxxx

### APP 내 모바일 헬프센터 첨부 권한 체크
Online Contact 내 문의하기 첨부 이용 시, **고객사 App**의 **카메라 및 사진첩 권한 유무**에 따라 **첨부 권한을 제한**할 수 있도록 제공되는 기능입니다.
해당 기능을 이용하기 위해서는 하기 2가지 작업이 필요합니다.

- 헬프센터 URL 호출 시, ?from=app 파라미터를 붙여 호출
- Online Contact 개발 가이드에 따라 고객사 측 App 개발 (참고 가이드 : [Open API 개요](https://docs.nhncloud.com/ko/Contact%20Center/ko/online-contact-api-guide-openapi-overview/), [티켓 첨부 가이드](https://docs.toast.com/ko/Contact%20Center/ko/online-contact-api-guide-openapi-ticket/#_29))
