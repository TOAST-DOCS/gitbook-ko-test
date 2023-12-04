## Contact Center > Online Contact > API 가이드 > Open API 개요

Online Contact에서는 헬프센터 공지사항, FAQ, 티켓 정보, 티켓 생성 등 다양한 상담 정보를 **Open API**로 제공합니다.

Open API를 활용하여 외부 시스템에서 Online Contact의 상담 정보를 쉽게 확인할 수 있습니다.

### API 인증방법

#### Open API 설정
![OpenAPI_설정](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-openapi-overview_img0010.png)

Online Contact에서 제공하는 Open API를 사용하려면 [서비스관리 → 인증] 메뉴에서 기능을 활성화해야 합니다.
 
**① OPEN API 활성화**

- Open API 기능을 사용하려면 **활성화** 버튼을 클릭합니다.
- 활성화 시 서비스 Key가 자동 생성됩니다.

**② 서비스 Key**

- API를 호출하고, 전송되는 데이터를 암호화하는데 사용되는 인증 키입니다.
- Open API 활성화 시 자동 생성되며, **API Key 변경**을 클릭하면 Key 값을 변경할 수 있습니다.

<!--
#### 조직ID
![](http://static.toastoven.net/prod_contact_center/dev1_1_2.png)

전체 관리 → 계약 서비스 현황 → 조직 정보 탭에서 **① NHN Cloud 조직ID**를 확인하실 수 있습니다.
-->
#### 인증 Header

각 Request Header에 아래의 값들을 반드시 설정해야 합니다.

- Authorization: Security Key를 통해 생성된 인증 문자열
- X-TC-Timestamp: 현재 UTC 시간 값{new Date().getTime()}
- OUCODE: 유저 code(필수 아님，설정하지 않을 경우 기본 값은 Owner)

#### Authorization 문자열 생성 방법

HmacSHA256로 암호화하거나, (NHN Cloud 조직ID + request URI + 파라미터 값 + 현재 UTC시간 값)문자열에 대해 암호화하여 Authorization 문자열을 생성하실 수 있습니다.

> **※ 참고사항**
>
> NHN Cloud 조직ID는 **[전체관리 → 계약 서비스 현황 → 조직 정보]** 에서 확인할 수 있습니다.

#### Java 예제

##### 일반 요청(GET, POST)

```
String URL = "http://nhn-cs.oc.nhncloud.com/APISimple/openapi/v1/ticket/enduser/usercode/list.json?categoryId=1&language=ko";
String organizationId = "WopqM8euoYw89B7i"; // NHN Cloud 조직ID
String securityKey = "431402c0eaaf46d889f243db9e7492e2"; // 서비스 Key
String uri = "/APISimple/openapi/v1/ticket/enduser/usercode/list.json"; // request uri
StringBuilder sb = new StringBuilder();
sb.append(organizationId);
sb.append(uri);
sb.append("1").append("&").append("ko"); // 매개변수 순서에 따라(categoryId=1&language=ko)매개변수 사용(1&ko)
sb.append(body);// request body가 있을 경우 ，파라미터 뒤에 body 문자열 추가
sb.append(new Date().getTime());// X-TC-Timestamp값과 동일
SecretKeySpec signingKey = new SecretKeySpec(securityKey.getBytes("UTF-8"), "HmacSHA256");
Mac mac = Mac.getInstance(signingKey.getAlgorithm());
mac.init(signingKey);
byte[] rawHmac = mac.doFinal(sb.toString().getBytes("UTF-8"));
String authorization = new String(Base64.encodeBase64(rawHmac));
```

##### 파일 업로드

```
String URL = "http://nhn-cs.oc.nhncloud.com/APISimple/openapi/v1/ticket/attachments/upload.json";
String organizationId = "WopqM8euoYw89B7i"; // NHN Cloud 조직ID
String securityKey = "431402c0eaaf46d889f243db9e7492e2"; // 서비스 Key
String uri = "/APISimple/openapi/v1/ticket/attachments/upload.json"; // request uri
StringBuilder sb = new StringBuilder();
sb.append(organizationId);
sb.append(uri);
DigestUtils.appendMd5DigestAsHex(file.getInputStream(), sb);// 파일 첨부 시 , 파일의 MD5는 파라미터 값으로 인증 문자열에 추가
sb.append(new Date().getTime());// X-TC-Timestamp값과 동일
SecretKeySpec signingKey = new SecretKeySpec(securityKey.getBytes("UTF-8"), "HmacSHA256");
Mac mac = Mac.getInstance(signingKey.getAlgorithm());
mac.init(signingKey);
byte[] rawHmac = mac.doFinal(sb.toString().getBytes("UTF-8"));
String authorization = new String(Base64.encodeBase64(rawHmac));
```

##### OC 측 인증 방법

```
// Generate authorization string sample with request
StringBuilder sb = new StringBuilder();
sb.append(org.getId()); // organization Id
sb.append(request.getRequestURI()); // request URI
// upload file
if (request instanceof MultipartHttpServletRequest) {
	MultipartHttpServletRequest mpRequest = (MultipartHttpServletRequest) request;
	MultipartFile file = mpRequest.getFile("file");
	DigestUtils.appendMd5DigestAsHex(file.getInputStream(), sb);
// other
} else {
	Map<String, String[]> params = request.getParameterMap();
	if (!params.isEmpty()) {
		// Sort parameter
		Map<String, String[]> treeMap = new TreeMap<>(params);
		for (Map.Entry<String, String[]> entry : treeMap.entrySet()) {
			sb.append(entry.getValue()[0]).append("&");
		}
		sb.deleteCharAt(sb.length() - 1); // Delete '&' character
	}	
	if (request instanceof BodyReaderHttpServletRequestWrapper) {
		BodyReaderHttpServletRequestWrapper requestWrapper = (BodyReaderHttpServletRequestWrapper) request;
		if (requestWrapper.hasBody()) {
			String body = new String(requestWrapper.getBody(), StandardCharsets.UTF_8);
			if (!params.isEmpty()) {
				// params is not empty, add '&' character
				sb.append("&");
			}
			sb.append(body);
		}
	}	
}
String time = request.getHeader("X-TC-Timestamp");
// No '&' character
sb.append(time);

return sb.toString();
```

### 공통 리턴 결과
#### 리턴 결과 예제

```
//성공: 상세
{
    "header": {
        "resultCode": 200,
        "resultMessage": "",
        "isSuccessful": true
    },
    "result": {
        "content": {
        }
    }
}

//성공: 리스트
{
    "header": {
        "resultCode": 200,
        "resultMessage": "",
        "isSuccessful": true
    },
    "result": {
        "contents": [{
        }]
    }
}

//실패
{
    "header": {
        "resultCode": 403,
        "resultMessage": "Access Denied",
        "isSuccessful": false
    },
    "result": null
}
```

#### 리턴 결과 설명
|명칭|변수|데이터 타입|      설명|
|-------|---|-------------- |----------|
|Header|resultCode  |Integer|리턴 결과 Code, 정상은 200|
|    |resultMessage|String   |리턴 오류 메시지|
|    |isSuccessful |Boolean  |실행 결과(성공: true, 실패: false)|
|Result |contents     |JSON     |목록 결과 내용|
|       |content      |JSON     |상세 결과 내용|

#### 리턴 코드

- 200: SUCCESS
- 400: Bad Request
- 403: Access Denied(Forbidden)
- 404: Not Data Found
- 500: Server Error
- 9007: 관련된 데이터가 이미 존재
- 9005: 관련된 데이터가 없음

#### 리턴 코드(실패) 상세
##### 400

1. Authorization is blank
2. X-TC-Timestamp is not numeric
3. X-TC-Timestamp is expired(5분 내 유효)
4. Multipart request but file is null
5. Authorization is incorrect
6. Invalid paramter

##### 403

1. securityKey is null
2. clientIp is not allowed

### API 목록
#### 개발 환경 URL
|환경|BaseUrl|
|---|------------|
|알파|https://{domain}.oc.nhncloud.com|
|리얼|https://{domain}.oc.nhncloud.com	|

#### Security Key URL
|Security Key|URL|
|------------|-----|
|서비스의 Security Key  |/{serviceId}/openapi/v1/*|
|인증 없이 직접 사용 가능|/{serviceId}/api/v2/*|

#### API 목록
|그룹   |명칭    |유형     |URL|설명|
|---------|------------|---------|---|----|
|서비스    |서비스 상세                     |GET       |/{serviceId}/api/v2/service.json                                         |서비스 ID를 통해 서비스 정보 조회|
|공지사항  |말머리 리스트                    |GET       |/{serviceId}/api/v2/notice/categories.json                               |공지사항 말머리 리스트 취득      |
|      |태그 리스트                    |GET      |/{serviceId}/api/v2/notice/tags.json                                    |공지사항 태그 리스트 취득        |
|      |공지사항 리스트                   |GET      |/{serviceId}/api/v2/notice/list.json                                    |헬프센터 공지사항 리스트          |
|     |공지사항 상세                     |GET      |/{serviceId}/api/v2/notice/detail/{id}.json                               |공지사항 ID를 통해 공지사항 내용 취득|
|      |공지사항 첨부파일 열기 및 다운로드 |GET     |/{serviceId}/api/v2/notice/attachments/{id}                             |공지사항 첨부파일 열기/다운로드|
|FAQ  |카테고리 리스트                 |GET      |/{serviceId}/api/v2/helpdoc/categories.json                             |FAQ 카테고리 리스트 취득|
|      |FAQ 리스트                    |GET     |/{serviceId}/api/v2/helpdoc/list.json                                    |헬프센터 FAQ 리스트|
|      |FAQ 상세                        |GET     |/{serviceId}/api/v2/helpdoc/detail/{id}.json                           |FAQ ID를 통해 FAQ 내용 취득|
|      |FAQ 첨부파일 열기 및 다운로드      |GET      |/{serviceId}/api/v2/helpdoc/attachments/{id}                         |FAQ 첨부파일 열기 및 다운로드|
|문의 접수 |접수유형 리스트                  |GET       |/{serviceId}/api/v2/ticket/categories.json                            |서비스 내 접수유형 리스트 조회|
|      |접수유형 필드 리스트              |GET       |/{serviceId}/api/v2/ticket/field/user/{categoryId}.json                |접수유형을 통하여 대응되는 필드 리스트 확인|
|      |티켓 첨부파일 업로드              |POST       |/{serviceId}/openapi/v1/ticket/attachments/upload.json                |서버에 파일 업로드|
|      |티켓 생성                     |POST      |/{serviceId}/openapi/v1/ticket.json                                   |신규 티켓 생성|
|문의 내역 |고객 티켓 리스트              |GET       |/{serviceId}/openapi/v1/ticket/enduser/{usercode}/list.json             |검색 조건을 통해 조건에 맞는 고객의 티켓 리스트 노출|
|      |티켓 상세                     |GET      |/{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/detail.json|고객이 접수한 티켓 상세 조회|
|      |티켓 첨부파일 열기 및 다운로드  |GET    |/{serviceId}/api/v2/ticket/attachments/{id}                          |티켓 첨부파일 열기/다운로드|
|      |고객 재문의                     |POST  |{serviceId}/openapi/v1/ticket/enduser/{usercode}/{ticketId}/comment.json	|티켓 ID 기준으로 고객 재문의|