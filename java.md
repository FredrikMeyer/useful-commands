# Java

## Get current directory

```java
System.out.println(System.getProperty("user.dir"));
```

## Access files in _resource_ folder

```java
ClassLoader classLoader = getClass().getClassLoader();
File file = new File(Objects.requireNonNull(classLoader.getResource(TESTFILE)).getFile());
```

