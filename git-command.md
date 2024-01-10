
[How to inject a commit between some two arbitrary commits in the past?](https://stackoverflow.com/questions/32315156/how-to-inject-a-commit-between-some-two-arbitrary-commits-in-the-past)


把当前修改的内容导出位patch保存
```
git add .
git diff HEAD > new-01.diff

git apply new-01.diff
```
