## Network > Private DNS > 개요

Private DNS는 VPC 별로 독립된 DNS를 구성 할 수 있습니다. 별도의 DNS 솔루션이나 서버 없이 웹콘솔에서의 설정으로 VPC 내의 인스턴스에서 접근 가능한 DNS 서비스를 할 수 있습니다.

## 주요 기능
- VPC 별로 독립된 DNS를 구성할 수 있습니다.
- 별도의 DNS 솔루션이나 서버 없이 콘솔을 통한 설정만으로 VPC 내의 인스턴스에서 접근 가능한 DNS 서비스를 구성할 수 있습니다.
- 하나의 Zone(도메인 영역)에 한 개 이상의 VPC를 연결할 수 있습니다. 
- Zone을 외부에서 요청하는 경우 응답을 받을 수 없습니다. 
- VPC 내의 인스턴스는 VPC에 연결된 Zone뿐만 아니라, 외부 등록기관을 통해 등록된 도메인(ex. nhncloud.com)에 대한 요청에도 응답을 받을 수 있습니다. 
- Private DNS를 사용하는 VPC에는 프라이빗 IP DNS(로컬 도메인)가 제공됩니다. 
- VPC 내의 인스턴스는 별다른 설정 없이 프라이빗 IP DNS로 접근 가능합니다.

## 서비스 대상

- VPC 내에서만 접근 가능한 도메인 설정이 필요한 경우
- NHN Cloud 서비스와 연동을 위해 설정이 필요한 경우

## 서비스 용어

| 용어 | 설명 |
|---|---|
| 도메인 | 네트워크에서 컴퓨터를 식별하는 주소를 사람이 쉽게 인식할 수 있는 형태로 나타낸 방법입니다. |
| DNS Zone | DNS가 서비스하는 호스트의 도메인 영역입니다. 레코드 세트의 컨테이너이며 도메인과 하위 도메인의 트래픽을 라우팅하는 방법을 포함하고 있습니다. |
| 레코드 세트 | DNS Zone으로 서비스하는 호스트 정보로, 도메인의 트래픽을 라우팅하는 방법입니다. |
| 레코드 세트 타입 | 호스트의 트래픽을 라우팅하는 방법을 나타내는 리소스 유형입니다. |
| 레코드값 | 호스트의 트래픽을 라우팅하는 방법을 기술한 것으로 레코드 세트 타입(리소스 유형)에 따라 입력 내용이 결정되며 특정 유형을 제외하고 하나 이상 등록할 수 있습니다. |