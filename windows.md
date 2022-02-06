<h2 align="center">Windows helper</h2>

### Restoring WSL2 after new instalation
 * See https://github.com/codeedu/wsl2-docker-quickstart
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
 * To change the default user, open the Windows Terminal program:
```console
cd C:\Users\bscpaz\AppData\Local\Microsoft\WindowsApps\CanonicalGroupLimited.UbuntuonWindows_***
./ubuntu config --default-user bscpaz (yes, with "./" instruction)
``` 

### Remove Caps Lock on screen
  * Disable OSD under Control Center 3.0 program

### Change name of Window's user folder
  * See youtube video: Y5_Q2BmTx3Y
