## §Install

```shell
maven clean install
maven dockerfile:build
```


simple config i pom.xml 

```xml
<plugins>
    <plugin>
        <groupId>com.spotify</groupId>
        <artifactId>dockerfile-maven-plugin</artifactId>
        <executions>
            <execution>
                <id>default</id>
                <goals>
                    <goal>build</goal>
                </goals>
            </execution>
        </executions>
    </plugin>
</plugins>
```

with image name
```xml
 <configuration>
    <repository>ghoul/basic</repository>
 </configuration>
```


with build arguments
```xml
<buildArgs>
    <IMAGE_VERSION>0.0.1</IMAGE_VERSION>
</buildArgs>
```


with custom tag
```xml
<buildArgs>
    <tag>unstable</tag>
</buildArgs>
```

or tagged with project version

```xml 
 <tag>${project.version}</tag>
 ```

use custom dockerfile 

 ```xml
<contextDirectory>context</contextDirectory>
<dockerfile>context/sub/Dockerfile</dockerfile>

```

to skip  build docker 
```xml 
<configuration>
    <skip>true</skip>
</configuration>

```