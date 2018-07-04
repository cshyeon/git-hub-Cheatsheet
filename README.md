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

commit 메세지 수정
```bash
# N은 확인할 이전 헤드 갯수
git rebase HEAD~[N] -i
# 이후 나오는 에디터 창에서 수정할 commit의 맨 앞의 tag를 reword로 변경후 저장후 나가기
# 새로운 에디터 창이 뜨면 커밋 메세지 수정!
```

### `clone`
사용자 디렉토리 이름 설정
```bash
git clone [url] [directory name]
#git clone https://github.com/cshyeon/git-hub-Cheatsheet.git myfolder
```
