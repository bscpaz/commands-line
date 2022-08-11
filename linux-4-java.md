<h2 align="center">Linux for Java</h2>

## Environment

### Installing OpenJDK 8

#### Dowload the jdk-8u202-linux-x64.tar.gz

```bash
cp /mnt/d/Users/bscpaz/Downloads/jdk-8u202-linux-x64.tar.gz /tmp
```

```bash
sudo tar xf /tmp/jdk-8u202-linux-x64.tar.gz -C /usr/lib/jvm
```

```bash
cd /usr/lib/jvm
```

```bash
sudo ln -s jdk1.8.0_202 default-java
```

```bash
sudo vim /etc/profile.d/jdk.sh
```

```file
export JAVA_HOME=/usr/lib/jvm/default-java
export PATH=${JAVA_HOME}/bin:${PATH}
```

```bash
sudo chmod +x /etc/profile.d/jdk.sh
```

```bash
source /etc/profile.d/jdk.sh
```

```bash
java -version
```

### Installing Eclipse in WSL2

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
sudo apt install libswt-gtk-4-jni
```
```bash
sudo apt install openjdk-8-jdk
```

### Maven config

#### Installing distribution file

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz -P /tmp
```

```bash
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
```

```bash
sudo ln -s /opt/apache-maven-3.8.6 /opt/maven
```

#### Setup environment variables

```bash
sudo vim /etc/profile.d/maven.sh
```

```file
export M2_HOME=/opt/maven
export MAVEN_HOME=/opt/maven
export PATH=${M2_HOME}/bin:${PATH}
```

```bash
sudo chmod +x /etc/profile.d/maven.sh
```

```bash
source /etc/profile.d/maven.sh
```

#### Verify the installation

```bash
mvn -version
```

#### VSCode configuration

###### On VSCode, Close and Open to reload.
###### Add the following path as the picture below:

```bash
/opt/apache-maven-3.8.6/bin/mvn
```

![image](https://user-images.githubusercontent.com/9732874/179816973-fea7dee0-e628-4b6e-92a4-b48b5b4f788c.png)

