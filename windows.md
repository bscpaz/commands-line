<h2 align="center">Windows helper</h2>

### Restoring WSL2 after new instalation
  * See https://github.com/codeedu/wsl2-docker-quickstart
  * After installing WSL2, open Power Shell in admin mode:

```console
wsl --list --verbose
wsl --shutdown
```
 * Replace the new .vhdx at ```%userprofile%\AppData\Local\Packages\CanonicalGroupLimited.Ubuntuon...\LocalState``` by your old .vhdx

```console
wsl --export Ubuntu D:\AppData\Local\Packages\UbuntuonWindows\ubuntu.tar
wsl --unregister Ubuntu
wsl --import Ubuntu D:\AppData\Local\Packages\UbuntuonWindows D:\AppData\Local\Packages\Backup\ubuntu.tar
```
 * Replace the old .vhdx at ```D:\AppData\Local\Packages\UbuntuonWindows```.

### Remove Caps Lock on screen
  * Disable OSD under Control Center 3.0 program

### Change name of Window's user folder
  * See youtube video: Y5_Q2BmTx3Y
