<h2 align="center">GIT commands</h2>

## Configurations
#### Creating a SSH Keys
```console
ssh-keygen -t rsa -b 4096
```

#### Remote's commands
```console
git remote -v
```
```console
git clone -o <remote name> git@github.com:bscpaz/<repository>
```
```console
git remote add <remote name> https://git....
```
```console
git remote set-url origin git@github.com:bscpaz/<repository>
```
```console
git remote remove <remote name>
```
```console
git remote rename <old> <new>
 ```
#### Credentials configurations:
```console
git config core.sshCommand 'ssh -i "/home/bscpaz/.ssh/id_rsa"'
```
```console
git config --global user.name "Bruno Paz"
```
```console
git config --global user.email "soujava@gmail.com"
```
```console
git config --local user.name "Bruno Paz"
```
```console
git config --local user.email "soujava@gmail.com"
```
```console
git config --global credential.helper store
```
```console
git config --global credential.helper cache
```

Note: if the authentication fails, close the terminal and try again.

#### Show the credentials configurations:
```console
git config --global user.name
```
```console
git config --global user.email
```
```console
git config --local user.name
```
```console
git config --local user.email
```

## Commons commands
### Branch:

###### List all branches
```console
git branch
```
###### Remove a branch
```console
git branch -D <branch name>
```
###### Checkout to a new branch using a specific remote
```console
git checkout -b <branch name> --track <remote>/<branch>
```
###### Checkout to a existing branch
```console
git checkout <branch name>
```
###### Rename a existing branch
```console
git branch -m <new name>
```

###### Check logs on a branch
```console
git log -p .
```

###### Check logs on a file
```console
git log -p <file-name>
```

###### See what has changed in a file
```console
git diff <file-name>
```

###### Change commit's author
```console
git commit --amend --author="Bruno Paz<soujava@gmail.com>"
```
<hr>
<h4 align="center">Known issues</h4>

```console
Issue:
  Clonning a git repository using WSL2 occurs timeout on port 22 or 443

  bscpaz@2am:/$ git clone git@github.com:bscpaz/<some-repo>
  Cloning into '<some-repo>'...
  ssh: connect to host github.com port 22: Connection timed out
  fatal: Could not read from remote repository.

  Please make sure you have the correct access rights
  and the repository exists.
  
Solution:
  - First, check if your WSL2 can run a "sudo apt-get update". If not, it's a general problem.
  - Turn off your VPN and try again.
``` 

