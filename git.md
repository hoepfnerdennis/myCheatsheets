# Git

- [Branches](#Branches)
  * [List all Branches](#List-all-Branches)
  * [Rename your local branch](#Rename-your-local-branch)
  * [Delete local branch](#Delete-local-branch)
  * [Delete the old-name remote branch and push the new-name local branch](#Delete-the-old-name-remote-branch-and-push-the-new-name-local-branch)
  * [Reset the upstream branch for the new-name local branch](#Reset-the-upstream-branch-for-the-new-name-local-branch)
- [Commits and Manipulating](#Commits-and-Manipulating)
  * [fixup and autosquash](#fixup-and-autosquash)
  * [Rebase commands](#Rebase-commands)
  * [Splitting a Commit](#Splitting-a-Commit)
  
## Branches
### List all Branches
```
git branch -a
```
### Rename your local branch
```
git branch -m new-name
git branch -m old-name new-name
```
### Delete local branch
```
git branch -d branch_name
git branch -D branch_name
```
### Delete the old-name remote branch and push the new-name local branch
```
git push origin :old-name new-name
```
### Reset the upstream branch for the new-name local branch
```
git push origin -u new-name
```
## Commits and Manipulating
### fixup and autosquash
```
git commit --fixup <commit>
git rebase -i --autosquash <after-this-commit>
```
### Rebase commands
```
p, pick = use commit
r, reword = use commit, but edit the commit message
e, edit = use commit, but stop for amending
s, squash = use commit, but meld into previous commit
f, fixup = like "squash", but discard this commit's log message
x, exec = run command (the rest of the line) using shell
```
### Splitting a Commit
```
pick f7f3f6d changed my name a bit
edit 310154e updated README formatting and added blame
pick a5f4a0d added cat-file
```
```
$ git reset HEAD^
$ git add README
$ git commit -m 'updated README formatting'
$ git add lib/simplegit.rb
$ git commit -m 'added blame'
$ git rebase --continue
```
