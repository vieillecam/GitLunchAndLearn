
# GIT LUNCH AND LEARN

## Intro

## Command Line vs GUI tools

* git-gui
* Visual Studio Code
* Visual Studio
* ...


## Basic Day to Day WorkFlow

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

### Lastest commit

Undo latest commit

``` sh
git reset --hard HEAD
```

Ammend last commit

```sh
git commit --amend
```


## Merging

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