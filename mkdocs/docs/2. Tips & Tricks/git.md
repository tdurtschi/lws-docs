# Git

## My aliases

In particular, I use lol and lola constantly.

To use, amend your `~/.gitconfig` file with the aliases you want to include:

```
# This is Git's per-user configuration file.
[user]
    # ...

[alias]
    st = status
    ci = commit
    br = branch
    co = checkout
    ds = diff --staged
    lg = log -p
    lol = log --graph --decorate --pretty=oneline --abbrev-commit
    lola = log --graph --decorate --pretty=oneline --abbrev-commit --all 

```
