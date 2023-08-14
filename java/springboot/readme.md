### JAR to WAR

If you want the project's build to package the application into a WAR file, you will need to make the following changes:

1) Add the `<packaging>war</packaging>` tag to the project's pom.xml file and add the dependency below:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.7.14</version>
    <relativePath/>
  </parent>
  <groupId>bscpaz.com.br</groupId>
  <artifactId>api</artifactId>
  <version>1.0.0</version>
  <name>api</name>
  <packaging>war</packaging>
...
  <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-tomcat</artifactId>
    <scope>provided</scope>
  </dependency>
```   
2) Modify the main class of the project (ApiApplication) to inherit from the `SpringBootServletInitializer` class and override the configure method:
```java
@SpringBootApplication
public class ApiApplication extends SpringBootServletInitializer {

  @Override
  protected SpringApplicationBuilder configure(SpringApplicationBuilder application) {
    return application.sources(ApiApplication.class);
  }

  public static void main(String[] args) {
    SpringApplication.run(ApiApplication.class, args);
  }
}
```
