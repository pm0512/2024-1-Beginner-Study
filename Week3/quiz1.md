## <p style="text-align:center;">개발 입문 스터디 Quiz 1</p>

#### Example
GDSC는 무엇의 약자인지 적으시오.

- 답: Google Developer Student Clubs

### Q1
Git에서 파일의 상태는 크게 untracked와 tracked로 나눌 수 있다.  
그렇다면 tracked에는 어떤 상태가 있는지 모두 적으시오.

- 답: unmodified, modified, staged

### Q2
Git에는 세 가지 영역이 있다.  
세 가지 영역을 모두 나열하시오.

- 답: working directory, staging area, local repository

### Q3
현재 우리는 ```main```브랜치에 있다.  
```develop```이라는 브랜치를 새로 만들고 이동까지 한번에 할 수 있는 명령어를 적으시오.

- 답: git checkout -b ~~"<브랜치 이름>"~~ **develop**

### Q4
Working Directory에 있는 파일들을 모두 Staging Area에 추가할 수 있는 명령어를 적으시오.

- 답: git add .

### Q5
```
1. Create a merge commit
2. Squash and merge
3. Rebase and merge
```
위의 세 가지가 어떤 차이가 있는지 간단히 적으시오.

- 답: ~~merge commit은 두 브랜치를 공통 부모로 하는 새로운 커밋을 생성하고, squash and merge는 main 브랜치에 하나의 커밋으로 병합되고, rebase and merge는 커밋의 베이스를 재설정한다는 점에서 차이가 있다.~~ **merge commit은 새로운 병합 커밋을 만들어 병합하고, Squash and merge는 모든 변경 사항을 하나의 커밋으로 압축하여 병합한다. 마지막으로 Rebase and merge는 대상 브랜치의 변경 사항을 현재 브랜치의 최신 커밋 위에 재배치하여 병합한다.**

### Q6
```git log --oneline```으로 commit의 기록을 확인해보니  
첫 줄에 ```a1s2d3f (HEAD -> develop) docs: readme 추가```라는 log가 찍혔다.
알 수 있는 사실을 모두 적으시오.

- 답: develop에서 현재 작업 중이며, readme를 추가함.

### Q7
```git log --oneline```으로 commit의 기록을 확인해보니 아래와 같은 log를 확인 할 수 있었다.  
```
a1s2d3f (HEAD -> develop) fifth commit
s2d3f4g fourth commit
345hj26 third commit
7g8dg7f second commit
5g568vk first commit
```
이때, fourth commit까지 제거하고 fourth commit과 fifth commit의 변경 사항은
Staging Area에 남아 있길 바란다면 reset을 어떤 옵션과 함께 사용하면 되는지 적으시오.

- 답: git reset --soft 345hj26

### Q8
```git log --oneline```으로 commit의 기록을 확인해보니 아래와 같은 log를 확인 할 수 있었다.
```
a1s2d3f (HEAD -> develop) fifth commit
s2d3f4g fourth commit
345hj26 third commit
7g8dg7f second commit
5g568vk first commit
```
reset은 너무 위험하니 revert를 사용하려고 하여 ```fifth commit```을 되돌리고 싶다면 
어떤 명령어를 사용하면 되는지 적으시오. 

- 답: ~~git revert --no-edit a1s2d3f~~ **git revert a1s2d3f**

### Q9
여러 사람이 협업하는 프로젝트에서 커밋을 되돌려야 한다.  
reset과 revert 중에 어떤 것을 선택할 것인지를 그 이유와 함께 적으시오.

- 답: revert를 사용할 것이다. reset은 commit을 사용하기 때문에 다른 브랜치에도 영향을 줄 수 있지만, revert는 생성하여 되돌리기 때문에 그럴 위험이 없다.
- **reset은 커밋 히스토리를 변경하므로 revert를 사용하는 것이 안전하다.**
