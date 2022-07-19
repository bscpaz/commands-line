<h2 align="center">Linux for Java</h2>

## Environment

### Maven config

Installing distribution file

```bash
wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz -P /tmp
```

```bash
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
```

```bash
sudo ln -s /opt/apache-maven-3.8.6 /opt/maven
```


Setup environment variables

```bash
sudo vim /etc/profile.d/maven.sh
```

```file
export JAVA_HOME=/usr/lib/jvm/default-java
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

Verify the installation

```bash
mvn -version
```
