<h1 align="center">Hibernate</h1>
<p align="center">This page shows Hibernate problems and solutions.</p>

#### ERROR: operator does not exist: character = bytea

###### Problem with parameters passed to nativeQuery. Convert Enum key to String.
Exemple: change the following
```java
query.setParameter("param", MyEnum.D);
```
to this way:
```java
query.setParameter("param", MyEnum.D.toString());
```
