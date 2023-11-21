# git-git
记录Git的特殊用法，知道你会简单用git，等你着急想用git功能而不会的时候就急了

---

![Alt text](image.png)

---

### 检查一个文件被哪个gitignore忽略，可以清楚打印具体文件和行号

```
git check-ignore -v filename
```

source: [git - Explain which gitignore rule is ignoring my file - Stack Overflow](https://stackoverflow.com/questions/12144633/explain-which-gitignore-rule-is-ignoring-my-file)

---

### 检查一个文件是否被git管理，被git管理的文件列表

```
# 当前目录所有被git管理的文件列表
git ls-tree -r HEAD --name-only

# 当前master分支被git管理的文件列表
git ls-tree -r master --name-only

# 曾经在git库出现的所有文件，所有分支，所有文件，包括删除的
git log --pretty=format: --name-only --diff-filter=A | sort - | sed '/^$/d'
```

source: [How can I make git show a list of the files that are being tracked? - Stack Overflow](https://stackoverflow.com/questions/15606955/how-can-i-make-git-show-a-list-of-the-files-that-are-being-tracked)

---

### 添加一个被gitignore忽略的文件

1. 找到被忽略规则的.gitignore
2. 最下面加一个例外规则，叹号开头，`!filepath`

source: [git - Make .gitignore ignore everything except a few files - Stack Overflow](https://stackoverflow.com/questions/987142/make-gitignore-ignore-everything-except-a-few-files)

---

### 强制加入文件到git管理

```
git add -f file
git add --force file
```

source: [git - Force add despite the .gitignore file - Stack Overflow](https://stackoverflow.com/questions/8006393/force-add-despite-the-gitignore-file)

---

### 克隆本地git项目，测试

克隆本地自己的库，验证是否缺少文件，是否提交正确后，再push推送到远程仓库

```
# git bash
git clone /D/proj/github/lukezhang-123/vim-win-msvc/.git

# 更新git，重置当前库文件
git pull
git reset --hard HEAD
```

---

### 撤回最后几次提交，提交错了信息，文件等等

```
# 撤回最后一次提交，当前本地文件不会被任何修改删除
git reset HEAD^
# 撤回最后一次提交，--hard 参数是当前本地文件回退到上次提交状态，删除修改信息，慎用
git reset --hard HEAD^

# 撤回最后两次提交
git reset HEAD~2

```

source: [Git delete last commit -- GitHub](https://gist.github.com/cutiko/0b1615c63504a940877541362cc51211)

---

### github提交敏感信息处理

source: 

[Removing sensitive data from a repository - GitHub Docs](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)

[从存储库中删除敏感数据 - GitHub 文档](https://docs.github.com/zh/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)

---

### github, markdown样例

source:

[Basic writing and formatting syntax - GitHub Docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

[Full Markdown Example, allysonsilva/Full-Markdown.md - GitHub](https://gist.github.com/allysonsilva/85fff14a22bbdf55485be947566cc09e)

[Markdown Cheatsheet · adam-p/markdown - GitHub](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

---

### github, markdwon preview online

[markdown-editor-online - GitHub](https://jbt.github.io/markdown-editor/)

---

### github bio 多行显示

原理：加全码空格，使页面排版自动换行

复制链接里，双引号内的，全码空格，放到bio每行后面

links: [Correct syntax for newline in Github Bio - Stack Overflow](https://stackoverflow.com/questions/43406317/correct-syntax-for-newline-in-github-bio)

