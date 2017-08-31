
# GIT LUNCH AND LEARN

## Intro

## Command Line vs GUI tools

* git-gui
* Visual Studio Code
* Visual Studio
* git bash

### CLI PROS

* Work on every development platform
* Work can be automated
* Command line is the only option for specific tasks
* The command line lets you know exactly what you do, exactly when you do it

### GUI PROS

* GUIs help take care of a lot of work that can be obscure
* A GUI can save you many lines of code with a drag-and-drop or the push of a button
* The barrier-of-entry for GUIs is much lower than for the command line
* Most importantly, GUIs are best able to graphically represent collaboration

## Basic Day to Day WorkFlow

### Most Important

``git status``

### Branching

Show All branches ``git branch -a | grep SPWEB*``

``` sh
git branch new-branch-name master
git checkout new-branch-name master
OR
git checkout -b BEL-4015-a-good-resume-sentence-on-the-PBI
```

``` sh
git push -u origin new-branch-name
```

### Work

``` sh
git pull
git add *
git commit -m 'blah'
git push
```

### Sync and Pull Requests

``` bash
# when work is done
# create Pull Request
# then after completion / merge, remote branch is deleted
# we sync master
git checkout master
git pull
# if you need to work again on your branch then
git checkout your-branch
git merge master
# otherwise
git remote prune origin
git branch -d my-new-feature
```

### history

``` sh
git log
gitk filename
```

## Merging

``` sh
git merge master
# merging mode
git commit -m 'fixed some merge conflicts'
```

## Stashes (~Shelvesets)

``` sh
git stash
git list
git apply
```

## bash Profile

``~/.gitconfig``

``` sh
[gui]
        recentrepo = C:/newSources
[user]
        email = camille.viot@marinepress.com
        name = Camille VIOT
[alias]
lg1 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
lg = !"git lg1"
        co = checkout
        br = branch
        ci = commit
        s = status
        p = push

[core]
        editor = 'c:/program files/sublime text 3/subl.exe' -w
```

``~/.bashrc``
``cd "/c/Src/OpenSeasGit"``

## Aliases

``git config --global alias.pl pull``

## SSH vs HTTPS Connection to the remote

[public SSH Key](https://www.visualstudio.com/fr-ca/docs/git/use-ssh-keys-to-authenticate)

## More advanced situations

Visit a specific commit in time :

``` sh
git checkout <commit hash>
# want to experiment some changes ?
git checkout -b new-branch <commit-hash>
```

## Undo things :

Undo latest commit

``` sh
git reset --hard HEAD
```

Ammend last commit

```sh
git commit --amend
```

Hard delete **unpublished** commits :

``` sh
git reset --hard <commit hash>
# some work to keep before ?
git stash
git reset --hard <commit hash>
git stash pop
```

Hard delete **published** commits :

``` sh
git revert <commit hash 1> <commit hash 2> <commit hash 3>
# some work to keep before ?
git commit
```


### rebase / 