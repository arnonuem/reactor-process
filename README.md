# reactor-process

![Java CI](https://github.com/syamantm/reactor-process/workflows/CI%20Build/badge.svg?branch=master)

A java library to run a `java.lang.Process` with a reactive approach. It allows output of the process to be consumed as a reactive stream, instead of blocking and waiting for the process to finish. 

## Add dependency

### Configure GitHub packages repository
* Maven - [See official github instructions](https://help.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-apache-maven-for-use-with-github-packages)
* Gradle - [See official github instructions](https://help.github.com/en/packages/using-github-packages-with-your-projects-ecosystem/configuring-gradle-for-use-with-github-packages)

### Gradle dependency
```groovy
api("io.github.syamantm:reactor-process:0.0.1-SNAPSHOT")
```
### Maven dependency
```xml
<dependency>
  <groupId>io.github.syamantm</groupId>
  <artifactId>reactor-process</artifactId>
  <version>0.0.1-SNAPSHOT</version>
</dependency>
```

## Usage

```java
// Import the Processes utility class
import io.github.syamantm.reactor.process.Processes;

public class MyStreamingProcess {
  public Flux<String> processAsStream() { 
    // Create a ProcessBuilder
    ProcessBuilder pb = new ProcessBuilder().command("ls");

    // Return the reactive stream from a ProcessBuilder
    return Processes.fromBuilder(pb);
  }
}
```
