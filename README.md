# git-basic

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
