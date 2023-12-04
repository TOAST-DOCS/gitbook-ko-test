## Security > Security Advisor > 개요

Security Advisor는 고객이 생성한 NHN Cloud 조직 및 프로젝트 리소스의 보안 설정 상태를 점검하고 권장 가이드를 제시하는 서비스입니다. <br> 안전한 클라우드 환경을 위해 권장 가이드를 활용할 수 있습니다.<br>Security Advisor는 프로젝트 단위로 활성화되고 특정 리전에서 서비스를 활성화하면 다른 모든 리전에도 서비스가 활성화됩니다.<br>단, 리전마다 제공되는 클라우드 서비스가 다르므로 점검 대상 및 범위는 차이가 있습니다.

## 주요 기능
* NHN Cloud 조직의 거버넌스 설정을 점검하고 권장 조치 방법을 적용하여 클라우드 환경의 안전성을 높일 수 있습니다.
* NHN Cloud 프로젝트에 속한 장기 미사용 계정을 점검하고 권장 조치 방법을 안내합니다.
* Security Groups를 점검하여 인스턴스에 적용된 보안 규칙을 확인할 수 있습니다.
* RDS에 대한 접근 설정을 점검하여 불필요한 접근을 차단할 수 있습니다.
* 주기적인 자동 점검 기능을 제공하고 결과를 이메일로 전송할 수 있습니다.

## 점검 대상 및 서비스 리전
### 선택 점검 리전 별 지원 범위
|구분|지원 리전|
|---|---|
|조직으로 구분된 점검 항목|한국(판교) 리전, 한국(평촌) 리전, 일본(도쿄) 리전, 미국(캘리포니아) 리전|
|프로젝트로 구분된 점검 항목|한국(판교) 리전, 한국(평촌) 리전, 일본(도쿄) 리전|

### 선택 점검 항목의 프로젝트 항목 점검 대상 리소스
|구분&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|점검 항목|대상 리소스|비고|
|---|---|---|---|
|프로젝트 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |Security Groups 점검|Instance, Security Groups|Database Instance, NKS 클러스터 제외|
|프로젝트 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Database Security Groups 점검|Database Instance(MS-SQL Instance, MySQL Instance, PostgreSQL Instance, CUBIRD Instance, MariaDB Instance, Tibero Instance, Redis Instance), Security Groups|
|프로젝트 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |RDS 접근제어 점검 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|RDS for MySQL, RDS for MariaDB, RDS for MS-SQL|RDS for MariaDB, RDS for MS-SQL는 판교 리전에서만 서비스되므로 판교 리전에서만 점검 가능|

## 프로젝트 멤버 서비스 이용 역할

Security Advisor는 프로젝트 서비스입니다.
프로젝트 관리자는 프로젝트에 등록된 NHN Cloud 회원 또는 IAM 멤버에 역할을 부여할 수 있습니다.

|서비스|역할|설명&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|---|---|---|
|Security Advisor|ADMIN|Security Advisor의 모든 서비스를 관리할 수 있습니다.<br> - Security Advisor 서비스 Create(생성), Read(읽기), Update(갱신), Delete(삭제)<br><br>Security Advisor 서비스가 제공하는 모든 기능을 사용할 수 있습니다.<br>- 대시보드 보기, 엑셀 저장<br>- 점검 항목 선택 점검, 점검 항목 기본 정보 보기, 탐지 리소스 보기, 탐지 리소스 선택 예외, 예외 리소스 보기, 예외 리소스 예외 해제<br>- 결과 수신 설정, 자동 점검 설정|
||PERMISSION|Security Advisor 서비스를 활성화하거나 비활성화할 수 있습니다.<br>- 서비스 Enable(활성화), Disable(비활성화)|
||VIEWER|Security Advisor 서비스 점검 결과를 확인할 수 있습니다.<br>- 대시보드 보기, 엑셀 다운로드<br>- 점검 항목 기본 정보 보기, 탐지 리소스 보기, 예외 리소스 보기<br>* VIEWER 역할에는 '설정' 화면을 제공하지 않습니다.|

## 서비스 사용 절차
### 서비스 활성화 절차
서비스 활성화 권한을 가진 계정으로 NHN Cloud에 로그인합니다. Security 카테고리에서 Security Advisor를 클릭하여 서비스를 활성화합니다.
![이미지1](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_01.png)

### 서비스 비활성화 절차
서비스 활성화 권한을 가진 계정으로 NHN Cloud에 로그인합니다. 프로젝트 이름 옆의 톱니바퀴 아이콘을 클릭하여 **프로젝트 관리** 메뉴로 진입합니다.
**이용 중인 서비스**에서 Security Advisor 항목의 **비활성화**를 클릭하여 서비스를 종료합니다.
![이미지2](https://kr1-api-object-storage.nhncloudservice.com/v1/AUTH_2acdfabf4efe4efc8a04c00b348110c9/cdn_origin/prod_securityadvisor/overview_02.png)
