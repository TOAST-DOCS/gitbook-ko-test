## Contact Center > Online Contact > API 가이드 > 회원 연동 (POST)

## 회원 연동

### 개요

회원 연동은 자체 사용중인 서비스의 회원 인증을 Online Contact의 헬프센터에 적용하여 회원 문의를 접수하고, 접수한 문의 내역을 다시 확인할 수 있도록 제공하는 기능입니다.

회원 연동은 GET 방식과 POST 방식의 두 가지 타입으로 제공하며, 연동을 위해서 Online Contact에서 제공하는 개발 명세서에 따라 API를 개발하여 회원연동 메뉴에 등록해야 합니다.

**1. POST 방식**

- 연동하려는 서비스가 PC, Mobile 플랫폼에서 WEB 기반으로 제공될 경우 적합합니다.
- 서비스의 로그인 화면이 WEB URL 형태로 제공되어야 사용 가능합니다.
- 개발 명세에서 세부적으로 2가지 타입을 제공합니다.(Client-side, Sever-side)

**2. GET 방식**

- WEB 기반의 로그인 화면이 없는 서비스의 경우 적합합니다.
- WEB 기반이 아닌 Native APP 서비스의 경우 적합한 연동 방식입니다.

본 문서에는 POST 방식에 대해 설명하고 있습니다.
GET 방식 가이드가 필요하다면, [API 가이드 > 회원 연동(GET)](https://docs.nhncloud.com/ko/Contact%20Center/ko/online-contact-api-guide-openapi-member-get/) 문서를 참고하십시오.

### 프로세스(POST 방식)

1. 자체 서비스를 이용중인 고객이 헬프센터의 '문의하기' 또는 '문의내역' 페이지 접속
2. 헬프센터 페이지에서 로그인 상태 URL을 호출하여 로그인 상태 확인('로그인 상태 URL'은 아래 제공된 명세서에 따라 개발 후, Online Contact 회원연동 메뉴에 등록 필요)
3. 로그인 상태 확인 후 결과에 따라,
   - '로그아웃' 상태일 경우 자체 서비스의 '로그인 URL'을 호출하여 로그인 유도('로그인 URL'은 고객사에서 제공하고 있는 로그인 화면 사용)
   - '로그인' 상태일 경우 '원격 로그인 API'를 호출하여 고객 정보를 Online Contact 헬프센터에 전달
4. '문의하기' 또는 '문의내역' 페이지 접속

### 회원 연동 방법
![OpenAPI_POST회원연동](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-openapi-sso_img0011.png)

개발 명세서에 따라 API를 개발한 후 **[서비스 관리 > 헬프센터 > 회원 연동]** 메뉴에 접속하여 아래와 같이 설정합니다.

**① 회원 연동 활성화**

- 회원 연동 기능을 사용하기 위해 '활성화' 버튼을 클릭합니다.

**② 비회원 문의 접수**

- 회원 연동 시 로그인 사용자만 문의를 접수 가능한지 설정합니다.
- 활성화 시 로그아웃 상태에서도 문의 접수가 가능해지며, 비활성화 시 로그인 사용자만 문의 접수가 가능하도록 통제됩니다.

**③ 로그인 타입**

- POST 방식을 선택합니다.

**④ URL 설정**

- **로그인 URL**: 로그인 상태 URL을 호출했을 때, 유저가 로그인 상태가 아니라면 이동되는 로그인 화면 URL을 입력합니다.
- **로그인 상태 URL**: 헬프센터 접속 및 페이지 이동 시 유저가 로그인 상태인지 체크하는 URL을 입력합니다.
- URL은 하단의 개발 명세서를 참고하여 자체 운영중인 서비스에서 제공해야 합니다.

**④ 파라미터 설정**

- 필요에 따라 원격 로그인을 통해 Online Contact로 전달된 고객 정보를 **로그인 상태 URL 호출 시** 파라미터로 다시 전송할 수 있습니다.
- **추가** 버튼을 눌러 파라미터를 추가할 수 있으며, 요청 헤더 또는 쿼리에 포함하여 전송할 수 있습니다.
- 파라미터명은 **POST 원격 로그인 API**를 통해 Online Contact로 전달한 파라미터 명칭과 동일해야 합니다.

## 개발 명세서

### 인증토큰 생성

Token 생성 샘플은 아래와 같으며, 파라미터 순서는 반드시 아래와 일치해야 합니다.

Online Contact 조직 Key는 [전체 관리 → 계약 서비스 현황 → 조직 정보] 메뉴에서 확인할 수 있습니다.

(※ Sample project > application.properties > oc.apikey= 항목에 조직 Key를 저장)

```
private String getSHA256Token(String serviceId, String usercode, String username, String email, String phone,
        String returnUrl, Long time, String apiKey) throws Exception {
    StringBuilder sb = new StringBuilder();
    // Order by follow number:
    sb.append(serviceId); // 1
    sb.append("&");
    sb.append(usercode); // 2
    sb.append("&");
    if (StringUtils.isNotBlank(username)) {
        sb.append(username); // 3
        sb.append("&");
    }
    if (StringUtils.isNotBlank(email)) {
        sb.append(email); // 4
        sb.append("&");
    }
    if (StringUtils.isNotBlank(phone)) {
        sb.append(phone); // 5
        sb.append("&");
    }
    　if (StringUtils.isNotBlank(memberno)) {
        sb.append(memberno); // 6
        sb.append("&");
    　}
    if (StringUtils.isNotBlank(returnUrl)) {
        sb.append(returnUrl); // 7
        sb.append("&");
    }
    sb.append(time); // 8

    SecretKeySpec signingKey = new SecretKeySpec(apiKey.getBytes("UTF-8"), "HmacSHA256");
    Mac mac = Mac.getInstance(signingKey.getAlgorithm());
    mac.init(signingKey);
    byte[] rawHmac = mac.doFinal(sb.toString().getBytes("UTF-8"));
    return new String(Base64.encodeBase64(rawHmac));
}

// Sample
// Use this same input, the output is : Ah9M58CQ9RFTShjFuqziQr+0MjmJxN6+bzWxMD71moo=
public static void main(String[] args) throws Exception {
    String s = getSHA256Token("hangame", "testusercode", "testUsername", "test@email.com", "123456789",
    null, 1660095873001L, "7cf2828608274a49a3f06152b2188927");
    System.out.println(s); // Output: Ah9M58CQ9RFTShjFuqziQr+0MjmJxN6+bzWxMD71moo=
}
```

### POST 원격 로그인 API(From client side)

#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/v2/enduser/remote.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/v2/enduser/remote.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|POST 원격 로그인 API(From client side)|HTTPS  |POST    |UTF-8|Redirect    |사용자 시스템에서 동적으로 form를 생성하여 브라우저에 반환하며, form은 자동으로 API에 form정보를 전달. API에서 전달된 form정보로 인증 후 성공시 로그인 Cookie 값 설정.|

**사용자 시스템에서의 호출 방법**은 하단 Sample project의 다음과 같은 class를 참조하십시오.

- FormLoginController.java
- Method: submitLogin  

#### 요청 파라미터 정의
|명칭|변수|데이터 타입|필수|설명|
|-----|----|------------|----|----|
|서비스ID           |service|Varchar(50)|O|서비스 ID|
|유저ID            |usercode|Varchar(50)|O|유저ID，유일한 유저임을 표시|
|유저 명            |username|Varchar(50)|X|유저 명|
|유저 이메일 주소|email|Varchar(100)|X|유저 이메일|
|전화번호          |phone|Varchar(20)|X|전화번호|
|회원번호          |memberno|Varchar(50)|X|회원번호|
|현재 시간의 timestamp|time|Long|O|호출 시간이 3분 초과 시, 타임아웃 얼럿 출력.|
|인증 Token           |token |Varchar|O|다음 파라미터 값과 조직 Key로 산출된 SHA256(필수가 아닌 파라미터 값이 null 혹은 빈값일 경우, 암호화 문자열에 추가할 필요 없음. 주의: 문자열 중 각 값의 순서는 다음 예시에 지정된 순서와 일치해야 함.) SHA256Digest(service & usercode & username & email & phone & memberno & returnUrl & time)|
|리턴 화면 URL|returnUrl|Varchar|X|설정 및 로그인 성공 시 해당 주소로 이동|

#### 결과 데이터

returnUrl 파라미터 존재 시 지정된 returnUrl로 이동, returnUrl 파라미터가 없을 경우 문자열(SUCCESS) 반환

### POST 원격 로그인 API(From server side)
#### 인터페이스 설명

- URL: https://{domain}.oc.nhncloud.com/api/v2/enduser/remote.json
- URL(개발): https://{domain}.oc.alpha-nhncloud.com/api/v2/enduser/remote.json

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|POST 원격 로그인 API(From server side)|HTTPS  |POST    |UTF-8|String   |사용자가 서버에서 직접 API 호출. API 로그인 성공 후 로그인 Cookie 값 설정.|
  
**사용자 시스템에서의 호출 방법**은 하단 Sample project의 다음과 같은 class를 참조하십시오.

- ApiLoginController.java
- Method: submitLogin
  
#### 요청 파라미터 정의
|명칭|변수|데이터 타입|필수|설명|
|-----|----|-----------|-----|----|
|서비스ID|service|Varchar(50)|O|서비스 ID|
|유저ID|usercode|Varchar(50)|O|유저ID, 유일한 유저임을 표시|
|유저 명|username|Varchar(50)|X|유저 명|
|유저 이메일 주소|email|Varchar(100)|X|유저 이메일|
|전화번호|phone|Varchar(20)|X|전화번호|
|회원번호|memberno|Varchar(50)|X|회원번호|
|현재 시간의 timestamp|time|Long|O|호출 시간이 3분 초과 시, 타임아웃 얼럿 출력.|
|인증 Token|token|Varchar|O|다음 파라미터 값과 조직 Key로 산출된 SHA256(필수가 아닌 파라미터 값이 null 혹은 빈값일 경우, 암호화 문자열에 추가할 필요 없음. 주의: 문자열 중 각 값의 순서는 다음 예시에 지정된 순서와 일치해야 함.) SHA256Digest(service & usercode & username & email & phone & memberno &  time)|

#### Response Data
```
{	
  "header": {	
    "resultCode": 200,	
    "resultMessage": "",	
    "isSuccessful": true	
  },	
  "result": {	
    "content": "xxxxxxaccessTokenxxxxxxx"	
  }	
}	
```

헬프센터 호출 시, 리턴된 content 값을 헬프센터 URL 파라미터 - accessToken 값으로 지정하여 Online Contact에 전달.

예시: https://nhn-cs.oc.alpha-nhncloud.com/hangame/hc/?accessToken=xxxxxxaccessTokenxxxxxxx

### POST 로그인 URL(사용자)

#### 인터페이스 설명

- URL: 사용자 제공
- URL(개발): 사용자 제공

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|
|------------|--------|------|------|------|
|POST 로그인 URL(사용자)|HTTPS|GET|UTF-8|Redirect|

서비스 측 로그인 URL은 아래 기능을 제공해야 합니다.

1) 사용자 로그아웃 상태

- 로그인 화면 출력
- 계정/비밀번호로 로그인 진행
- 로그인 성공 후 cookie 생성 및 로그인 상태 기록, 로그인 상태 체크 시 사용됨
- 로그인 성공 후 Client 혹은 Server단에서 고객 정보를 Online Contact으로 전달(POST 원격 로그인 API(From client side), POST 원격 로그인 API(From server side) 참조)

2) 사용자 로그인 상태

- 로그인 성공 후 Client 혹은 Server단에서 고객 정보를 Online Contact으로 전달(POST 원격 로그인 API(From client side), POST 원격 로그인 API(From server side) 참조)

#### 요청 파라미터 정의
|명칭|변수|데이터 타입|필수|설명|
|---------|---------|-----------|---------|----|
|리턴 URL|returnUrl|Varchar|O|로그인 성공 후 이동되는 URL|

#### SSO 로그인 기능

1) 사용자 로그아웃 상태

- ① 로그인 화면으로 이동
- ② 사용자 로그인
- ③ 서비스 측의 서버에서 사용자 로그인 처리 및 로그인 사용자 관련 쿠키 생성
- ④ POST 원격 로그인 API 호출(POST 원격 로그인 API(From client side), POST 원격 로그인 API(From server side) 참조)

2) 사용자 로그인 상태

- ① POST 원격 로그인 API 호출(POST 원격 로그인 API(From client side), POST 원격 로그인 API(From server side) 참조)

#### POST 원격 로그인 API 호출 방법

1) POST 원격 로그인(From client side)

- ① 사용자 정보와 API Key 기준으로 로그인 token 생성
- ② 사용자 정보와 token을 브라우저로 리다이렉트
- ③ 화면에서 Form 작성, 상세한 파라미터는 POST 원격 로그인 API(From client side) 참조
- ④ Form 제출
- ⑤ POST 원격 로그인 API를 통해 사용자 정보와 token 전송
- ⑥ 로그인 성공 후 {returnUrl}로 이동

2) POST 원격 로그인(From server side)

- ① 사용자 정보와 API Key 기준으로 로그인 token 생성
- ② 서버에서 POST 원격 로그인 API(From server side) 호출
- ③ API 호출 파라미터(usercode, time)를 returnUrl 뒤에 추가
      - 예시) https://nhn-cs.oc.alpha-nhncloud.com/multilanguage/hc/ticket/list/?usercode=xxxxxx@163.com&time=1566531359635
- ④ {returnUrl}로 이동

### POST 로그인 상태 URL(사용자)
#### 인터페이스 설명

- URL: 사용자 제공
- URL(개발): 사용자 제공

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|--------|--------|------|--|----------|
|POST 로그인 상태 URL(사용자)|HTTPS|GET|UTF-8|JSON|사용자가 쿠키 정보를 기준으로 로그인 여부를 확인 후 JSON 형식의 데이터를 리턴. 서비스 측 Server에서 response에 Cross domain 접속 설정 필요|

**Cross domain 접속 설정** 방법은 하기 내용을 참조하십시오.
```
response.addHeader("Access-Control-Allow-Origin", request.getHeader("origin"));
response.addHeader("Access-Control-Allow-Credentials", "true");
```

**사용자 시스템에서의 구현 방법**은 하단 Sample project의 다음과 같은 class를 참조하십시오.

- FormLoginController.java
- Method: loginStatus

#### 요청 파라미터 정의

- 없음

#### 결과 데이터
|명칭|변수|데이터 타입|필수|설명|
|---------|---------|-----------|---------|----|
|javascript function|login|Boolean|O|로그인 상태. 로그인: true, 로그아웃: false|
|유저 ID|usercode|Varchar(50)|X|유저 ID(유니크 값). 로그인 상태가 true인 경우 필수|

#### Response Body
```
{
"login": "true",
"usercode":"usercodeXXX"
}

{
"login": "false",
"usercode": null
}
```

## 적용 예시
### Sample Code
✔ [Sample Code 다운로드](https://static.toastoven.net/prod_contact_center/oc_sso_sample-20220817.zip)

### iframe 이용 예시
#### 1. iframe으로 Online Contact 헬프센터를 사용자 페이지에 삽입
Sample Code 파일 중 'oc_sso_sample/src/main/resources/templates/help_frame.ftl'을 참조하십시오.
iframe의 이름은 반드시 id = "ocPage"로 지정해야 합니다.
```
<iframe src="https://${domain}/hangame/hc/?iframe=true" id="ocPage" frameborder="0" scrolling="no" 
      style="padding-top: 60px; box-sizing: unset; height: 100px; width: 100%"></iframe>
```  

페이지에 viewport 설정 시 mobile/web 브라우저 모두에서 헬프센터를 사용할 수 있습니다.
```
<meta name="viewport" content="width=device-width,initial-scale=1.0,minimum-scale=1.0,maximum-scale=1.0,user-scalable=0">
```

#### 2. parent 페이지 내에서 Online Contact 헬프센터의 높이를 확인하여 iframe의 height 조정
help_frame.ftl 파일 중 javascript 코드를 참조하십시오.
```
// Listener for OC content height change
window.addEventListener('message',function(event){
    // Set iframe height
    if(event.data > 0) {
    updateHeight(event.data);
    }
});

var updateHeight = function(wrapHeight) {
var iframe = window.document.getElementById('ocPage');
if(iframe != null) {
iframe.style.height = '0px'; 
var setHeight = (document.body.clientHeight > document.body.scrollHeight) ? document.body.clientHeight : document.body.scrollHeight;
var margin = 70;
setHeight = setHeight > wrapHeight ? setHeight : wrapHeight;
iframe.style.height = setHeight + margin + "px";
}
};
```

#### 3. 사용자 시스템에서 login 후 설정해야 할 cookie는 사용자 페이지에서 취득 가능
help_frame.ftl 파일 중 javascript 코드를 참조하십시오.
```
// get cookie
function getCookie(name) {
    var arr,reg=new RegExp("(^| )"+name+"=([^;]*)(;|$)");
    if(arr=document.cookie.match(reg))
        return unescape(arr[2]);
    else
        return null;
}
$.when( $.ready ).then(function() {
    var ssotoken = getCookie("sso_test_login");
    var usercode = getCookie("usercode");
    if(ssotoken != null && usercode != null) {
        var signout = $("#signout");
        $("#signout").html("Welcome " + usercode + "! <a href='/logout.nhn'>Sign out</a>");
        $("#signout").show();
        $("#signin").hide();
    }
});
```
