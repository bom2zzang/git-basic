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
  ```

  67 충돌 만들기
