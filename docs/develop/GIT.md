#### git 工具配置

---

> git是最常用的分布式版本控制工具，通过分布式，分支管理， 数据完整性，速度等特性，git都是必不可少的工具

##### command：
> - 提供常用的git命令alias缩写
```bash
# git stash
alias gss="git stash save"
alias gsa="git stash apply"
alias gsl="git stash list"

# git status
alias gs="git status"
# git branch
alias gb="git branch"

# git diff
alias gdiff="git diff"
alias gdifflocal="git diff --cached"

# git reset
alias greset="git reset --mixed"
alias greseth="git reset --hard"
alias gresets="git reset --soft"
# git revert
alias grevert="git revert"
# git clean
alias gclean="git clean -n"
alias gcleanf="git clean -f"
alias gcleanfd="git clean -df"

# push pull fetch merge rebase checkout add commit cherry-pick
# git checkout
alias gch="git checkout"
alias gchb="git checkout -b"
# git rebase
alias gr="git rebase"
alias gri="git rebase -i"
# git fetch
alias gf="git fetch"
# git pull
alias gpl="git pull"
# git push
alias gp="git push"
alias gpom="git push origin master"
alias gpsom="git push --set-upstream origin master"
# git merge
alias gm="git merge"
alias gmm="git merge master"
alias gmabort="git merge --abort"
# git commit
alias gcm="git commit -m"
# git add
alias ga="git add"
# git cherry-pick
alias gcp="git cherry-pick"
# git tag
alias gtl="git tag -l"
alias gtdel="git tag -d"
alias gt="git tag"
# push first recent tag
alias gtp="git push origin | git tag | head -n 1"
```

---

##### git config：
> git 提供了 config 子命令，可用于指定一些配置，如下:
> 注意 --global 是全局生效，如果只想让当前项目生效，可以不加
> 可以通过 .git/config 查看当前仓库所有的配置
> 可以通过 ~/.gitconfig 查看当前git工具的配置

```bash
# display .gitconfig
git config --list --global --show-origin

# 这两个是提交commit必须的配置，并且email会对github的贡献值统计有影响
git config --global user.email "xxx@gmail.com"
git config --global user.name "xxxx"

# core command
git config core.sshCommand "ssh -i /path/to/key"

# http proxy
git config --global http.proxy http://localhost:8090
git config --global https.proxy http://localhost:8090
```