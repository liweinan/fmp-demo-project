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