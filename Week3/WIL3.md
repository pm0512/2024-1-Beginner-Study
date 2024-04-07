- ### git log
  - commit 기록을 최신 순으로 확인
  - `--oneline` 옵션을 사용하면 각 커밋을 한 줄에 요약
- ### commit ld
  - commit의 식별을 위해 사용하는 40자 길이의 16진수
  - 중복 확률은 2의 80제곱 분의 1
  - *SHA-1 해시 함수*를 사용

##### *SHA 함수
###### Secure Hash Algorithm, 안전한 해시 알고리즘
###### **SHA-1 함수** : 임의의 길이의 입력데이터(최대 2의 64제곱)를 160비트의 출력데이터으로 바꿈
###### > 인터넷 보안 프로토콜과 공개키 인증서에도 적용되고 있는 매우 중요한 암호 알고리즘

- ### head
  - **현재 작업 중인 위치**
  - 현재 작업 중인 브랜치의 가장 최근 commit
  - 다음 commit의 base가 되는 commit
  - 새로운 commit이 생기면 HEAD도 변경

- ### git status
  세가지 상태에 따라 파일을 분류하여 확인

|Condition|Description|
|:--:|:--:|
|changes to be committed|현재 스테이징 된 새로운 파일과 수정된 파일을 알 수 있음|
|changes not staged for commit|현재 스테이지 되지 않은 수정된 파일을 알 수 있음|
|untracked files|현재 스테이징 되지 않은 새로운 파이 목록을 알 수 있음|

## commit 되돌리기
1. ### amend
   `commit --amend`
   
   - 마지막 commit의 내용에 변경이 있을 때 사용
   - 완전히 새로운 commit으로 대체 (commit id가 바뀜) 
   - vim으로 진입하여 commit 메시지를 수정하게 됨

|Code|Description|
|:--:|:--:|
|git commit --amend -m "커밋 메세지"|'m' option으로 vim 진입 없이 commit 메시지 수정|
|git commit --amend --no-edit|'--no-edit' option으로 commit 메시지 수정 없이 commit 수정|

🚨**다른 사람이 작업 기반으로 삼고 있는 coomit은 amend하면 안됨**

2. ### reset
   - commit을 제거하는 데 사용
   - `git reset '--option' "< commit id >"` 돌아갈 commit의 id를 사용
   - 3가지 option 존재
      
     `reset --soft`
       - 커밋만 취소
       - 변경 사항이 staging area로 돌아감

     `reset --mixed`
       - default
       - 커밋을 취소
       - 변경 사항이 working directory로 돌아감
    
     `reset --hard`
       - 커밋을 취소
       - 변경 사항을 모두 제거하고 이전 커밋으로 돌아감

3. ### revert
   - `git revert '--option' "< commit id >"`
   - commit을 제거하지 않고 되돌림
   - 되돌리기 위한 새로운 commit이 생성됨
   - 2가지 option 존재

     `resvert --no-edit`
     
     편집기 진입 없이 바로 revert 가능

     `revert --no-commit`

     직접 commit 하지 않고, revert 내용을 staging area에 올림

### 📌 reset vs revert
- reset은 commit을 삭제하므로 위험
- commit을 공유하는 다른 브랜치에도 영향을 줄 수 있음
- commit을 삭제하기보다 생성하여 되돌리는 revert가 안전