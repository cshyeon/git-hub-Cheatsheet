# git-hub-Cheatsheet
Git and Github cheatsheet

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

### `clone`
사용자 디렉토리 이름 설정
```bash
git clone [url] [directory name]
#git clone https://github.com/cshyeon/git-hub-Cheatsheet.git myfolder
```