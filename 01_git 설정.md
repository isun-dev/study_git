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

# git 초기화

1. 폴더 생성
2. git init 명령어롤 통해 초기화

```bash
***@***-ui-MacBookPro git_study % git init
Initialized empty Git repository in /Users/******/Documents/git_study/.git/
```

2-1. 초기화 후 파일  목록 확인

```bash
drwxr-xr-x   3 ******  staff   96  2 20 12:57 .
drwx------@ 24 ******  staff  768  2 20 12:57 ..
drwxr-xr-x   9 ******  staff  288  2 20 12:57 .git
```

2-2. .git 폴더 확인 방법

```bash
******@******-ui-MacBookPro git_study % open .git
```

![img](https://user-images.githubusercontent.com/43905552/154840851-9a589bc2-686f-4223-b24a-9f4443887ade.png)

# git 삭제

```bash
rm -rf .git
```

# 변경점을 저장하기 - 수정사항 검토 및  commit 생성

## git status

- commit 할 수 있는 새로운 파일 및 수정된 파일의 목록을 보여준다.

```bash
******@******-ui-MacBookPro git_study % git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

## git 도움말

```bash
git config --h
```

# Git Workflow

### local 구성 ⇒ 내 컴퓨터

- working directory: 작업내용
    - untracked와 tracked로 나뉘어져 있다.
    - git이 이미 track을 하고 있다면 tracked에 분류되고, 아직 tracking이 되지 않은 것들은 untracked로 분류된다.
    - tracked 에는 unmodified와 modified가 있는데, 전 파일과 비교했을 때 변동 사항이 있으면,
- staging area: 작업 후 버전 히스토리에 올릴 준비가 되어 있는 내용
- .git directory: 버전 히스토리를 가지고 있는 부분

### remote ⇒  Github

- 로컬 commit 내용을 Github와 같은 저장소에 push하여 저장.
- Github에서 pull해서 서버에서 로컬로 가져오기.

# commit 파일 정보

- 각각의 commit에는 스냅샷된 정보를 기반으로 고유한 hash 코드가 부과가 된다. 이를 통해 버전 정보를 확인할 수 있다. 또한 commit에는 메시지, 저자, 시간 등이 함께 저장되어 있다.

## 새로운 파일 생성 후, git status

- 현재 a.txt 파일은 untracked인 상태이다.

```bash
-rw-r--r--@  1 ******  staff    13  2 20 19:16 a.txt
******@******-ui-MacBookPro git_study % git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	a.txt

nothing added to commit but untracked files present (use "git add" to track)
```

- a.txt를 tracked 상태로 되게 할려면 git add를 하면 된다.

```bash
git add a.txt
```

- git add를 한 후, git status 확인 시

```bash
**@**-ui-MacBookPro git_study % git add a.txt
**@**-ui-MacBookPro git_study % git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   a.txt
```

- 파일 수정 후 git status

```bash
**@**-ui-MacBookPro git_study % echo nicole >> a.txt
**@**-ui-MacBookPro git_study % git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   a.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   a.txt
```

# git ignore

```bash
echo *.txt > .gitignore
```