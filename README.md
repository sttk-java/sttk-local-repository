# [local-m2-repository][repo-url]

Maven 2 compatible local repository for Sttk Java library


## Declaring this repository

This section assumes that this repository is located just under the parent directory of your project root directory (`${project.root.dir}/../local-m2-repository`).


### for Maven

`pom.xml`:

```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <repositories>
    <repository>
      <id>local-m2-repository</id>
      <url>file://${user.dir}/../local-m2-repository</url>
    </repository>
  </repositories>
</project>
```

### for Gradle 

`build.gradle`:

```
repositories {
  maven {
    url "../local-m2-repository"
  }
}
```

### for Ivy

`ivysettings.xml`:

```
<ivysettings>
  <settings defaultResolver="local-m2-repository" />
  <resolvers>
    <filesystem name="local-m2-repository" m2compatible="true">
      <artifact pattern="${basedir}/../local-m2-repository/[organisation]/[module]/[revision]/[module]-[revision](-[classifier]).[ext]" />
    </filesystem>
  </resolvers>
</ivysettings>
```


## License

Copyright (C) 2021 Takayuki Sato

This program is free software under MIT License.
See the file LICENSE in this distribution for more details.


[repo-url]: https://github.com/sttk-java/local-m2-repository
