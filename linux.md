<h2 align="center">Linux commands</h2>

* Files / Directories

| Command | Description |
| --- | --- |
| `mv file1.txt file2.txt` | Rename a file |
| `rm -dr <dir-name>` | Remove a non-empty dir recursively |
| `cd -` | Returns to the last directory |
| `ln -s <dir> <link-name>`| Creates a simbolic link |
| `mkdir -p br/com/bscpaz/user`| Creates multiple folders at once |


* Search

| Command | Description |
| --- | --- |
| `Ctrl + r` | Reverse-in-search |
| `Ctrl + r` (again) | Searches backwards through your history |
| `which <program>` | Shows the location of a program |


* IPs
 
| Command | Description |
| --- | --- |
| `apt update && apt install iproute2 -y` | Install IP package with confirmation |
| `apt-get update && apt-get install iputils-ping -y` | Intall PING package with confirmation |
| `ip addr show` | Shows the IP of current linux |


* Zip/Unzip

| Command | Description |
| --- | --- |
| `sudo apt-get install unzip` | Install Unzip package |
| `sudo apt-get install libzip-dev -y` | Install libzip-dev package |
| `sudo unzip path/filename.zip -d another_path_or_same_path` | Unzip a zip file from one directory to another. -d = directory |
| `tar -xvf sampleArchive.tar.gz` | Unzip a tar.gz. x=extract; v=vervose; f=file |
| `tar -xvf sampleArchive.tar.gz` | Unzip a tar.gz. x=extract; v=vervose; f=file |
| `tar -xvf sampleArchive.tar.gz -C /home/ExtractedFiles/`| Unzip a tar.gz. -C=target directory |



* JDK

| Command | Description |
| --- | --- |
| `sudo apt install default-jdk` | Install JDK |


* User / Permissions

| Command | Description |
| --- | --- |
| `su bscpaz` | Change user |
| `sudo -i` | Change to super user |
| `chown -R bscpaz:bscpaz <dir>` | Change owner recursively to user:group in `<dir>` folder |


* SSH

| Command | Description |
| --- | --- |
| `ssh-keygen -t rsa -b 4096` | Generates a SSH key par |

* WEB

| Command | Description |
| --- | --- |
| `apt-get update && apt-get install curl -y` | Install curl (client URL) |
| `curl http://localhost` | Check client URL connectivity |
| `curl http://host.docker.internal:8080` | A docker container accessing a service (8080) in the host machine (my machine) |
 
 * Environment

| Command | Description |
| --- | --- |
| `vim ~/.profile` | edit .profile file to export variables |
| `source ~/.profile` | reload .profile file |
| `nproc`| Shows the number of processing units available |
| `sudo cat /etc/passwd` | List all users |
 
