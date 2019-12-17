# Git 기초

## 개념

### SCM 이란?

Source Code Manager의 약자

코드의 버전을 관리를 위해 존재



## 관련 프로그램

### Git

로컬저장소 관리

https://git-scm.com/download/win

#### 시작 설정

 Git에서 저장소를 만들때 가장 먼저 해야할 일은 바로 <.gitignore> 파일 설정이다. 필요없는 data나 공유하면 안되는 중요 파일을 예외 처리 하기 위한 설정이다. 

![](01_git기초.assets/ignore1.png)

![](01_git기초.assets/ignore2.PNG)

#### .gitignore 설정 참고

http://gitignore.io/ 에서 사용하는 엔진이나 언어를 기입하면 .gitignore 파일에 추가해야할 설정이 출력된다.



### GitHub

클라우드 저장소 관리

https://github.com/



### Sourcetree

Git 관리 GUI

https://www.sourcetreeapp.com/

#### 로컬저장소 설정

![](01_git기초.assets/SOURCETREE실행1.PNG)



#### Git/Github 연동

##### Sourcetree 연동 준비

![](01_git기초.assets/github1.PNG)



![](01_git기초.assets/github2.PNG)

![](01_git기초.assets/github3.PNG)



![](01_git기초.assets/github4.PNG)



##### Github 설정 및 url 주소 확인

![](01_git기초.assets/github12-0.PNG)



![](01_git기초.assets/github12-1.PNG)



![](01_git기초.assets/github12-2.PNG)

##### Sourcetree에서 Git, Github 연동

![](01_git기초.assets/github11.PNG)



![](01_git기초.assets/github12-3.PNG)

##### 참고 - commit이 안될 때

저장소로 사용할 폴더 우클릭

![](01_git기초.assets/sourcetree_error1.PNG)

아래의 명령어 사용

![](01_git기초.assets/sourcetree_error2.PNG)



#### PUSH / PULL을 이용한 동기화

##### PUSH

![](01_git기초.assets/clone3-push.PNG)

![](01_git기초.assets/clone3-1-push.PNG)

 Sourcetree에서 로컬에 저장된 내용을 온라인 저장소에 upload



##### PULL

![](01_git기초.assets/clone4-pull.PNG)

![](01_git기초.assets/clone4-1-pull.PNG)

 Sourcetree에서 온라인 저장소에 저장된 내용 로컬로 download



#### CLONE

![](01_git기초.assets/clone1-github-1576543497255.PNG)

Github의 온라인 저장소url 위치를 확인

![](01_git기초.assets/clone2-sourecetree-1576543690110.PNG)

Sourcetree에서 Github에서 받아온 url를 받아와서 저장



#### Team Project

![](01_git기초.assets/Github_collabo.PNG)

Github에서 해당 프로젝트에 Setting -> Collaboration 에서 Github ID를 추가. (추가시  e-mail로 초대 메세지가 전달 됨)

초대 받은 사용자들은 CLONE 과정을 통해 data 공유



#### BRANCH

##### 생성

![](01_git기초.assets/make_branch.PNG)

이어올 branch에 체크아웃 상태에서 브랜치 생성

###### 참고 - 체크아웃

![](01_git기초.assets/checkout.PNG)

Sourcetree에서 위와 같이 포커싱 되어 있는 상태

##### 삭제

![](01_git기초.assets/delete_branch.png)

삭제할 branch가 아닌 다른 branch에 체크아웃을 하고 삭제



#### MERGE - Local

![](01_git기초.assets/MergeToMaster1.png)

기준이 될 브랜치에 체크아웃 상태에서 병합할 브랜치 우클릭 -> 현재 브랜치로 병합

![](01_git기초.assets/MergeToMaster2.png)

병합 후 위와 같이 그래프가 이어진 것을 확인

##### 참고 - master branch

master branch는 주로 배포 가능한 버전을 관리. 개발은 다른 branch에서 개발해서 병합하는게 안전



#### Recovery

##### 초기화

![](01_git기초.assets/recover_branch.png)

돌아갈 commit을 우클릭 -> 초기화

![](01_git기초.assets/recovery-hard.png)

HARD - 시점으로 파일들이 완전히 돌아감

MIXED - commit 목록에 안 올리고 commit하기 전 단계로 돌아감

SOFT - commit 목록에 올리고 commit하기 전 단계로 돌아감

 **Local 에서의 복구는 비교적 간단한 편이지만 온라인으로 업로드 후에 복구는 history가 꼬일 수 있음(왠만하면 Online push 후에 복구를 통한 작업을 하지 말자)**

###### 참고 - commit 전에 리셋하는 방법

![](01_git기초.assets/NoneCommitRecovery.png)

![](01_git기초.assets/NoneCommitRecovery2.png)

history에서 바로 전에 commit한 곳에 checkout(청소)



#### MERGE - Online

![](01_git기초.assets/branch_online2.png)

Sourcetree에서 commit한 branch만 push

![](01_git기초.assets/branch_online3_github.png)

Github에서 push 정보 확인

![](01_git기초.assets/branch_online4_github.png)

세부 내용 작성

![](01_git기초.assets/branch_online5_github-1576570848308.png)

Merge pull request ?? - 뭐하는건지 알아보자

![](01_git기초.assets/branch_online6-1_github.png)

이 상태에서 Sourcetree의 pull 실행시 위오 같이 아직 merge가 안되 있는걸 확인 가능

![](01_git기초.assets/branch_online6_github.png)

confirm을 하면

![](01_git기초.assets/branch_online6-2_github.png)

위와 같이 merge 상태가 확인 되고

![](01_git기초.assets/branch_online6-3_github.png)

Sourcetree에서 pull 하면 위와 같이 표기

![](01_git기초.assets/branch_online7_github-1576571990474.png)

최종적으로 위와 같이 출력된다면 online 상에서 merge가 완료



##### 참고 - 

 visual code에서는 merge에서 충돌나는 경우. 충돌난 파일이 보라색으로 보임

 branch 잔가지도 바로 master에 통합 가능

 origin 은 그냥 default로 설정된 이름. 바꿔도 상관없음



### Typora

README.md 파일(markdown 파일) Editor

https://www.typora.io/#windows

#### 환경설정

![](01_git기초.assets/typora.PNG)

이미지 저장을 위한 환경설정



