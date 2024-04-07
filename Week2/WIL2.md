## Fork
다른 사용자의 Repository를 자신의 계쩡으로 복사하여 독립적으로 수정하고 관리

## Star
관심 있는 Repository나 프로젝트에 star를 달아 "북마크"와 같이 관리

## Issue
Repository에서 작업 계획, 토론 및 추적을 위해 활용

## Branch
+ 기존 Branch에서 분기되어 생성되는 별도의 작업 공간
+ *fork와 달리* 같은 Repository에 생성됨

|Code|Description|
|:--:|:--:|
|git branch|현재 브랜치 확인|
|git branch -a|모든 브랜치 확인|
|git branch "<브랜치 이름>"|브랜치 생성|
|git branch -D "<브랜치 이름>"|브랜치 삭제|
|git checkout "<브랜치 이름>"|브랜치 이동|
|git checkout -b "<브랜치 이름>"|브랜치 생성 후 이동|

### Branch의 종류
#### 1. Main Branch
수명이 무한하다.
+ #### master branch
  *제품으로 출시될 수 있는 브랜치*로,
  사용자에게 배포 가능한 상태만을 관리한다. 배포(release) 이력을 관리하기 위해 사용한다.
+ #### develop branch
  *다음 출시 버전을 개발하는 브랜치*로, 기능 개발을 위한 브랜치들을 병합하기 위해 사용한다. 즉, 모든 기능이 추가되고 버그가 수정되어 배포 가능한 안정적인 상태라면 develop 브랜치를 master 브랜치에 merge(병합)한다.
#### 2. Suppoting Branch
팀 구성원 간에 평행 개발을 할 수 있고, 기능을 쉽게 추적할 수 있다. 또한 여러 가지 문제도 해결하기 쉬워진다. 하지만 결국 제거될 것이기 때문에 제한된 수명을 갖는다.
+ #### feature branch
  *기능을 개발하는 브랜치*로, 새로운 기능 개발 및 버그 수정이 필요할 때마다 develop 브랜치로부터 분기한다.
+ #### release branch
  *이번 출시 버전을 준비하는 브랜치*로, 배포를 위한 최종적인 버그 수정, 문서 추가 등 배포와 직접적으로 관련된 작업을 수행한다.
+ #### hotfix branch
  *출시 버전에서 발생한 버그를 수정하는 브랜치*로, 배포한 버전에 긴급하게 수정을 해야 할 필요가 있을 경우, master 브랜치에서 분기하는 브랜치이다. 필요한 부분만 수정한 후 다시 master 브랜치에 병합하여 이를 배포한다.

### Branch 네이밍 규칙
#### "type/<issue 번호>-<간략한 설명>"

## Pull Request
+ 분기된 Branch를 다시 병합하기 위한 절차
+ 새로운 변경을 제안하거나 병합 시 발생하는 충돌을 해결
+ Merge에 앞서 코드 리뷰

## Merge
1. #### Merge Commit
![Merge Commit](<merge commit.png>)
+ 두 브랜치를 공통 부모로 하는 새로운 commit 'E'를 만듦
+ A, B, C의 커밋이 그대로 main 브랜치로 병합

2. #### Squash and Merge
![Squash and Merge](<squash and merge.png>)
+ A, B, C의 커밋을 'squash'
+ 하나의 커밋으로 main 브랜치로 병합
  
3. #### Rebase and Merge
![Rebase and Merge](<rebase and merge.png>)
+ A, B, C 커밋의 base를 재설정
+ 모두 새로운 커밋으로 변경
+ **commit hash**가 변경됨
+ 무수한 충돌을 경험할 수 있으니 사용에 주의

#### *Commit Hash(Commit Id)란?
+ commit의 식별을 위해 사용하는 40자 길이의 16진수
+ 중복 확률은 2의 80제곱 분의 1
+ *SHA-1 해시 함수*를 사용
  
##### *SHA 함수
###### Secure Hash Algorithm, 안전한 해시 알고리즘
###### **SHA-1 함수** : 임의의 길이의 입력데이터(최대 2의 64제곱)를 160비트의 출력데이터으로 바꿈
###### > 인터넷 보안 프로토콜과 공개키 인증서에도 적용되고 있는 매우 중요한 암호 알고리즘

___
[GIT/GITHUB를 활용한 실습](https://github.com/pm0512/2024-1-Beginner-Study/pull/2)
