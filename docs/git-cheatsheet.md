\# Git 日常速查表



\## 基础三连（最常用）

git status              # 看当前改了啥

git add <文件名>        # 加入暂存区（git add . 是全部加入）

git commit -m "说明"     # 提交到本地仓库

git push                # 推到远端



\## 分支操作

git branch              # 看本地有哪些分支

git branch -a           # 看所有分支（包括远端）

git switch <分支名>     # 切换到已有分支

git switch -c <新分支名> # 创建并切换到新分支

git branch -d <分支名>  # 删除已合并的本地分支

git branch -D <分支名>  # 强制删除未合并的分支（慎用）



\## 同步远端

git pull                # 拉取并合并远端最新代码

git fetch               # 只拉取不合并

git push -u origin <分支名>  # 首次推送新分支



\## 查看历史

git log --oneline       # 简洁版提交历史

git log --oneline -5    # 最近 5 条

git diff                # 看工作区还没 add 的改动

git diff --cached       # 看已 add 但还没 commit 的改动



\## 撤销/回退

git restore <文件名>     # 丢弃工作区改动（没 add 之前）

git restore --staged <文件名>  # 撤出暂存区（不丢改动）

git commit --amend      # 改最近一次 commit 的消息

git reset --hard HEAD\~1 # 回退到上一次 commit（⚠️ 会丢改动）



\## 整理历史

git rebase -i HEAD\~3    # 合并最近 3 个 commit

git rebase main         # 变基到 main 最新位置



\## 远程管理

git remote -v           # 看远端地址

git remote set-url origin <新地址>  # 改远端地址

git remote prune origin # 清理远端已删分支的追踪记录



\## 冲突处理

git pull --rebase origin main   # 拉取时用 rebase

git status              # 看哪个文件冲突了

\# 手动编辑冲突文件，删掉 <<< === >>> 标记

git add <冲突文件>

git rebase --continue    # 继续 rebase

git rebase --abort       # 放弃 rebase



\## 临时暂存

git stash               # 藏起当前改动

git stash pop           # 恢复藏起的改动



\## 日常一句话

改完代码上传：git add . \&\& git commit -m "xxx" \&\& git push

拉取最新：git pull

开新功能：git switch -c feat/xxx → 改 → add → commit → push → 网页开 PR

改一半要切分支：git stash → 切分支 → 回来 git stash pop

