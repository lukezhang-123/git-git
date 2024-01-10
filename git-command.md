### git利用rebase提交中间加入commit

[How to inject a commit between some two arbitrary commits in the past?](https://stackoverflow.com/questions/32315156/how-to-inject-a-commit-between-some-two-arbitrary-commits-in-the-past)

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
