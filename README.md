# State Machine Compiler
This project forked https://github.com/orolle/SMC, primarily so the artifacts are published to maven central

```
<project>
  ...
  <packaging>jar</packaging>
  ...
  <build>
    <plugins>
      <plugin>
        <groupId>com.github.orolle</groupId>
        <artifactId>smc-maven-plugin</artifactId>
        <executions>
           <execution>
              <goals>
                 <goal>smc</goal>
              </goals>
           </execution>
        </executions>
        <configuration>
          <verbose>true</verbose>
          <sync>true</sync>
          ...
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
Put your sm-files in the "src/main/smc"-folder of your project root. Compile the sm-files to java-classes through executing "mvn smc:smc". The generated classes are found in "target/generated-sources/smc"-folder. The plugin is in an early and buggy version. Please use it with caution and on your own risk.

To execute the compiled java-classes include the maven dependency in your pom.xml
```
<dependency>
  <groupId>uk.camsw.smc</groupId>
  <artifactId>smc-lib-java</artifactId>
  <version>6.4.0</version>
</dependency>
```

For modelling finite state machines with SMC please see http://smc.sourceforge.net/SmcManual.htm
A good and dense slide-based tutorial is found here  http://smc.sourceforge.net/slides/SMC_Tutorial.pdf
