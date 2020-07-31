<p align="center">
  <a href="" target="blank"><img src="serverless.png" width="200" height="200" alt="Serverless Logo" /></a>
</p>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)


# 서비리스(Serverless)

서버리스란, 서버가 없다는 의미입니다. 하지만 서버가 없는 것이 아니라 "서버를 관리할 필요가 없는" 뜻 입니다. 
그렇다면 어떻게 서버를 대신해 준다는 걸까요? 내부적으로는 FaaS(Function as a Service) 혹은 BaaS(Backend as a Service) 정의되는 기술을 사용해서 서버를 대체하게 됩니다.


:heavy_exclamation_mark: 용어
> FaaS(Function as a Service)? 함수(or 람다)만 개발하고 나머지 서버들의 역할을 서비스를 제공하는 쪽(AWS, AZURE, GCP)에서 담당하겠다는 방식
> BaaS(Function as a Service)? 모바일에 특화된 백엔드 개발 서버를 대신해 주는 역할을 하는 방식을 의미함. 


## 최종 목표
<img src="overview.png" height="200" alt="Serverless Logo" />

 - Route53◊
 - SSL
 - CloudFront
 - S3
 - Auth0
 - Lambda
 - DyanmoDB


## 시작하기

서버리스 프레임워크를 설치하고 프로젝트를 하나 만든 후에 배포 해보자.

> 사전작업: [Node] 설치에서 Node를 설치하면 `npm`이 설치된다.

- 서버리스 프레임워크 설치
```
$ npm install serverless -g
...
> serverless@1.77.1 postinstall /Users/kim.hyunsung/superb/tutorials/serverless-basic/node_modules/serverless
> node ./scripts/postinstall.js


   ┌───────────────────────────────────────────────────┐
   │                                                   │
   │   Serverless Framework successfully installed!    │
   │                                                   │
   │   To start your first project run 'serverless'.   │
   │                                                   │
   └───────────────────────────────────────────────────┘

$ sls --version
Framework Core: 1.60.5
Plugin: 3.2.7
SDK: 2.2.1
Components Core: 1.1.2
Components CLI: 1.4.0
```

- 프로젝트 생성
```
$ sls create --template hello-world
Serverless: Generating boilerplate...
 _______                             __
|   _   .-----.----.--.--.-----.----|  .-----.-----.-----.
|   |___|  -__|   _|  |  |  -__|   _|  |  -__|__ --|__ --|
|____   |_____|__|  \___/|_____|__| |__|_____|_____|_____|
|   |   |             The Serverless Application Framework
|       |                           serverless.com, v1.60.5
 -------'

Serverless: Successfully generated boilerplate for template: "hello-world"
Serverless: NOTE: Please update the "service" property in serverless.yml with your service name
```

- 프로젝트 생성 결과
```
$ tree -L 1 .
.
├── LICENSE
├── handler.js
├── node_modules
├── package-lock.json
└── serverless.yml
```

- 배포
```
$ sls deploy or serverless deploy
Serverless: Packaging service...
Serverless: Excluding development dependencies...
Serverless: Creating Stack...
Serverless: Checking Stack create progress...
........
Serverless: Stack create finished...
Serverless: Uploading CloudFormation file to S3...
Serverless: Uploading artifacts...
Serverless: Uploading service serverless-basic.zip file to S3 (35.17 MB)...
Serverless: Validating template...
Serverless: Updating Stack...
Serverless: Checking Stack update progress...
.................................
Serverless: Stack update finished...
Service Information
service: serverless-basic
stage: dev
region: us-east-1
stack: serverless-basic-dev
resources: 12
api keys:
  None
endpoints:
  GET - https://urxi5ygey0.execute-api.us-east-1.amazonaws.com/dev/hello-world
functions:
  helloWorld: serverless-basic-dev-helloWorld
layers:
  None
Serverless: Run the "serverless" command to setup monitoring, troubleshooting and testing.


   ╭───────────────────────────────────────╮
   │                                       │
   │   Update available 1.60.5 → 1.77.1    │
   │   Run npm i -g serverless to update   │
   │                                       │
   ╰───────────────────────────────────────╯

```

- 프로젝트 제거
```
$ sls remove
Serverless: Getting all objects in S3 bucket...
Serverless: Removing objects in S3 bucket...
Serverless: Removing Stack...
Serverless: Checking Stack removal progress...
.............
Serverless: Stack removal finished...
```
---

## 내부 살펴보기

- Serverless.yml 구성
- 람다 구조

## 프론트엔드 작업하기

- Route53 & Custom Domains

- Creating SSL

- Creating CloudFront Distribution

- Invalidating the Cache


## 백엔드 작업하기

- DB 만들기

- API 서비스 만들기

- 엔드 포인트 연결

- 인증


## TODO
- [ ] 로컬 테스트하기
- [ ] 안전하게 배포하기
- [ ] 다른 언어로 사용하기

## Reference
- [Full stack Serverless](https://www.serverless.com/learn/courses/full-stack-application-development-on-aws/)
- [Serverless Install](https://velopert.com/3549)