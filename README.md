# 📎 Link 
https://github.com/to1step/backend

<br />

# ⚒️ Project Architecture 

<img src="https://github.com/gkqkehs7/to1step-Backend/assets/77993709/7dffea09-46a1-4c9e-a858-ea8b4f63e6ac" />

<br/>

## 🔍 Node.js (v16)

### nvm을 통한 버전 일치

팀원들이 각자의 로컬에서 개발을 하였기 때문에, 각자 데스크톱의 `node.js`버전이 달라 발생하는 에러를 방지하기 위해 `nvm`을 통해 `node.js`의 버전을 16으로 일치시켰습니다.

✏️ [nvm을 이용한 node.js 버전 관리](https://velog.io/@gkqkehs7/nvm%EC%9D%84-%ED%86%B5%ED%95%9C-node.js-%EB%B2%84%EC%A0%BC-%EA%B4%80%EB%A6%AC)

<br/>

### REST의 원칙을 지키는 API설계

REST의 원칙을 지켜 간결하고 가독성이 좋은 API를 설계하였고, UI에 묶이지 않는 API를 설계하여 API의 확장성을 높였습니다.

✏️ [REST API란?](https://velog.io/@gkqkehs7/REST-API%EB%9E%80) | ✏️ [REST 원칙을 지키며 API를 설계하자](https://velog.io/@gkqkehs7/%EB%8B%A4%EB%A5%B8-%EC%82%AC%EB%9E%8C%EC%9D%B4-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-%ED%9E%98%EB%93%A0-%EC%9E%98%EB%AA%BB%EB%90%9C-API-%EC%84%A4%EA%B3%84) | ✏️ [API는 UI에 종속되지 않아야 한다](https://velog.io/@gkqkehs7/API%EB%8A%94-ui%EC%97%90-%EC%A2%85%EC%86%8D%EB%90%98%EC%A7%80-%EC%95%8A%EC%95%84%EC%95%BC%ED%95%9C%EB%8B%A4)

<br/>

### Controller와 Service의 역할 분리

`Controller`와 `Service`의 역할을 철저히 분리하여 `Controller`는 클라이언트 요청을 처리하고 응답을 반환하는 역할을 수행하도록 하였고, `Service`는 비즈니스 로직을 처리하는 역할을 수행하도록 하였습니다.

✏️ [Controller와 Service의 역할 분리](https://velog.io/@gkqkehs7/Controller%EC%99%80-Service-%EB%B6%84%EB%A6%AC)

<br/>

### class-validator를 통한 유효성 검사

`class-validator` 를 사용하여 사용자로부터 입력받은 데이터나 외부에서 받은 데이터를 검증하여 잘못된 데이터가 데이터베이스에 들어가는 것을 방지하였습니다.

<br/>

### Dev-dependency 분리를 통한 빌드 경량화

개발 단계에서만 사용되고, 실제 프로덕션 환경에서는 필요하지 않은 패키지들은 **`devDependenc`** 로 별도 분리하여 설치하여 프로덕션 빌드 시에 더 가볍고 효율적인 빌드를 할 수 있게 하였습니다.

<br/>

### Day.js를 이용한 시간 통일

저희의 클라우드 서버가 한국에 존재하지 않기 때문에, 모든 시각을 한국 시간으로 통일해 주기위해 날짜 라이브러리를 도입하여야 했는데, 그 중 크기가 작고 가벼워 가장 많이 사용되는 day.js를 채택하였습니다.

<br/>

### Cutsom Error를 통한 Front-end와의 소통

서버에서 발생할 수 있는 에러를 `BadRequestError` , `UnauthorizedError` , `ForbiddenError` , `InternalServerError` , `NotFoundError` 로 나누어 class화 하고 Front-end가 처리할 수 있는 에러들에 대해선 ErrorCode들을 미리 enum type으로 정의해 둔 다음, 해당 에러에 맞는 class로 mapping하여  Front-end와 소통하였습니다.

✏️ [Custom Error를 이용한 Front-end와의 소통](https://velog.io/@gkqkehs7/Custom-Error%EB%A5%BC-%ED%86%B5%ED%95%9C-front-end%EC%99%80%EC%9D%98-%EC%86%8C%ED%86%B5)

<br/>

### Winston.js를 통한 로그 기록

`Winston.js`를 이용하여 서버에 들어오는 모든 요청, 서버에서 발생하는 모든 에러에 대해 파일로 기록하였습니다.

✏️ [Winston.js를 통한 로그 기록하기](https://velog.io/@gkqkehs7/Winston%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-logger)

<br/>

### Discord.js를 통한 Exception Error 핸들링과 API 개선

서버에서 발생하는 Exception Error에 대해 `Discord.js`를 통해 Discord로 메세지를 보내게 하여 바로 대응할 수 있도록 하였고, API소요시간을 계산하여 2000ms 이상 걸리는 API에 대해서 Discord로 메세지를 보내 로직을 개선할 수 있게 하였습니다.

✏️ [API소요시간 계산하기](https://velog.io/@gkqkehs7/API-%EC%86%8C%EC%9A%94%EC%8B%9C%EA%B0%84-%EA%B3%84%EC%82%B0) | ✏️ [Discord.js를 통한 Error-bot 만들기](https://velog.io/@gkqkehs7/Discord.js%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-Error-bot-%EB%A7%8C%EB%93%A4%EA%B8%B0)

<br/>

## 🔍 Typescript (v5.1.3)

`Node.js` 는 빠르고 간단하게 API를 만들 수 있다는 것에 강점이 있다고 생각합니다. 하지만 서버는 안정성이 최우선이므로, `TypeScript`를 통해 동적타입 언어인 `Javascript` 에서는 검사하지 못했던 변수, 함수, 인터페이스 등의 타입 오류를 사전에 최대한 차단하였고. 이로 인해 런타임 시점의 타입 관련 버그를 사전에 방지 하였습니다.

<br/>

## 🔍 Prettier

코드 스타일을 일관성 있게 유지하고 흔히 발생하는 실수나 잠재적인 오류를 사전에 감지하기 위해 `prettier`를 사용하였습니다.

```tsx
"lint-staged": {
  "./src/**/*.{ts,tsx,js,jsx}": [
    "eslint --fix"
  ]
}
```

<br/>

## 🔍 Husky

오류가 있는 코드나 lint에 맞지 않는 코드가 올라와 develop에 merge되는 것을 막기위해 `Husky` 를 사용하여 commit과 push에 정책을 적용하였습니다.

### pre-commit

```tsx
> npm run lint-staged
```

`lint-staged` 명령어를 통해 변경된 파일들만 대상으로 lint를 실행하여 commit 전에 에러를 확인하였습니다.
<br/>

### pre-push

```tsx
> tsc --noEmit
```

`tsc --noEmit` 명령어를 통해 TypeScript 파일을 컴파일하여 JavaScript 파일을 생성하지 않고, 타입 검사만 수행한 다음, 통과하면 push가 되도록 하였습니다.

✏️ [Husky를 이용한 git hook 적용하기](https://velog.io/@gkqkehs7/Husky-git-hook-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0)

<br/>

## 🔍 Jest

### Jest를 통한 테스트 주도 개발

Jest 라이브러리를 이용하여 API를 작성할때 해당 API에 대해서 테스트를 작성하여 버그를 빠르게 감지하고 코드의 안정성을 높였습니다. 
또한 husky를 통해 push전에 테스트를 진행하여 테스트를 통과하지 못한 API가 있을시에 코드가 병합되지 않게 조치하였습니다.

✏️ [Jest를 통한 테스트 주도 개발](https://velog.io/@gkqkehs7/jest%EB%A5%BC-%ED%86%B5%ED%95%9C-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%A3%BC%EB%8F%84-%EA%B0%9C%EB%B0%9C)

<br/>

## 🔍 Docker

### 일관성 있는 배포

Docker 컨테이너가 애플리케이션과 그 실행에 필요한 모든 종속성들을 포함하고 있기 때문에, 우리의 서비스를 Docker로 컨테이너화 하여 개발 환경과 프로덕션 환경 사이의 일관성을 유지하였습니다. 또한 다양한 플랫폼과 환경에서 일관성 있게 배포할 수 있게 하였습니다.

<br/>

### 효율적인 자원 관리

Docker는 호스트 OS와 리소스를 공유하여 실행되어 가상화 방식에 비해 더 적은 리소스를 소비하기 때문에 우리의 서비스를 Docker로 컨테이너화 하여 더 효율적인 자원 관리와 높은 서버 활용률을 얻을 수 있게 하였습니다.

✏️ [Docker란 무엇이고 왜 사용할까?](https://velog.io/@gkqkehs7/%EB%8F%84%EC%BB%A4%EC%9D%98-%EC%9D%B4%EB%AF%B8%EC%A7%80%EC%99%80-%EC%BB%A8%ED%85%8C%EC%9D%B4)

<br/>

### .dockerignore를 이용한 이미지 경량화

`.dockerignore` 에 Docker 이미지를 빌드할 때 포함하지 않을 파일이나 디렉토리를 지정하여, 이미지 크기를 경량화 하였습니다.

✏️ [Docker 이미지 경량화 하기](https://velog.io/@gkqkehs7/Docker%EB%A1%9C-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EB%B9%8C%EB%93%9C-%EB%B0%8F-%EA%B2%BD%EB%9F%89%ED%99%94)

<br/>

### Docker-compose를 이용한 컨테이너 관리

`docker-compose.yml` 파일에 컨테이너를 실행하는데 필요한 네트워크, 볼륨, 환경 변수 등을 정의하여. 가독성이 좋게 하였고, 애플리케이션 구성을 이해하고 공유하기 쉽게 하였습니다.

<br/>

## 🔍 Github action

### CI

`docker/build-push-action@v4` 를 이용하여 DockerFile에 작성된 대로 우리의 서비스를 이미지로 만들어 `Github packages`에 저장되도록 하였습니다.

<br/>

### CD

`Github packages`에 저장된 이미지를 `appleboy/ssh-action@master` 를 이용하여 우리의 클라우드 서버에 접근하여 이미지를 컨테이너화 하여 서비스를 실행할 수 있게 하였습니다.

<br/>

### Action secrets을 통한 환경변수 관리

`Action secrets`에 우리의 환경변수들을 넣어서 이미지가 빌드될때 환경변수로 주입하여 .giitignore에 포함되어 GIthub에 로드 되지 않던 환경변수들을 관리하였습니다.

✏️ [Github-action을 통한 CI/CD](https://velog.io/@gkqkehs7/Github-action%EC%9D%84-%ED%86%B5%ED%95%9C-CICD)

<br/>

## 🔍 Filebeat

### Filebeat를 이용한 로그 서빙

Winston.js로 기록한 우리 서버의 로그들을 기록한 폴더를 volume에 연결하고  `Filebeat` 또한 컨테이너로 실행한 다음 volume으로 연결하여 로그가 쌓일때마다 Filebeat가 Elasticsearch로 우리들의 로그를 보내게 만들었습니다.

✏️ [Filebeat를 이용해 서버 로그 서빙하기](https://velog.io/@gkqkehs7/Docker-volume%EC%99%80-Filebeat%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%98%EC%97%AC-%EC%84%9C%EB%B2%84-%EB%A1%9C%EA%B7%B8-%EC%88%98%EC%A7%91)

<br/>

## 🔍 Nginx

### WAS의 부담 줄이기

`nginx` 를 도입하여 정적인 컨테츠에 대해선 `nginx` 가 처리해 주기 때문에 Node.js로 구동되고 있는 WAS에 대해 부담을 줄였습니다.

<br/>

### Reverse proxy

`nginx` 를 이용해 http로 80번 port에 들어온 요청들에 대해서 대리로 받은 다음, 443번 port로 redirect시켜서 보내주고. `reverse-proxy` 를 이용해 4000번에서 작동하고 있는 node.js서버로 요청이 가게 하였습니다. 이렇게 `리버스 프록시는(reverse-proxy)`를 통해 서버를 감추고, SSL/TLS 암호화를 사용하여 데이터를 안전하게 전송할 수 있게 하였습니다.

✏️ [Http와 Https 그리고 SSL은 각각 무엇일까?](https://velog.io/@gkqkehs7/HTTP%EC%99%80-HTTPS-%EA%B7%B8%EB%A6%AC%EA%B3%A0-SSL) | ✏️ [Nginx란 무엇이고 왜 사용할까?](https://velog.io/@gkqkehs7/nginx-web-server-was) | ✏️ [Nginx 설치 및 Https 적용하기](https://velog.io/@gkqkehs7/nginx-%EC%84%A4%EC%B9%98-%EB%B0%8F-https-%EC%A0%81%EC%9A%A9)

<br/>

# ⚒️ 문제해결 / 개선사항

### 도커 네트워크를 이용하여 외부 접근은 차단하고 컨테이너들끼리 소통하게 하기

6379 port 에서 작동하고 있는 redis 컨테이너가 외부의 접근을 받아, 수시로 데이터가 모두 날라가 버리는 현상이 발생하였습니다. 

따라서 6379번의 방화벽을 차단하여 외부 접근은 막고 도커 네크워크를 이용해 서버와 레디스가 소통할 수 있도록 만들어 주었습니다.

✏️ [도커 네트워크를 통한 서버와 redis연결](https://velog.io/@gkqkehs7/Redis%EC%9D%98-%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80-%EC%82%AD%EC%A0%9C%EB%90%98%EB%8D%98-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0)

<br/>

## static 변수 선언 때문에 환경변수가 로드되지 않던 문제 해결

dotenv.config()를 프로젝트 최상단에 선언하였지만, 싱글턴으로 작성한 Redis를 연결하는 함수가 

dotenv.config() 보다 먼저 실행되어, Redis에 연결이 되지 않는 현상이 발생하였습니다. 

JavaScript에서 static 키워드를 사용하여 선언된 변수는 클래스가 로드될 때 기본적으로 초기화 된다는 사

실을 알았고, 해당 변수를 인스턴스 변수로 수정하여 문제를 해결하였습니다.

✏️ [staic으로 선언한 변수는 언제 로드되는가?](https://velog.io/@gkqkehs7/static%EB%A1%9C-%EC%84%A0%EC%96%B8%ED%95%9C-%EB%B3%80%EC%88%98%EB%8A%94-%EC%96%B8%EC%A0%9C-%EB%A1%9C%EB%93%9C%EB%90%98%EB%8A%94%EA%B0%80)

<br/>

## 4000ms 소요되던 API 1000ms로 단축

Discord.js로 2000ms 이상 소요되는 API에 대해 알림을 보내도록 하였는데, 알림이 온 문제의 API에 대해

생성/수정 보단 조회가 많이 일어나는 서비스임을 감안하여, 생성단에서 처리할 수 있는 작업은 Database 

table에 새 column을 추가하는 작업을 통해 생성 및 수정시에 처리하였고, Promise.all의 병렬 처리를 이용

하여 API 수행시간을 단축하였습니다.

 ✏️ [Promise.all과 DB column추가로 인한 API 소요시간 단축](https://velog.io/@gkqkehs7/API%EC%86%8C%EC%9A%94%EC%8B%9C%EA%B0%84-%EA%B0%9C%EC%84%A0)
