Git/Github
======================
## 1. Git
>git add
* 파일 추가
>git add .
* 모든 파일 추가
>git status
* 변경사항 확인
>git log
* 로그 확인
>git diff
* 파일이 어떤 내용으로 추가 혹은 변경되었는지 확인

git commit
-------
|작업|VI 명령어|상세|
|------|---|---|
|입력 시작|i|텍스트 입력 모드로 전환|
|입력 종료|ESC|명령어 입력 모드로 전환|
|저장 없이 종료|:q||
|저장 없이 강제 종료|:q!|입력한 것 있을 때 사용|
|저장하고 종료|:wq|압력한 것 있을 때 사용|
|위로 스크롤|k|git log등에서 내역이 길 때 사용|
|아래로 스크롤|j|git log등에서 내역이 길 때 사용|

>init commit           
* 입력 후 저장하고 종료
>git commit -m "메시지"
* 커밋 메시지 작성
>git commit -am "메시지"
* 모든 변경된 파일 스테이징과 커밋 메시지 작성

>새 파일은 갱신이 안되므로 git add를 사용하자!

## 2. Git 과거로 돌리기
* reset  : 원하는 시점으로 돌아간 뒤 이후 내역 삭제
* revert : 되돌리기를 원하는 시점의 커밋을 거꾸로 실행
* .git 폴더를 백업 하는 것도 방법

## 3. 브랜치 생성
* 프로젝트를 하나 이상의 모습으로 관리해야 할 때 사용
* 여러 작업들이 각각 독립되어 진행될 때

### 3.1 브랜치 생성/이동/삭제
>git branch '브랜치명'    
* 브랜치 생성
>git branch              
* 브랜치 목록 확인
>git switch '브랜치명'    
* 브랜치로 이동
>git switch -c '브랜치명' 
* 브랜치로 생성과 이동
>git branch -d '브랜치명' 
* 브랜치 삭제
>git branch -D '브랜치명' 
* 브랜치 강제 삭제
>git log --'명령어' 
```
--all      : 모든 브랜치의 커밋 로그 포함
--decorate : 브랜치와 같은 참조 정보를 로그에 표시
--oneline  : 각 커밋을 한 줄로 요약하여 출력
--graph    : 커밋 기록을 시각적으로 나타냄
```

### 3.2 브랜치 합치기
#### 3.2.1 merge
* feature 브랜치에서 main 브랜치에 통합 할 때 사용
* 기존 커밋은 그대로 유지됨
* 브랜치의 히스토리 보존으로 추적하기 편함
* 히스토리 보존으로 복잡해 질 수 있음
```
git checkout main
git merge feature-branch
```

#### 3.2.2 Rebase
* 한 브랜치의 변경 사항을 다른 브랜치의 최신 커밋 위로 옮김
* feature에서 작업하다 main에서 새로운 커밋 발생시 재정렬 할때 사용
* 기존의 커밋 히스토리 변경하여 새로운 커밋 생성해서 히스토리가 깨끗한 편
* 브랜치를 업데이트 하는 동안 발생 할 수 있는 충돌 해결에 유용
* 커밋 히스토리가 변경되어 팀원들이 같은 브랜치 사용시 조심 해야함
```
git checkout feature-branch
git rebase main
```
## 요약
* Merge는 브랜치의 히스토리를 보존하면서 두 브랜치를 통합함. 커밋 히스토리가 복잡해질 수 있지만, 변경 이력을 명확히 추적할 수 있음
* Rebase는 브랜치를 최신 상태로 업데이트하면서 깔끔한 히스토리를 유지함. 그러나 브랜치의 히스토리가 변경되므로 주의 요구

## 4. Github
### 4.1 push, pull
>git push
* 로컬에서 원격 저장소로 업로드
>git pull
* 원격 저장소에서 로컬로 다운로드 후 통합
```
git pull -no-rebase : merge 방식
git pull --rebase   : rebase 방식
```
