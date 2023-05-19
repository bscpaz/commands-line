<h2 align="center">WSL2/Windows helper</h2>

### Adding GUI into WSL2
```bash
sudo apt-get purge xrdp
```
```bash
sudo apt install -y xrdp
```
```bash
sudo apt install -y xfce4
```
```bash
sudo apt install -y xfce4-goodies
```
```bash
sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
```
```bash
sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
```
```bash
sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
```
```bash
sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
```
```bash
echo xfce4-session > ~/.xsession
```
```bash
sudo vim /etc/xrdp/startwm.sh
```
```bash
# test -x /etc/X11/Xsession && exec /etc/X11/Xsession
# exec /bin/sh /etc/X11/Xsession
startxfce4
```
```bash
sudo /etc/init.d/xrdp start
```
```bash
sudo apt install firefox
```

### Restoring WSL2 after new instalation
 * See https://github.com/codeedu/wsl2-docker-quickstart

 #### Recover the old Ubuntu installation:
 * Backup your old .vhdx putting it in ```D:\AppData\Local\Packages\Backup\``` path;
 * After installing WSL 2, open Power Shell in admin mode;
 * Execute the following commands to change the location of .vhdx file:

```console
wsl --list --verbose
```
```console
wsl --shutdown
```
To terminate the specified distribution, or stop it from running
```console
wsl --terminate Ubuntu
```
```console
wsl --export Ubuntu D:\AppData\Local\Packages\Backup\ubuntu.tar
```
```console
wsl --unregister Ubuntu
```
```console
wsl --import Ubuntu D:\AppData\Local\Packages\UbuntuonWindows D:\AppData\Local\Packages\Backup\ubuntu.tar
```
```console
wsl --import Ubuntu C:\desenvolvimento\wsl2\ubuntu D:\AppData\Local\Packages\Backup\ubuntu_pje.tar
```
 * Replace the new .vhdx by your backup file.

 #### Reset root password:
 * Log-in the ubuntu with root user.
```console
whoami
```
```console
passwd
```
 #### Change default user
 * Open the Windows Terminal program:
```console
cd C:\Users\bscpaz\AppData\Local\Microsoft\WindowsApps\CanonicalGroupLimited.UbuntuonWindows_***
```
```console
./ubuntu config --default-user bscpaz
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
  * Disable OSD under Control Center 3.0 program (right click on icon)

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

### Limpeza Epson
* Clique na impressora;
* Gerenciar;
* Preferência de impressão;
* Guia "manutenção".
