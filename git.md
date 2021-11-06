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
