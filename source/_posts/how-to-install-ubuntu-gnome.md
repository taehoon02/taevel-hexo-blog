---
title: Ubuntu GNOME 16.04 LTS 설치하기
date: 2018-07-09 02:58:51
---

## 필자의 노트북
삼성 노트북 5 NT500R5L-Y54M

## 설치
[https://b.chalk.pe/posts/setting-up-ubuntu-gnome-16-04/]

### 달리 해야할 점
필수 패키지 설정 명령어 입맛에 맞게 변경.

```bash
sudo apt update
sudo apt install -y steam oracle-java8-installer git fcitx fcitx-hangul nodejs yarn numix-icon-theme-circle mongodb-org
sudo apt upgrade && sudo apt autoremove
```

### APT로 설치하기 귀찮은 프로그램들
1. [Telegram Desktop]
3. [Visual Studio Code]
4. [Google Chrome]

### 추가로 해야할 점
[https://b.chalk.pe/posts/setting-up-oh-my-zsh/]



[https://b.chalk.pe/posts/setting-up-ubuntu-gnome-16-04/]: https://b.chalk.pe/posts/setting-up-ubuntu-gnome-16-04/
[여기]: http://cdimage.ubuntu.com/ubuntu-gnome/releases/16.04.1/release/
[Telegram Desktop]: https://desktop.telegram.org/
[Slack]: https://slack.com/downloads/linux
[Visual Studio Code]: https://code.visualstudio.com/download
[Google Chrome]: https://www.google.co.kr/chrome/index.html
[https://b.chalk.pe/posts/setting-up-oh-my-zsh/]: https://b.chalk.pe/posts/setting-up-oh-my-zsh/