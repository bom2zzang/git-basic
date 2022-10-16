# git-basic

[매우쉽게 알려주는 git & github](https://codingapple.com/course/git-and-github/)

## 명령어

- add

  ```
  // 여러 파일 스테이징
  git add 파일1 파일2

  // 모든 파일 스테이징
  git add .
  ```

- 상태확인

  ```
  git status
  ```

- add(스테이징) 취소

  ```
  git restore --staged 파일1
  git restore --staged .
  ```

- 커밋

  ```
  git commit -m '메세지'
  ```

- 로그 확인

  ```
  git log [--all] [--online] [--graph]
  ```

- 차이점 비교

  ```
  git diff

  // 과거 특정 커밋과의 차이점 비교
  git diff 커밋id

  // 과거 특정 커밋2개의 차이점 비교
  git diff 커밋id1 커밋id2

  // 보기 좋게 비교 - 하지만 불편함
  git difftool
  ```

- branch

  ```
  // 브랜치 생성
  git branch 브랜치명

  // 브랜치로 이동
  git switch 브랜치명 // (요즘)
  git checkout 브랜치명 // (과거)

  // 브랜치 합치기
  git merge 브랜치명

  // 브랜치 삭제
  git branch -d 브랜치명 // 병합이 완료된 브랜치 삭제
  git branch -D 브랜치명 // 병합하지 않은 브랜치 삭제
  ```

- merge conflict

  ```
  // 1. 충돌 코드 제거
  // 2. 스테이징
  git add 파일명
  // 3. 커밋
  git commit -m '메세지'
  ```

- rebase and merge

  - 브랜치의 시작점을 다른 커밋으로 옮겨주는 행위
  - 브랜치끼리 차이가 많으면 충돌이 발생할 수 있음

  ```
  // 1. 새로운 브랜치로 이동하여 rebase
  git switch 새브랜치
  git rebase main

  // 2. 브랜치가 main 끝으로 이동한 상태에서 merge
  git switch main
  git merge 새브랜치
  ```

- squash and merge
  - 새 브랜치에 있던 코드 변경사항들이 main브랜치로 텔레포트
  ```
  git switch main
  git merge --squash 브랜치명
  git commit -m '메세지'
  ```
- 파일 하나 되돌리기

  ```
  git restore 파일명 // 최근 commit 상태로 되돌리기
  git restore --source 커밋아이디 파일명 // 특정 커밋아이디 시점으로 되돌리기
  git restore --staged 파일명 // 특정 파일 staging 취소
  ```

- commit을 되돌리기

  ```
  git revert 커밋아이디
  ```

- 전부 되돌리기

  - untracked 파일들은 (git add 안해놓은 파일들은) 유지됨.
  - git clean 명령어 찾아서 쓰면 untracked 파일들도 다 지울 수 있음.
  - reset option : hard / soft / mixed(default)

  ```
  git reset --hard 커밋아이디
  ```

- `git pull` = `git fetch` + `git merge`

- 보관하기

  ```
  git stash
  git stash save "bbb 코드짰는데 망함" // 메모 가능
  git stash list // 목록 보기
  git stash pop // 최근에 보관한 코드 불러오기
  git stash drop 삭제할id // 특정 stash 삭제
  git stash clear // 모든 stash 삭제
  git stash -p // 일부 코드만 stash
  ```

## workflow 전략

- git flow

  - 브랜치 구성

  1. main 브랜치
  2. develop 브랜치 (개발용)
  3. feature 브랜치 (develop에 기능추가용)
  4. hotfix 브랜치 (main 브랜치 버그해결용)
  5. 가끔 release 브랜치 (develop 브랜치를 main 브랜치에 합치기 전에 최종 테스트용)
     ![img](https://codingapple.com/wp-content/uploads/2022/07/%EA%B7%B8%EB%A6%BC6.png)

- Trunk-based
  - ![img](https://codingapple.com/wp-content/uploads/2022/07/%EA%B7%B8%EB%A6%BC7.png)
