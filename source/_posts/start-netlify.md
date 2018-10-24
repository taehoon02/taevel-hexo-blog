---
title: Netlify 시작하기
date: 2018-10-12 21:16:08
---

## Netlify를 사용한 이유
Netlify를 사용한 이유는 [해당 글](https://www.datanyze.com/market-share/paas/netlify-vs-heroku)을 참고하시기 바랍니다.

## Netlify 사이트 생성
회원가입을 합니다. 전 깃허브를 사용하였습니다.

접속후 `New site from git`를 선택하여 사이트를 생성합니다.

### 액세스 제한
민감한 저장소에 대한 액세스 권한을 부여하는 것에 대해 걱정이된다면 GitHub를 사용하여 응용 프로그램 액세스를 제한 할 수 있습니다.
자세한 내용은 [Netlify - GitHub Permissions](https://www.netlify.com/docs/github-permissions/)에서 확인할 수 있습니다.
원할 경우 체크합니다.

### 저장소 선택
사이트로 올릴 깃허브 저장소를 선택합니다.
저장소 안에는 `index.html`이 있는 것을 추천합니다.

### 기본 빌드 설정
기본 빌드를 설정합니다.
브랜치, 빌드 명령(없다면 적지 않아도 됩니다), 정적 디렉토리(Public directory)를 작성합니다.

정적 디렉토리의 경우 보통 `public/` 혹은 `dist/`로 설정됩니다.

마지막으로 `Deploy site` 버튼을 눌러 사이트를 배포합니다.
약간의 시간이 지난 후 배포가 완료되면 `Published` 메시지를 확인할 수 있습니다.

만약 실패의 경우 `Deploy log`를 확인합니다.

1단계가 완료되었습니다.

### 도메인 설정
`Site setting > Site information > Site name` 클릭하여 도메인을 설정할 수 있습니다.
사용자 정의 도메인이 없을 경우 용이합니다.

## 사용자 정의 도메인 설정
2단계인 `Set up a custom domain` 을 선택한 후 `Add custom domain`을 클릭하여 보유하고 있는 나의 도메인을 입력합니다.

### DNS 설정
DNS를 설정합니다. `Set up Netlify DNS`를 하면 사용자 정의 도메인에 대한 DNS  레코드가 포함될 DNS 영역을 만들어야 합니다. 그러면 사이트의 필수 DNS 레코드가 자동으로 생성됩니다.

### 네임서버 변경
도메인 제공 업체의 계정에 로그인하고 제공되는 호스트 이름으로 네임 서버를 변경합니다.
저는 [hosting.kr](https://www.hosting.kr/)를 사용합니다.

네임서버 변경 후 잠시(5~10분) 기다리면 완료됩니다.
이제 사용자 정의 도메인을 사용할 수 있습니다.

>저같은 경우 [DNSZi](https://dnszi.com)를 사용해서 네임서버를 관리하는지라 이쪽에서 설정해주면 됩니다. 이 경우 사용자마다 다르므로 자세히 설명하지 않겠습니다.

## 무료 TLS 인증서로 HTTPS 보안 및 암호화를 추가
마지막 단계인 3단계입니다. `Secure your site with HTTPS`를 선택합니다.
페이지 중간에 HTTPS 영역에서 `Verify DNS configuration`를 선택합니다.

DNS 변경 사항이 전파될 때까지 1시간 정도 소요됩니다.

### Let’s Encrypt 인증서 프로비저닝
1시간 정도 기다린 후 HTTPS를 사용할 준비가 되면 `Let’s Encrypt certificate` 버튼이 생성됩니다. 버튼을 누르면 [Let’s Encrypt](https://letsencrypt.org/)에서 TLS 인증서를 제공하고 CDN에 설치합니다.

역시 몇 분 기다리면 무료 인증서의 [프로비저닝](https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9C%EB%B9%84%EC%A0%80%EB%8B%9D)이 완료됩니다.

이제 HTTPS를 사용할 수 있습니다.

>저같은 경우 [DNSZi](https://dnszi.com)로 HTTPS 보안 접속을 사용할 수 있습니다. 이 경우 해당 단계를 진행하지 않아도 됩니다.

### 프로젝트 업데이트
프로젝트를 수정하여 Github에 푸쉬하면 Netlify에서 자동으로 빌드하여 배포합니다. 푸쉬 후 자동 배포까지 대략 1~5분이 소요됩니다.

## 참고
이 글은 [해당글](https://heropy.blog/2017/09/30/markdown/)을 참고하였습니다. 훨씬 더 자세하게 나와있으며, 이 글의 작성 목적은 개인 기록임을 밝힙니다.