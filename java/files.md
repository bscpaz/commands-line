<h1 align="center">Java files</h1>
<p align="center">This page shows Java classes related to files</p>

#### java.io.InputStream
A Java _InputStream_ is connected to some data source of ordered sequence of bytes, like a file, a network connection, a pipe. This is an abstract class and we need to use one of it's subclasses like _FileInputStream_, _BufferedInputStream_, _DataInputStream_.

Exemple:
```java
ClassLoader classloader = Thread.currentThread().getContextClassLoader();
InputStream fis = classloader.getResourceAsStream("input.xlsx");
```

#### java.io.FileInputStream
A _FileInputStream_ obtains input bytes from a file in a file system. _FileInputStream_ is meant for reading streams of raw bytes such as image data. For reading streams of characters, consider using _FileReader_.

Exemple:
```java
InputStream inputstream = new FileInputStream("/source/input_text.txt");
```
