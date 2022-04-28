# AWS CloudFront를 통해 Frontend 배포하기
## Amazon CloudFront란?
### Amazon CloudFront는 .html, .css, .js 및 이미지 파일과 같은 정적 및 동적 웹 콘텐츠를 사용자에게 더 빨리 배포하도록 지원하는 웹 서비스입니다. 
출처 : [AWS Document](https://docs.aws.amazon.com/ko_kr/AmazonCloudFront/latest/DeveloperGuide/Introduction.html)

- CDN (Content delivery network or content distribution network) 서비스와 유사한 기능을 제공

## [CloudFront 생성하기](https://us-east-1.console.aws.amazon.com/cloudfront/v3/home?region=ap-northeast-2#/welcome)
- Default Root Object : index.html (프론트 엔드 메인 페이지)

## Git Action을 통해 배포하기
- [TIL/git_action.md]()
- Front end source code Repository
    - [Test1](https://github.com/devpcjin/cloudfront-test)
    - [Test2](https://github.com/devpcjin/frontend-hw)


## 배포 확인하기
- CloudFront의 대체 도메인으로 접속해서 원하는 결과 나오는지 확인하기
