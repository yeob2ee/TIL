# 06/07 Git & GitHub 특강

## GIT

### CLI

- Command Line interface
- 명령줄
- 명령을 해야 실행되고, 하지 않으면 어떠한 것도 하지 않는다.

### CLI - command

- ls : list
- touch : 빈 파일 생성
- rm : remove
- mkdir : make diretory(폴더를 만든다.)
- cd (blank): change diretory blank를 더블클릭과 같음
- .. : 상위폴더
- git : git과 관련된 명령어들을 나열.
- pwd : present working diretory


> interface : 스마트폰을 touch interface를 가지고 있다고 한다. --> 조작을 한다.

### GUI
- Graphic User Interface
- 그래픽 - 유저간의 요소

### 버전관리 시스템
- git은 분산 버전 관리 시스템 (DVCS)
- 버전관리? : 소프트웨어의 상태 --> sw를 작동시키는 소스코드의 상태.
- 크롬도 크로미움이라는 오픈소스 기반으로 되어있다. 최신버전 1.58GB이다. 백만개의 버전이 있는데, 모든 용량은 고작 25GB임. --> 모두 git 덕분이다.
- google docs : 이전 버전을 저장하여 조회하거나 복원시킬 수도 있다.
- git이 가장 많이 사용되고 있고, 리누스 토르발스가 개발하였으며 리눅스를 만든 사람이기도 한다.

- 컴퓨터 파일의 변경사항을 추적하고 여러명의 사용자들 간에 파일들의 작업을 조율
- 분산 버전 관리 시스템 : 로컬에서도 버전을 기록하고 관리, 원격 저장소를 활용하여 협업, 한쪽에 불이 나도 괜찮다.

### 저장소를 만들어 보자.
1. 작업을 하고
2. 변경된 작업을 모아서 add
3. 버전으로 남긴다 commit

### git 명령어
- git init : 초기화
- git status : 상태확인
- git add (파일명, 모든 파일이면 .)
- git commit -m '~~~'
- git log
- git status
- 다른분의 정리
    - 명령어 정리
    - git init = git초기화 (git 저장소 만듬)
    - git add . = 모든 파일을 staging Area에 모음.
        - --> 원하는 부분만 commit하고 싶어서.
    - git commit -m 'a' = a라는 버전을 남김
    - git status  = git 상태 확인 
        - working, staging area 상태
    - git git log = 버전이 기록된것을 확인
        - commit 된 것을 확인

## 조퇴한 이후 내용
- git push origin main 하면 깃허브 아이디, 닉네임 적어주라는 메시지 발생하고
본인 깃헙 아이디 닉네임 입력해주고나서 다시 git push origin main 입력하면 자기 깃허브에 커밋한 내용이 저장된다.

# 06/08

- git remote add origin 'repo 주소'
origin 이름으로 주소를 깃 원격저장소(remote) 추가(add)

- git remote rm origin 
origin으로 설정되어있는 저장소를 삭제(rm)한다.

- git push origin main
깃 원격저장소로 보내(push) origin/main 으로

- git remove -v 
원격저장 목록 조회

- git config --global core.editor "code --wait"
--> 커밋할떄 메세지를 길게 적을 수 있도록

- git log -1 : -1 최근 한줄만 보기
- git log -1--oneline : 최근한줄 한줄로 보기

- 이상하게 ~~ 이런거 뜨는 거 빔?님? 그거임
- :q! 로 탈출가능
- git pull origin main : pull

![이미지](./git_img01.PNG)

---

- 프로젝트와 관련이 없어서 파일을 따로 관리하고 싶어요! --> .gitignore 파일을 만들어서 이름을 적어놓으면 안됨 (파일도 가능) --> *.csv하면 csv 확장자는 전부 제외할 수 있다.
### 숨기는 이유
- 개발환경에 관련된 것들 : window, Mac(.DS_store)
- 개발언어와 관련된 것들 : 더 빨리 하기 위해 자체적으로 만들어놓은 것들
- IDE : 텍스트 에디터
- 개인 프로젝트에는 필요하지만, 공유되서는 안되는 경우


## Branch

- 독립적인 작업을 만들고 관리한다.
- master branch : 소비자가 실제로 사용하고, 라이브 서버에 적용되고 있는 버전, 제품으로 출시될 수 있는 branch
- 기능별로 팀이 다르고 개발을 따로 하고 있는 branch, 다 끝내고 개발팀 전체가 하나의 가지에 합치는 merge
- pull함수는 fetch와 pull을 가진 함수이다.

### branch 명령어
- git branch  {branch name}
- git checkout {brach name}
- git switch {branch name}
- git checkout -b {branch name}
- git branch -d {branch name}
- git log --oneline --graph

### Git Flow
- merge라는 행위를 github에서 하는것
- 리뷰를 하고 검토할 수 있을 것이다. 충돌난 부분, 변화된 부분만 따로 볼 수가 있다.

## 협업
- git clone {같이 작업할 user's url} : 단순히 Repo 복사
- folk 후 git clone {folk한 user's url}
- folk를 해서 복사본을 내 Repo로 만들고 변경사항을 Repo주인에게 Pull Request를 보내서 수정을 요구할 수 있다.

### 강사님의 메모장
main 프로젝트의 주소에 들어가서 'Fork' 클릭하고 Create Fork 클릭
원격저장소에 clone해야함. (반드시 나의 저장소에 클론해주어야 한다.)
git clone https://github.com/(%EB%82%98%EC%9D%98 원격저장소 주소)/(fork한 name)
명령어는 바탕화면에서 git bash 또는 terminal을 열어서 입력해준다.
git 저장소가 아닌 곳에서 (main표기가 없는) 입력해주면 된다.
바탕화면에 fork 받은 폴더가 있는데 이것을 vs code로 열어서 코드 작성 진행.
작성이 끝나면 add, commit, git push origin main 진행
Github에 들어가서 Pull Request 만든다.








## 꿀팁

- [도움되는 링크목록](https://hg-edu.notion.site/Git-GitHub-66251d4fe0c24075ace6f51110b5c919)

- [GitHub_Docs](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

- [DeepL translator](https://www.deepl.com/translator)
- [gitignore 파일 생성기](https://www.toptal.com/developers/gitignore/)
- [MS사_신기술강의](https://www.youtube.com/watch?v=FaV0tIaWWEg)
- 오픈소스 컨트리뷰션
- https://octoverse.github.com/
- https://git-scm.com/book/ko/v2
- https://backlog.com/git-tutorial/kr/intro/intro1_1.html
