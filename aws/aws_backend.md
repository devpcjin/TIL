# AWS Elastic Beanstalk를 통해 Frontend 배포하기
## AWS Elastic Beanstalk 이란?
### Elastic Beanstalk를 사용하면 애플리케이션을 실행하는 인프라에 대해 자세히 알지 못해도 AWS 클라우드에서 애플리케이션을 신속하게 배포하고 관리할 수 있습니다.
출처 : [AWS Document](https://docs.aws.amazon.com/ko_kr/elastic-beanstalk/index.html)

## [Elastic Beanstalk 생성하기](https://ap-northeast-2.console.aws.amazon.com/elasticbeanstalk/home?region=ap-northeast-2#/welcome)
- 어플리케이션 이름 설정
- 알맞는 플랫폼 선택 (Python으로 해봤음)
- 샘플 애플리케이션 선택
- 제공된 URL에 접속해서 샘플 어플리케이션이 잘 작동하는지 확인
- IAM에 권한 추가하기
    - elasticbeanstalk에 해당하는 알맞은 권한 추가

## Git Action을 통해 배포하기
- [TIL/git_action.md]() 참고
- Front end source code Repository
    - [Test1](https://github.com/devpcjin/my-backend)
    - [Test2](https://github.com/devpcjin/backend-hw)

## 배포 확인하기
- Front-end와 연동 확인하기
    - Front-end (CloudFront)로 접속하여 정상적으로 동작하는지 확인하기