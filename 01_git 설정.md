# Git 제대로 배우기

# 참고: 유트브, 드림코딩 by 엘리, (깃, 깃허브 제대로 배우기)

## 사용 툴

- MAC iTerms2, 소스트리

# Github CheatSheet

- HOME: [https://training.github.com/](https://training.github.com/)
- 한국어: [https://training.github.com/downloads/ko/github-git-cheat-sheet/](https://training.github.com/downloads/ko/github-git-cheat-sheet/)
- 중국어: [https://training.github.com/downloads/zh_CN/github-git-cheat-sheet/](https://training.github.com/downloads/zh_CN/github-git-cheat-sheet/)
- [https://ndpsoftware.com/git-cheatsheet.html#loc=index](https://ndpsoftware.com/git-cheatsheet.html#loc=index);

# 기본 설정

## git config 리스트 확인

```bash
git config --list
```

## git config 설정

```bash
# 설정하는 방법
git config --global user.name 'isun-dev'
git config --global user.email '이메일'

# 설정내용 확인 방법
git config user.name
git config user.email
```

## git 에서 CRLF 개행 문자 차이로 인한 문제 해결하기
```bash
git config --global core.autocrlf input
```