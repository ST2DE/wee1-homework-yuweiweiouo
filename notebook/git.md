# git 常用指令

團隊常常需要切換或合併 branch，底下是常用 git 指令

## git pull

拉最新的 `master` 程式碼到目前 branch。不管是在任何 branch 都是執行底下指令

```
$ git pull --rebase origin master
```

## git reset

發送 Pull Request 後，又需要修改目前 Branch 程式，請善用 git reset 來回到前一次 commit 紀錄

```
$ git reset --soft HEAD^
```

`HEAD^` 代表回到上一個 commit，如果要回到多個 commit 請用 `HEAD~4`，其中 `4` 請換成您要的數字

## git branch

用來看目前有哪些 branch 或者是強制刪除壞掉的 branch

```
$ git bracnch -D xxxx
```

`-D` 是強制刪除

## git checkout

用來切換 branch

### 切換到遠端 branch

要 review 別人的 pull request，請使用底下指令

```
# 讀取最新的 origin 程式碼
$ git fetch origin
$ git checkout -b test origin/test
```

這樣就可以切換到遠端 test branch 繼續操作

### 單純切換 local branch

```
$ git checkout master
```

## git rebase

在 PR 內合併多個 commit 內容，這是用在 Code Review 完成後，原作者新增多個 commit，需要將全部 commit 合成一個 

```
$ git rebase -i commit_id
```

底下是常用的狀況

```
f, fixup = like "squash", but discard this commit's log message
s, squash = use commit, but meld into previous commit
```

把要 squash 的 commit id 前面都改成 `f`，然後 `:wq` 存檔。遇到衝突解決後，可以下

```
$ git add xxxx
$ git rebase --continue
```

要跳出 git rebase 的話，請下

```
$ git rebase --abort
```