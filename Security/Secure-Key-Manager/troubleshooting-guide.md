## Security > Secure Key Manager > 문제 해결 가이드
Secure Key Manager를 사용하면서 발생할 수 있는 주요 문제에 대한 해결 방법을 설명합니다.

### API 호출이 실패하면서 Invalid Appkey 오류 메시지를 반환합니다.
* API 호출에 사용한 앱키가 유효하지 않을 때 발생합니다.
    * Secure Key Manager 관리 페이지의 URL & Appkey 창에 표시되는 올바른 앱키를 사용하셨는지 확인하십시오.

### API 호출이 실패하면서 Invalid Key Id 오류 메시지를 반환합니다.
* API 호출에 사용한 Key Id가 유효하지 않을 때 발생합니다.
    * 올바른 Key Id를 사용하셨는지 확인하십시오.
    * Key가 사용 중인 상태인지 확인하십시오.
    
### API 호출이 실패하면서 Invalid Key Version 오류 메시지를 반환합니다.
* API 호출에 사용한 Key Version이 유효하지 않을 때 발생합니다.
    * 대칭키 복호화 API에서 발생했다면, 암호화 당시 사용했던 키 버전이 존재하는지 확인하십시오.
    * 비대칭키 검증 API에서 발생했다면, 서명 당시 사용했던 키 버전이 존재하는지 확인하십시오.

### API 호출이 실패하면서 Invalid User Data 오류 메시지를 반환합니다.
* API 호출에 사용한 사용자 데이터가 유효하지 않을 때 발생합니다.
    * 대칭키 복호화 API에서 발생했다면, 복호화 대상 데이터가 올바른지 확인하십시오.
    * 비대칭키 검증 API에서 발생했다면, 서명값이 올바른지 확인하십시오.

### API 호출이 실패하면서 Invalid Key Status 오류 메시지를 반환합니다.
* API 호출에 사용한 Key의 상태가 유효하지 않을 때 발생합니다.
    * 대칭키 복호화 API에서 발생했다면, 암호화 당시 사용했던 키가 '사용중' 상태인지 확인하십시오.
    * 비대칭키 검증 API에서 발생했다면, 서명 당시 사용했던 키가 '사용중' 상태인지 확인하십시오.

### API 호출이 실패하면서 Invalid Key Version Status 오류 메시지를 반환합니다.
* API 호출에 사용한 Key Version의 상태가 유효하지 않을 때 발생합니다.
    * 대칭키 복호화 API에서 발생했다면, 암호화 당시 사용했던 키 버전이 '사용중' 상태인지 확인하십시오.
    * 비대칭키 검증 API에서 발생했다면, 서명 당시 사용했던 키 버전이 '사용중' 상태인지 확인하십시오.
    
### API 호출이 실패하면서 IPv4 Auth Failure 오류 메시지를 반환합니다.
* IPv4 주소 인증에 실패했을 때 발생합니다.
    * API를 호출하는 클라이언트의 IPv4 주소를 Secure Key Manager에 등록했는지 확인하십시오.
    * Secure Key Manager에 등록한 클라이언트의 IPv4 주소가 '사용중' 상태인지 확인하십시오.

### API 호출이 실패하면서 MAC Auth Failure 오류 메시지를 반환합니다.
* MAC 주소 인증에 실패했을 때 발생합니다.
    * API를 호출하는 클라이언트의 MAC 주소를 Secure Key Manager에 등록했는지 확인하십시오.
    * Secure Key Manager에 등록한 클라이언트의 MAC 주소가 '사용중' 상태인지 확인하십시오.
    * API를 호출할 때 X-TOAST-CLIENT-MAC-ADDR 요청 헤더에 클라이언트의 MAC 주소를 추가했는지 확인하십시오.

### API 호출이 실패하면서 Certificate Auth Failure 오류 메시지를 반환합니다.
* 클라이언트 인증서 인증에 실패했을 때 발생합니다.
    * Secure Key Manager에서 발급한 인증서를 사용하는지 확인하십시오.
    * Secure Key Manager에 등록한 인증서가 '사용중' 상태인지 확인하십시오.

### API 호출이 실패하면서 인증서 관련 오류 메시지를 반환합니다.
* 인증서가 올바르지 않을 때 발생합니다.
    * Secure Key Manager에서 발급한 인증서를 사용하는지 확인하십시오.
    * 인증서의 유효 기간을 확인하십시오.
    
##### 이밖에 API 요청 중 발생한 오류에 대해서는 고객 센터([support@toast.com](mailto:support@toast.com))로 문의해 주시기 바랍니다 
