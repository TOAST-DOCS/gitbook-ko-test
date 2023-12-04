## Content Delivery > CDN > 개요

CDN 서비스를 이용해 배포할 원본 콘텐츠를 원본 서버에 저장해 두면, 전 세계 캐시 서버로 콘텐츠가 배포됩니다. 최종 사용자는 가장 가까운 캐시 서버에서 빠른 속도로 파일을 전송받을 수 있습니다.

또한, 서비스 제공자가 CDN 서비스를 이용하면 트래픽 대부분을 캐시 서버에서 처리하기 때문에 원본 서버의 트래픽 폭주로 인한 서비스 장애를 사전에 방지하여 원본 서버의 가용률을 높일 수 있습니다.

콘텐츠를 최종 사용자에게 전달할 때, 일반 인터넷망이 아닌 전용선을 사용하여 더욱 높은 품질의 서비스를 제공할 수 있어 서비스 신뢰도도 높일 수 있습니다.

## 주요 기능

- 캐시 설정으로 사용자 접근을 제어할 수 있습니다.<br/>
  리퍼러(referrer) 정보를 이용해 사용자 콘텐츠 접근 여부를 관리할 수 있습니다. 정규 표현식 형태로도 입력할 수 있으며 동시에 여러 리퍼러를 제어할 수 있습니다.
- 캐시 만료 시간을 원하는 대로 설정할 수 있습니다.
- 캐시 재배포<br/>
  원본 콘텐츠가 변경되면 기존에 지정된 캐시 만료 시간 이후에 새로운 콘텐츠로 캐시가 업데이트됩니다. 하지만 '캐시 재배포' 기능을 이용하면 빠르게 기존 캐시를 새 콘텐츠로 업데이트할 수 있습니다.
- 글로벌 네트워크<br/>
전 세계 캐시 서버를 이용해 빠른 속도의 서비스를 제공합니다.
- HTTP/2 프로토콜 지원<br/>
  생성하는 모든 CDN 서비스에 대해 HTTP/2 프로토콜을 기본 지원합니다. 별도의 설정 없이 HTTP/1, HTTP/1.1, HTTP/2 프로토콜을 이용할 수 있습니다.