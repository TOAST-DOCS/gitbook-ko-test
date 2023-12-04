## Contact Center > Online Contact > 서비스 가이드 > 서비스 가입 및 기본 설정

## 회원 가입
### NHN Cloud 회원가입
![서비스가입_회원가입](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0010.png)

Online Contact는 NHN Cloud 회원가입 후 이용할 수 있습니다.

NHN Cloud 홈페이지 우측 상단의 **회원가입** 버튼을 클릭하여 회원 가입을 진행할 수 있으며, 사업자 회원의 경우 **사업자등록증**을 첨부해야 하므로 미리 준비해주십시오.

### 결제수단 등록
![서비스가입_결제수단등록](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0020.png)

NHN Cloud 서비스를 이용하기 위해서는 결제수단을 반드시 등록해야 합니다.

- 회원가입을 완료하면 로그인 시 **마이페이지 → 결제수단** 화면으로 이동됩니다.
- 페이지를 벗어났다면 **① 우측 상단 이메일 계정 클릭** → **② 결제수단**으로 접근할 수 있습니다.
- 해당 화면에서 **③ 결제 수단 추가** 버튼을 클릭하여 요금을 결제할 카드를 등록합니다.
- 결제 수단은 PAYCO에 등록된 신용카드 또는 소지중인 신용카드를 등록할 수 있으며 체크카드는 등록이 불가합니다.

### 콘솔 실행
![서비스가입_콘솔실행](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0030.png)

결제수단 등록 후 NHN Cloud 홈페이지 상단 **CONSOLE** 버튼을 클릭하여 NHN Cloud CONSOLE로 이동합니다.

NHN Cloud CONSOLE에서는 Online Contact를 비롯한 다양한 서비스 및 조직, 멤버 등을 관리할 수 있습니다.

## 서비스 활성화

### 조직 생성
![서비스가입_조직생성](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0040.png)

NHN CLOUD의 서비스 사용을 위해서는 조직을 먼저 생성해야합니다.
기존 생성된 조직이 있을 경우 Online Contact를 사용할 조직을 선택한 후 다음 단계로 이동합니다.

- 조직을 생성하려면 CONSOLE 화면 좌측 상단의 **"조직을 생성해 주세요"** 영역을 클릭합니다.
- **조직 생성 대화상자**가 실행되며, 생성할 조직의 이름을 입력합니다.
- **확인** 버튼을 클릭하면 조직이 생성됩니다.

### 서비스 선택 및 설정
![서비스가입_서비스선택](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0050.png)

Online Contact 서비스를 활성화하려면 아래와 같이 설정합니다.

**① 서비스 선택**

- 조직 생성 후 화면 상단의 **서비스 선택**을 클릭합니다.
- NHN Cloud에서 제공하는 서비스 목록이 나타나며, 목록 중 **Online Contact**을 클릭합니다.

**② 조직/도메인 설정**

- Online Contact를 사용할 조직과 도메인을 설정합니다.
- **조직이름**은 CONSOLE에서 선택한 조직이 기본 입력되어 있으며, 다른 조직으로 변경하거나 추가할 수 있습니다.
- **도메인**은 Online Contact 접속 시 사용되는 URL로, `https://{도메인이름}.oc.nhncloud.com/` 형태로 제공됩니다.
- 도메인 이름을 작성한 후 **저장**을 클릭하면 중복체크 후 도메인이 생성됩니다.

**③ IAM 멤버 등록**

- Online Contact를 이용할 멤버를 등록합니다.
- **IAM 멤버 등록** 버튼을 클릭한 후 ID, 이름, 이메일 주소를 입력하여 계정을 등록하며 여러 명의 멤버를 등록할 수 있습니다.
- 등록한 메일 주소로 비밀번호 설정 메일이 발송되며, 해당 메일을 통해 각각 비밀번호 설정 후 서비스를 이용할 수 있게 됩니다.
- 등록한 IAM 멤버 중 **OWNER** 계정으로 사용할 ID를 체크한 후 **다음** 버튼을 클릭하면 서비스 생성이 완료됩니다.

> **※ 참고사항**
>
> NHN Cloud의 계정은 아래와 같이 두 가지로 구분됩니다.
> 
> - **NHN Cloud 회원**: NHN Cloud에 가입된 회원으로 **NHN Cloud 전체 서비스 및 조직을 관리하는 회원**입니다.
> - **IAM 멤버**: 조직 내부 회원으로 **조직 내에서만 유효한 멤버**입니다. NHN Cloud 인증을 하지 않은 아이디로 생성되며, NHN Cloud CONSOLE의 **멤버 관리 → IAM 멤버** 탭에서 추가할 수 있습니다.

**④ 완료**

- 서비스 준비 완료 안내와 함께 **Online Contact URL**과 **OWNER** 권한을 가진 계정이 표시되며, 해당 링크를 통해 Online Contact 서비스에 접속할 수 있습니다.
- **로그인 보안 설정**을 클릭하면 2차 인증, 로그인 실패 시 처리, 세션 등을 관리할 수 있습니다. 자세한 내용은 [로그인 보안 설정 가이드](https://docs.nhncloud.com/ko/nhncloud/ko/console-guide/#iam)를 참고하십시오.

## 접속 및 로그인
![서비스가입_서비스선택](https://static.toastoven.net/prod_contact_center/OC3.0/kr/online-contact-guide-primary-setting_img0060.png)

서비스가 활성화되면 Online Contact 페이지에 접속하여 서비스를 이용할 수 있습니다.

**① URL을 통한 접속**

- Online Contact는 아래와 같이 서비스 활성화 단계에서 입력했던 **도메인 이름**을 통해 접속할 수 있습니다.
- `https://{도메인이름}.oc.nhncloud.com/`

**② CONSOLE을 통한 접속**

- NHN Cloud 회원이라면, **CONSOLE 내 조직 서비스 이용 현황**에서 Online Contact를 클릭하여 접속할 수 있습니다.

**③ IAM 멤버 로그인**

- Online Contact 접속 시 로그인 화면이 나타나며, 등록했던 **IAM 멤버로 로그인**합니다.
- 최초로 접속한 경우 Online Contact 내에서 계약 정보, 조직 관리자 등을 설정해야하므로 **OWNER ID**로 로그인한 후 설정을 진행합니다.
- 로그인 시 비밀번호를 잊었다면 **비밀번호 찾기**를 클릭합니다. IAM 회원 등록 시 기재한 이메일로 비밀번호 재설정 메일이 전송되며 해당 메일을 통해 비밀번호를 변경할 수 있습니다.

✔ **\[FAQ 바로가기]** [비밀번호를 변경하고 싶습니다.](https://nhn-contact.oc.nhncloud.com/oc/hc/article/35/)