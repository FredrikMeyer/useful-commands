# Maven commands

## Install an artifact locally

```bash
mvn install:install-file  -Dfile=path-to-your-artifact-jar \
                          -DgroupId=your.groupId \
                          -DartifactId=your-artifactId \
                          -Dversion=version \
                          -Dpackaging=jar
```

Then import in `pom.xml` via

```xml
<dependency>
	<groupId>your.groupId</groupId>
        <artifactId>your-artifactId</artifactId>
        <version>version</version>
</dependency>
```

## Run Maven through a socks proxy

```
MAVEN_OPTS="-DsocksProxyHost=localhost -DsocksProxyPort=1234" mvn install
```

Passes the arguments to Java.
