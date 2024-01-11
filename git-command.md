### git利用rebase提交中间加入commit

[How to inject a commit between some two arbitrary commits in the past?](https://stackoverflow.com/questions/32315156/how-to-inject-a-commit-between-some-two-arbitrary-commits-in-the-past)

```shell
要插入的commit的历史前一个commit的sha1,可以用前7位就行
git rebase -i <commit-sha1>
## 如果要插入在第一个commit后时，用root
## git rebase -i --root

弹出编辑器，列出上面commit之后的commit历史，原第二行换行移到第三行，第二行写break，保存关闭当前编辑文件生效

提交修改，add,commit
如果有冲突，解决冲突，这时提交的信息要写上面第三行的提交信息（要插入commit的后面commit的信息），不然修改后，插入的commit和其后一个commit的提交信息不一样

完成剩下rebase，完成commit插入
git rebase --continue
```

---

### 把当前修改的内容导出位patch保存，文件要处于git管理下，新文件需要add到stage状态

```
git add .
git diff HEAD > new-01.diff

应用，恢复导出的修改
git apply new-01.diff

更多参数
git diff --cached --binary HEAD
```
