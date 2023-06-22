# Random Generator

This is a simple random number generation application which just generates a random string on `/random` endpoint.

## How to build
Just run `mvn clean install`

## How to run
Do `mvn spring-boot:run`

After spring boot initializes, just do a `curl localhost:8080/random` to check endpoint.


```bash
➤ mvn org.eclipse.jkube:kubernetes-maven-plugin:migrate
```

```diff
diff --git a/pom.xml b/pom.xml
index 25511af..9fc99b2 100755
--- a/pom.xml
+++ b/pom.xml
@@ -1,6 +1,4 @@
-<?xml version="1.0" encoding="UTF-8"?>
-<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
-         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
+<?xml version="1.0" encoding="UTF-8"?><project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
     <modelVersion>4.0.0</modelVersion>
 
     <groupId>meetup</groupId>
@@ -22,7 +20,7 @@
         <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
         <project.reporting.outputEncoding>UTF-8</project.reporting.outputEncoding>
         <java.version>1.8</java.version>
-        <fabric8.enricher.fmp-service.type>NodePort</fabric8.enricher.fmp-service.type>
+        <jkube.enricher.jkube-service.type>NodePort</jkube.enricher.jkube-service.type>
     </properties>
 
     <dependencies>
@@ -58,12 +56,12 @@
             </plugin>
 
             <plugin>
-                <groupId>io.fabric8</groupId>
-                <artifactId>fabric8-maven-plugin</artifactId>
-                <version>4.4.1</version>
+                <groupId>org.eclipse.jkube</groupId>
+                <artifactId>kubernetes-maven-plugin</artifactId>
+                <version>1.13.1</version>
             </plugin>
         </plugins>
     </build>
 
 
-</project>
+</project>
\ No newline at end of file
diff --git a/readme.md b/readme.md
index 3a8f26d..9b346ea 100644
--- a/readme.md
+++ b/readme.md
@@ -9,3 +9,9 @@ Just run `mvn clean install`
 Do `mvn spring-boot:run`
 
 After spring boot initializes, just do a `curl localhost:8080/random` to check endpoint.
+
+
+```bash
+➤ mvn org.eclipse.jkube:kubernetes-maven-plugin:migrate
+```
+
```

```txt
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< meetup:random-generator >-----------------------
[INFO] Building random-generator 0.0.1
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-dependency-plugin:3.1.1:tree (default-cli) @ random-generator ---
[INFO] meetup:random-generator:jar:0.0.1
[INFO] +- org.springframework.boot:spring-boot-starter-actuator:jar:2.1.8.RELEASE:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter:jar:2.1.8.RELEASE:compile
[INFO] |  |  +- org.springframework.boot:spring-boot-starter-logging:jar:2.1.8.RELEASE:compile
[INFO] |  |  |  +- ch.qos.logback:logback-classic:jar:1.2.3:compile
[INFO] |  |  |  |  \- ch.qos.logback:logback-core:jar:1.2.3:compile
[INFO] |  |  |  +- org.apache.logging.log4j:log4j-to-slf4j:jar:2.11.2:compile
[INFO] |  |  |  |  \- org.apache.logging.log4j:log4j-api:jar:2.11.2:compile
[INFO] |  |  |  \- org.slf4j:jul-to-slf4j:jar:1.7.28:compile
[INFO] |  |  +- javax.annotation:javax.annotation-api:jar:1.3.2:compile
[INFO] |  |  \- org.yaml:snakeyaml:jar:1.23:runtime
[INFO] |  +- org.springframework.boot:spring-boot-actuator-autoconfigure:jar:2.1.8.RELEASE:compile
[INFO] |  |  +- org.springframework.boot:spring-boot-actuator:jar:2.1.8.RELEASE:compile
[INFO] |  |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.9.9.3:compile
[INFO] |  |  |  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.9.0:compile
[INFO] |  |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.9.9:compile
[INFO] |  |  +- org.springframework:spring-context:jar:5.1.9.RELEASE:compile
[INFO] |  |  \- com.fasterxml.jackson.datatype:jackson-datatype-jsr310:jar:2.9.9:compile
[INFO] |  \- io.micrometer:micrometer-core:jar:1.1.6:compile
[INFO] |     +- org.hdrhistogram:HdrHistogram:jar:2.1.9:compile
[INFO] |     \- org.latencyutils:LatencyUtils:jar:2.0.3:compile
[INFO] +- org.springframework.boot:spring-boot-starter-web:jar:2.1.8.RELEASE:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter-json:jar:2.1.8.RELEASE:compile
[INFO] |  |  +- com.fasterxml.jackson.datatype:jackson-datatype-jdk8:jar:2.9.9:compile
[INFO] |  |  \- com.fasterxml.jackson.module:jackson-module-parameter-names:jar:2.9.9:compile
[INFO] |  +- org.springframework.boot:spring-boot-starter-tomcat:jar:2.1.8.RELEASE:compile
[INFO] |  |  +- org.apache.tomcat.embed:tomcat-embed-core:jar:9.0.24:compile
[INFO] |  |  +- org.apache.tomcat.embed:tomcat-embed-el:jar:9.0.24:compile
[INFO] |  |  \- org.apache.tomcat.embed:tomcat-embed-websocket:jar:9.0.24:compile
[INFO] |  +- org.hibernate.validator:hibernate-validator:jar:6.0.17.Final:compile
[INFO] |  |  +- javax.validation:validation-api:jar:2.0.1.Final:compile
[INFO] |  |  +- org.jboss.logging:jboss-logging:jar:3.3.3.Final:compile
[INFO] |  |  \- com.fasterxml:classmate:jar:1.4.0:compile
[INFO] |  +- org.springframework:spring-web:jar:5.1.9.RELEASE:compile
[INFO] |  |  \- org.springframework:spring-beans:jar:5.1.9.RELEASE:compile
[INFO] |  \- org.springframework:spring-webmvc:jar:5.1.9.RELEASE:compile
[INFO] |     +- org.springframework:spring-aop:jar:5.1.9.RELEASE:compile
[INFO] |     \- org.springframework:spring-expression:jar:5.1.9.RELEASE:compile
[INFO] +- org.springframework.boot:spring-boot-devtools:jar:2.1.8.RELEASE:runtime
[INFO] |  +- org.springframework.boot:spring-boot:jar:2.1.8.RELEASE:compile
[INFO] |  \- org.springframework.boot:spring-boot-autoconfigure:jar:2.1.8.RELEASE:compile
[INFO] \- org.springframework.boot:spring-boot-starter-test:jar:2.1.8.RELEASE:test
[INFO]    +- org.springframework.boot:spring-boot-test:jar:2.1.8.RELEASE:test
[INFO]    +- org.springframework.boot:spring-boot-test-autoconfigure:jar:2.1.8.RELEASE:test
[INFO]    +- com.jayway.jsonpath:json-path:jar:2.4.0:test
[INFO]    |  +- net.minidev:json-smart:jar:2.3:test
[INFO]    |  |  \- net.minidev:accessors-smart:jar:1.2:test
[INFO]    |  |     \- org.ow2.asm:asm:jar:5.0.4:test
[INFO]    |  \- org.slf4j:slf4j-api:jar:1.7.28:compile
[INFO]    +- junit:junit:jar:4.12:test
[INFO]    +- org.assertj:assertj-core:jar:3.11.1:test
[INFO]    +- org.mockito:mockito-core:jar:2.23.4:test
[INFO]    |  +- net.bytebuddy:byte-buddy:jar:1.9.16:test
[INFO]    |  +- net.bytebuddy:byte-buddy-agent:jar:1.9.16:test
[INFO]    |  \- org.objenesis:objenesis:jar:2.6:test
[INFO]    +- org.hamcrest:hamcrest-core:jar:1.3:test
[INFO]    +- org.hamcrest:hamcrest-library:jar:1.3:test
[INFO]    +- org.skyscreamer:jsonassert:jar:1.5.0:test
[INFO]    |  \- com.vaadin.external.google:android-json:jar:0.0.20131108.vaadin1:test
[INFO]    +- org.springframework:spring-core:jar:5.1.9.RELEASE:compile
[INFO]    |  \- org.springframework:spring-jcl:jar:5.1.9.RELEASE:compile
[INFO]    +- org.springframework:spring-test:jar:5.1.9.RELEASE:test
[INFO]    \- org.xmlunit:xmlunit-core:jar:2.6.3:test
[INFO]       \- javax.xml.bind:jaxb-api:jar:2.3.1:test
[INFO]          \- javax.activation:javax.activation-api:jar:1.2.0:test
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.835 s
[INFO] Finished at: 2023-06-23T01:02:14+08:00
[INFO] ------------------------------------------------------------------------
```


```bash
➤ mvn dependency:resolve-plugins


```