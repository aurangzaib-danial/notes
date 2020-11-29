# Remotes
Whenever we want to work with a remote like github, we have to tell git about the remote and also tell it to track against a branch of the remote.

## First add remote
```shell
$ git add remote origin 'url'
# origin is an alias for our remote, we could have named it anything but by convention.
```

## Pust code first time to the branch
```shell
$ git push -u origin master
# -u flag is for start tracking against the remote branch
```

**When we clone from github, we just get the master branch, to get all branches, type inside the directory after clonning `git fetch --all`**


