<h2 align="center">GIT commands</h2>

* Credentials configurations:
```console
bscpaz@2am:/$ git config core.sshCommand 'ssh -i "/home/bscpaz/.ssh/id_rsa"'
bscpaz@2am:/$ git remote set-url origin git@github.com:bscpaz/<repository>

bscpaz@2am:/$ git config --global user.name "Bruno Paz"
bscpaz@2am:/$ git config --global user.email "soujava@gmail.com"

bscpaz@2am:/$ git config --local user.name "Bruno Paz"
bscpaz@2am:/$ git config --local user.email "soujava@gmail.com"
```

* Show the credentials configurations:
```console
bscpaz@2am:/$ git config --global user.name
bscpaz@2am:/$ git config --global user.email

bscpaz@2am:/$ git config --local user.name
bscpaz@2am:/$ git config --local user.email
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
  - 

``` 

