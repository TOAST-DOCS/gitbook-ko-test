## Security > Security Monitoring > 콘솔 사용 가이드

여기에서는 Security Monitoring 콘솔 사용 방법을 설명합니다.

Security Monitoring 서비스를 사용하려면 **NHN Cloud Console**에 로그인하고, 서비스 목록에서 **Security > Security Monitoring**을 클릭합니다.

## 보안관제 서비스 신청 및 해제
### 보안관제 대상 추가
1. Security Monitoring 콘솔에서 **신청 현황** 탭을 클릭하고 **보안관제 서비스 미이용 현황**에서 관제 서비스를 이용할 인스턴스를 선택합니다.
2. 선택된 목록을 확인한 뒤 **관제대상 추가** 버튼을 클릭해 관제 서비스를 신청합니다.
3. 신청 후 <span style="color:#ab4642">**최대 1시간 이내에**</span> 해당 인스턴스에 대한 관제 서비스가 시작됩니다. 관제 서비스가 진행되면 **보안관제 서비스 이용 현황** 아래 **관제 현황** 열의 '접수대기' 상태가 '진행중'으로 변경됩니다.

### 보안관제 대상 해제
1. **보안관제 서비스 이용 현황** 목록에서 보안관제를 해제할 인스턴스를 선택한 후 **관제대상 해제** 버튼을 클릭합니다.
해제 요청 후 <span style="color:#ab4642">**최대 1시간 이내**</span>에 해당 인스턴스에 대한 관제가 해제됩니다.

## 보안관제 업무 수신 설정
보안관제 서비스 중 발생하는 이벤트에 대해 수신 설정을 할 수 있습니다.

![securitymonitoring_console_guide_210625.png](http://static.toastoven.net/prod_mss/securitymonitoring_console_guide_220719.png)

### 긴급 건 유선 연락 허용

긴급한 보안 이벤트가 발생하면 유선으로 연락받도록 신청할 수 있습니다.

**긴급건 유선연락 허용**에서 **예**를 클릭합니다.

- 신청자와 유선 연락 수신인이 같을 때
  - **신청자와 유선연락 수신인 동일 여부**에서 **예**를 클릭하면 가입된 유선 연락처 정보로 신청됨
- 신청자와 유선 연락 수신인이 다를 때
 1. **신청자와 유선연락 수신인 동일 여부**에서 **아니요**를 클릭합니다.
 2. **수신 담당자**와 **연락처**에 정보를 입력합니다.

**위 개인정보 수집 및 이용에 동의합니다**를 선택합니다.

### 업무 처리 내역 메일 수신 신청

보안관제 대응 및 처리 내역을 이메일로 받을 수 있습니다. 이메일 주소는 세미콜론(;)으로 구분해 여러 개를 입력할 수 있습니다.

3. **업무처리내역 메일 수신 신청**에서 **예**를 클릭합니다.
4. **이메일 주소**에 정보를 입력하고 **위 개인정보 수집 및 이용에 동의합니다**를 선택합니다.

## 보안관제 현황 확인
- **관제 현황** </span>  탭에서 보안관제 서비스를 신청한 인스턴스의 보안관제 대응 현황을 확인할 수 있습니다. 
  - 보안관제 대응 목록은 최근 1년 데이터만 검색할 수 있습니다.

![securitymonitoring_console_guide_210625_1.png](http://static.toastoven.net/prod_mss/securitymonitoring_console_guide_220719_1.png)

## 상세 이벤트 현황 확인
- **상세 이벤트 현황** </span>  탭에서 보안관제 서비스를 신청한 인스턴스의 상세 이벤트 현황을 확인할 수 있습니다. 
  - 상세 이벤트 목록은 최근 3개월 데이터만 검색할 수 있습니다.

![securitymonitoring_console_guide_210625_2.png](http://static.toastoven.net/prod_mss/securitymonitoring_console_guide_220719_2.png)