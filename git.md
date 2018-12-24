# Git

## Rename your local branch.
```
git branch -m new-name
git branch -m old-name new-name
```
## Delete the old-name remote branch and push the new-name local branch.
```
git push origin :old-name new-name
```
## Reset the upstream branch for the new-name local branch.
```
git push origin -u new-name
```
## fixup and autosquash
```
git commit --fixup <commit>
git rebase -i --autosquash <after-this-commit>
```
## Rebase commands
```
p, pick = use commit
r, reword = use commit, but edit the commit message
e, edit = use commit, but stop for amending
s, squash = use commit, but meld into previous commit
f, fixup = like "squash", but discard this commit's log message
x, exec = run command (the rest of the line) using shell
```
## Splitting a Commit
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
