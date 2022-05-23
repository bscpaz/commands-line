<h2 align="center">GIT commands</h2>

## Configurations
#### Rename a remote source
```console
git remote -v
```
```console
git remote rename <old> <new>
 ```
#### Credentials configurations:
```console
git config core.sshCommand 'ssh -i "/home/bscpaz/.ssh/id_rsa"'
```
```console
git remote set-url origin git@github.com:bscpaz/<repository>
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

#### Git clone / remote:
```console
git clone -o <remote name> git@github.com:bscpaz/<repository>
```
```console
git remote add <remote name> https://git....
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

