---
title: npm scripts와 gulp 비교
date: 2018-04-24 18:18:58
---

## npm scripts

### 장점

* `npm scripts`는 낮은 수준이며 사용하고자 하는 실제 라이브러리를 활용합니다.(예: "lint": "eslint ./")
* `package.json`은 사용 가능한 스크립트를 확인하는 중앙에 위치합니다.(`npm run`도 모든 스크립트를 나열)
* 작업이 너무 복잡해지면 다른 파일로 이동할 수 있습니다.(예: "complex-script": "babel-node tools/complex-script.js")
* `npm scripts`는 처음에 생각했던 것보다 더 강력합니다.(예: pre/post hooks, passing arguments, config variables, chaining, piping 등)
* 우리는 다음에 큰 것(Anvil, brocolli, Grunt, Gulp)이 나올 때 특정한 구조 추상화에 얽매이지 않을 수 있습니다.

### 단점

* 모든 사람이 `npm scripts`에 익숙한 것은 아닙니다.
* 일부 스크립트는 시간이 오래 걸리고 번거롭습니다.

### 편리한 모듈들

* `npm-run-all`: 여러개의 스크립트를 병렬 또는 순차적으로 실행하는 CLI도구입니다.
* `rimraf`: 노드에 대한 딥 삭제 모듈 (```rm -rf```처럼)
* `onchange`: 파일 세트를 보려면 glob패턴을 사용하고 추가, 변경 또는 삭제된 항목이 있을 때 명령을 실행할 수 있습니다.

## gulp

### 장점

* gulp 플러그인과 유틸리티가 많습니다.
* 공통적인 Gulp작업을 제공하기 위한 일부 도우미 라이브러리가 이미 있습니다.

### 단점

* Gulp 플러그인은 오래된 경우가 많으며, 기본 라이브러리의 새 기능을 지원하지 않습니다.
* 포장된 라이브러리가 아닌 Gulp 플러그인 작성자에게 종속되어 있습니다.
* Gulp 플러그인 문서는 일반적으로 매우 강력하지 않고 포괄적이지 않습니다.
* Gulp 플러그인을 디버깅하는 것은 당신에게 좌절을 줄 수 있습니다. 플러그인이나 기존 라이브러리에 문제가 있을 수 있거든요.
* 만약 Gulp에 대한 플러그인이 없는 경우 당신이 직접 작성해야 합니다.
* Gulp 내에서 발생하는 오류는 대부분 잘 처리되지 않습니다.

## 고려할 생각

* 오직 `npm scripts`로만 전환하는가, Gulp를 계속 사용하는가, 아니면 이 둘을 혼합하여 사용하는가?
* 만일 우리가 `npm scripts`와 Gulp의 합성된 무엇인가를 가지고 있다면 우리는 어떻게 무엇을 해야할지 결정해야되는가? 어느 정도의 복잡성 임계값이 충족될 때까지 `npm scripts`라는 가정으로 시작해야 하는가? 우리가 새로운 프로젝트에 `npm scripts`만을 사용하고 복잡성이 증가할 때 `tools/script-file.js`로 바꿀 수 있는가? (예는 [react-slingshot](https://github.com/coryhouse/react-slingshot) 참조)
* 이미 시행된 위험이 있는 프로젝트는 어떻게 조정하고 있는가? 계속해서 업데이트하고 있는가, 계속 업데이트하고 있는 것으로 확인될 경우에는 `npm scripts`로 전환하는 것을 고려할 수 있는가?


### 마치면서
이 문서는 [여기](https://gist.github.com/elijahmanor/179e47828bf760c218bb3820d929836d)의 내용을 번역한 것입니다. 오역 지적 받습니다.
