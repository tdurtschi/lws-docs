# Git

## My aliases

I find these git aliases useful to reduce typing. In particular, I use `git lol` and `git lola` daily, since they are very helpful commands and who can remember all those flags?

To use a git alias, just substitute the command with the alias. E.g. `git st` instead of `git status` .

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
