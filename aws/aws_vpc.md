# Amazon VPC (Virtual Private Cloud)

## Amazon VPS란?
### Amazon EC2의 네트워킹 계층
**주요 개념**
- VPC : 사용자의 AWS 계정 전용 가상 네트워크
- 서브넷 : VPC의 IP 주소 범위
- 라우팅 테이블 : 네트워크 트래픽을 전달할 위치를 결정하는 데 사용하는 라우팅이라는 이름의 규칙 집합
- 인터넷 게이트웨이 - VPC의 리소스와 인터넷 간의 통신을 활성화 하기 위해 VPC에 연결하는 게이트웨이

출처 : [AWS Document](https://docs.aws.amazon.com/ko_kr/vpc/index.html)

## 보안 그룹
- 방화벽과 비슷한 역할
- 보안그룹과 연결된 인스턴스들의 접근을 제안
- 같은 기능을 사용할 경우 같은 보안그룹을 사용

## 탄력적 IP
- 인스턴스에 고정된  IP를 부여하는 기능
- 인스턴스의 연결이 끊겼다 다시 연결되어도 일정한 IP를 유지