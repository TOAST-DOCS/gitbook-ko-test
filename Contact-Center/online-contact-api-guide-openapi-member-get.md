## Contact Center > Online Contact > API 가이드 > 회원 연동 (GET)

## 회원 연동

### 개요

회원 연동은 자체 사용중인 서비스의 회원 인증을 Online Contact의 헬프센터에 적용하여 회원 문의를 접수하고, 접수한 문의 내역을 다시 확인할 수 있도록 제공하는 기능입니다.

회원 연동은 GET 방식과 POST 방식의 두 가지 타입으로 제공하며, 연동을 위해서 Online Contact에서 제공하는 개발 명세서에 따라 API를 개발하여 회원연동 메뉴에 등록해야 합니다.

**1. POST 방식**

- 연동하려는 서비스가 PC, Mobile 플랫폼에서 WEB 기반으로 제공될 경우 적합합니다.
- 서비스의 로그인 화면이 WEB URL 형태로 제공되어야 사용 가능합니다.
- 개발 명세에서 세부적으로 2가지 타입을 제공합니다.(CLIENT-SIDE, SERVICER-SIDE)

**2. GET 방식**

- WEB 기반의 로그인 화면이 없는 서비스의 경우 적합합니다.
- WEB 기반이 아닌 Native APP 서비스의 경우 적합한 연동 방식입니다.

본 문서에는 GET 방식에 대해 설명하고 있습니다.
POST 방식 가이드가 필요하다면, [API 가이드 > 회원 연동(POST)](https://docs.nhncloud.com/ko/Contact%20Center/ko/online-contact-api-guide-openapi-sso/) 문서를 참고하십시오.

### 프로세스(GET 방식)

1. 자체 서비스를 이용하는 고객이 APP 내에서 헬프센터에 접속합니다.
2. APP에서 헬프센터 호출 시 아래 URL 형식으로 호출합니다.
    - https://**{org}**.oc.nhncloud.com/**{service}**/hc/?usercode=**{유저_아이디}**&username=**{유저_이름}**&email=**{유저_이메일}**&phone=**{유저_전화번호}**&token=**{인증토큰_값}**
3. 헬프센터에서 **'Token 검증 URL'**을 호출합니다.('Token 검증 URL'은 고객사에서 아래 제공된 명세서에 따라 개발 후 Online Contact 회원연동 메뉴에 등록 필요)
4. 토큰 검증 후 정상일 경우 ‘문의하기’ 또는 ‘문의내역’ 페이지에 접속됩니다. 이때 검증에 실패할 경우 ‘문의하기’는 비회원으로 접수됩니다.

### 회원 연동 방법
![OpenAPI_GET회원연동](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-openapi-member-get_img0010.png)

개발 명세서에 따라 API를 개발한 후 **[서비스 관리 > 헬프센터 > 회원 연동]** 메뉴에 접속하여 아래와 같이 설정합니다.

**① 회원 연동 활성화**

- 회원 연동 기능을 사용하기 위해 '활성화' 버튼을 클릭합니다.

**② 비회원 문의 접수**

- 회원 연동 시 로그인 사용자만 문의를 접수 가능한지 설정합니다.
- 활성화 시 로그아웃 상태에서도 문의 접수가 가능해지며, 비활성화 시 로그인 사용자만 문의 접수가 가능하도록 통제됩니다.

**③ 로그인 타입**

- GET 방식을 선택합니다.

**④ Token 검증 URL**

- 헬프센터 호출 시 자체 서비스에서 전달한 토큰을 검증하기 위한 URL입니다.
- 아래 개발 명세서에 따라 개발한 **Token 검증 URL**을 입력한 후 **저장** 버튼을 클릭합니다.



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

### GET 회원인증 방법

#### 인터페이스 설명

URL

- https://{org}.oc.nhncloud.com/{service}/hc/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d
- https://{org}.oc.nhncloud.com/{service}/hc/ticket/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d
- https://{org}.oc.nhncloud.com/{service}/hc/ticket/list/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d

URL(개발)

- https://{domain}.oc.alpha-nhncloud.com/{service}/hc/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d
- https://{domain}.oc.alpha-nhncloud.com/{service}/hc/ticket/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d
- https://{domain}.oc.alpha-nhncloud.com/{service}/hc/ticket/list/?usercode=aaaabbb&username=yzg&email=yzgname@163.com&phone=12345678901&time=12345678&token=8NPaBegAfbSvh1Lna9M0I1wBqjnoRyKO2r2izhuEAng%3d
  
|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|GET 회원인증 |HTTPS |GET |UTF-8 | |서비스 측에서 헬프센터 접속 시, 고객정보 및 암호화 후 생성된 token 값을 파라미터로 URL에 추가해서 호출|

#### 파라미터
|명칭|변수|데이터 타입|필수|설명|
|----|-------|----------|----|---|
|서비스 ID|service|VARCHAR(50)|O|서비스 ID|
|유저 ID |usercode|VARCHAR(50)|O|유저ID(유니크 값)|
|유저 명  |username |VARCHAR(50) |X |유저 명|
|유저 이메일|email  |VARCHAR(100)|O|유저 이메일|
|전화번호   |phone   |VARCHAR(20) |X |전화번호|
|회원번호|memberno|VARCHAR(50)|X|회원번호|
|timestamp|time    |LONG        |O|시간 단위: 밀리초|
|인증 Token|token  |VARCHAR     |O|다음 파라미터 값과 조직 Key로 계산(SHA256). (선택사항 값이 null 혹은 없을 경우, token 생성에서 제외. 주의사항: 문자열에서 각 값의 순서는 다음과 동일해야 함) SHA256Digest(service + usercode + username + email + phone + memberno + returnUrl + time)|

##### 인증 Token 생성 시 주의사항

1. Token 생성 시, 한글이 있을 경우 한글로 직접 생성. 인코딩 필요 없음
2. 생성된 Token을 URL 파라미터로 사용 시, encodeURIComponent()로 인코딩 필요

#### 결과 데이터

- Token 인증 성공: 회원으로 접속하는 주소로 이동
- Token 인증 실패: 비회원으로 접속하는 주소로 이동
- Token 인증 실패 상태에서 문의내역으로 접속 시, 문의하기 화면으로 이동

### Token 검증 URL(서비스 측)

#### 인터페이스 설명

- URL: 서비스 측에서 지원
- URL(개발): 서비스 측에서 지원

|인터페이스 명|프로토콜|호출방향|인코딩|결과 형식|인터페이스 설명|
|------------|-------|--------|-----|--------|--------------|
|Token 검증 URL |HTTPS |GET |UTF-8 |JSON |서비스 측에서 token과 usercode로 로그인 상태 확인 후 JSON 형태 결과 값을 전송|

#### 요청 파라미터
|명칭|변수|데이터 타입|필수|설명|
|----|-------|----------|----|---|
|유저 ID|usercode|VARCHAR(50)|O|유저 ID(유니크 값)|
|서비스 측에서 생성한 Token|token|VARCHAR|O|사용자가 GET 방식을 통해 Online Contact에 로그인 시, Online Contact으로 전달하는 token|

#### Response Body
```
로그인:
{
"login": "true",
"usercode":"usercodeXXX"
}


로그아웃:
{
"login": "false",
"usercode": null
}
```
