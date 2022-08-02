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

### Accessing directy wsl directory
```console
\\wsl$
```

### Showing which system is running on wsl.
```
wsl --list -v
```

### Remove Caps Lock on screen
  * Disable OSD under Control Center 3.0 program

### Change name of Window's user folder
  * See youtube video: Y5_Q2BmTx3Y

### Generate ssh-key
```console
ssh-keygen -m PEM -t RSA -b 4096
```
### Problem with connectivity using WSL2
* Make sure that your wireless configurations is a private and a reliable connection (not a public).
* Make sure that you are not using a VPN connection.

### Windows' crash after blue screen
If you see the message as following
```console
Reboot and Select proper Boot device
or Insert Boot Media in selected Boot device and press a key
```
Try this:
* Restart the computer, press DEL key;
* On setup, go to "Boot" tab;
* Choose "UEFI Hard Disk Drive BBS Priorities" option;
* Turn "Boot Option #1" from disable to "Windows Boot Manager (NVme Cl1-8D128)".

If, although, you see the message as following:
```console
Secure Boot Violation
Invalid signature detected. Check Secure Boot Policy in Setup
```
Try this:
* Restart the computer, press DEL key;
* On setup, go to "Boot" tab;
* Disable "Secure Boot" option.

### Configuring Wildfly on Windows

```console
cd D:\Trabalho\wildfly-18.0.1.Final\standalone\configuration 
```

```console
 keytool -genkey -alias server -keyalg RSA -keystore application.keystore
```
For example: use the password as 'password'.
