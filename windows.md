<h2 align="center">Windows helper</h2>

### Restoring WSL2 after new instalation
 * See https://github.com/codeedu/wsl2-docker-quickstart

 #### Recover the old Ubuntu installation:
 * Backup your old .vhdx putting it in ```D:\AppData\Local\Packages\Backup\``` path;
 * After installing WSL 2, open Power Shell in admin mode;
 * Execute the following commands to change the location of .vhdx file:

```console
wsl --list --verbose
wsl --shutdown
wsl --export Ubuntu D:\AppData\Local\Packages\Backup\ubuntu.tar
wsl --unregister Ubuntu
wsl --import Ubuntu D:\AppData\Local\Packages\UbuntuonWindows D:\AppData\Local\Packages\Backup\ubuntu.tar
```
 * Replace the new .vhdx by your backup file.

 #### Reset root password:
 * Log-in the ubuntu with root user.
```console
root@host:~# whoami
root
root@host:~# passwd
enter new UNIX password: <YOUR NEW PASSWORD>
retype new UNIX password: <YOUR NEW PASSWORD>
passwd: password updated successfully
```
 #### Change default user
 * Open the Windows Terminal program:
```console
cd C:\Users\bscpaz\AppData\Local\Microsoft\WindowsApps\CanonicalGroupLimited.UbuntuonWindows_***
./ubuntu config --default-user bscpaz (yes, with "./" instruction)
``` 

### Remove Caps Lock on screen
  * Disable OSD under Control Center 3.0 program

### Change name of Window's user folder
  * See youtube video: Y5_Q2BmTx3Y

### Generate ssh-key
```console
ssh-keygen -m PEM -t RSA -b 4096
```
