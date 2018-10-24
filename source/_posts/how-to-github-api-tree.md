---
title: Gihub API Tree 사용하기
date: 2018-04-11 12:15:15
---

## 준비할 것
1. [Postman] 설치
2. [github api token]받기 (github settings -> developer settings -> personal access tokens 에서 토큰 발급. (이 토큰은 잘 알아두도록 하자.))

## Tree 구하기
[GitHub API Tree]를 참고하여 작성한다.

1. Postman 실행
2. Authorization TYPE을 Basic Auth 로 하고 오른쪽에서 GitHub Username과 Password을 입력 후 왼쪽 Preview Request 버튼을 클릭한다.
3. 위쪽을 GET으로 하고 url에 ```https://api.github.com/repos/<username>/<repo_name>/git/refs/heads/master``` 을 입력 후 Send를 클릭한다.
4. 아래쪽 JSON 확장자명으로 된 파일 내용이 출력되는데 이 중에 object 안의 sha 부분을 복사한다. (숫자 영어로 되어있는 엄청나게 긴 부분)

아래 1번과 2번의 차이는 전자는 폴더 상위 내용을 포함하지 않고 후자는 폴더 상위 내용을 포함한다.<br>
자신이 필요한 Tree를 구하도록 하자.<br>
?recursive=1이 폴더 상위 내용을 포함한다고 선언하는 것이다.

1. 위쪽을 GET으로 하고 url에 ```https://api.github.com/repos/<username>/<repo_name>/git/trees/<sha>``` 을 입력 후 Send를 클릭한다. -> 깃허브 tree가 완성되었다.
2. 위쪽을 GET으로 하고 url에 ```https://api.github.com/repos/<username>/<repo_name>/git/trees/<sha>?recursive=1``` 을 입력 후 Send를 클릭한다. -> 깃허브 tree가 완성되었다.

## 마치면서
더 다양한 Gihub API는 [여기]를 참고하세요.


[Postman]: https://www.getpostman.com/
[github api token]: https://github.com
[Github API Tree]: https://developer.github.com/v3/git/trees/
[여기]: https://developer.github.com/
