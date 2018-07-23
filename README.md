# git-hub-Cheatsheet
Git and Github cheatsheet

# git & github 동기화
```bash
# 1. 현재 로컬의 수정사항 저장(현재 branch를 깨끗한 상태인 Head로 만듬)
git stash
# 2. 로컬 branch에 github의 remote 브랜치 최신상태를 적용
git pull
# 3-1. 로컬의 수정사항을 다시 반영 (방법1 stash에서 다시 반영된 내용 삭제)
git stash pop 
# 3-2. 로컬의 수정사항을 다시 반영 (방법2 stash에서 반영된 내용 보존)
git stash apply 
```

# github
#### commit 취소 반영
```bash
# reset local storage
git reset [--hard | --soft] [HEAD]
# Apply the reset situation to github.
git push origin master -f
```

#### Remote branch 삭제
```bash
git push origin --delete [REMOTE_BRANCH_NAME]
```


# git

### `Head` 
Head 확인

```bash
# Detail log
git log

# Reflog
git reflog
```


### `commit`
취소
```bash
git reset [--hard | --soft] [HEAD]
```

중간 commit 삭제 / commit 합치기
```bash
# 목적 : 불필요한 commit 메세지 / 수정 로그 삭제
# N은 하나로 합칠 커밋의 헤드 갯수
git rebase HEAD~[N] -i

# 최신순(맨 아래 로그)부터 하나로 합칠 커밋까지 squash로 변경
# HEAD 커밋을 이전 커밋 3개(HEAD 포함 4개)와 합칠경우 최신순 HEAD부터 3개의 커밋 로그에 대해 squash로 설정, 4번째 커밋은 합치기위해 그대로 pick 상태 유지, 저장 및 종료 (in vim - :wq)

# git rebase HEAD~4 -i
# ==================================
# pick version1
# squash version2
# squash version3
# squash current HEAD(version 4)
# ==================================

# 새롭게 뜨는 에디터창에 새로운 커밋 메세지 작성 후 저장 및 종료

# 결과로 current Head ,version 3, version2가 하나의 커밋으로 합쳐지면서 version 2, version 3에 추가되었던 내용이 current Head에서는 삭제된 경우 합친 커밋에 수정된 기록이 남지않음

```


commit 메세지 수정
```bash
# N은 확인할 이전 헤드 갯수
git rebase HEAD~[N] -i
# 이후 나오는 에디터 창에서 수정할 commit의 맨 앞의 tag를 reword로 변경후 저장후 나가기
# 새로운 에디터 창이 뜨면 커밋 메세지 수정!
```

### `clone`
사용자 디렉토리 이름을 지정할경우
```bash
git clone [url] [directory name]
#git clone https://github.com/cshyeon/git-hub-Cheatsheet.git myfolder
```

### dev branch create!!!
master branch modify


### dev modifiy1