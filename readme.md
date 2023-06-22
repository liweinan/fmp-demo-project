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

[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< meetup:random-generator >-----------------------
[INFO] Building random-generator 0.0.1
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- maven-dependency-plugin:3.1.1:resolve-plugins (default-cli) @ random-generator ---
[INFO] 
[INFO] The following plugins have been resolved:
[INFO]    org.apache.maven.plugins:maven-site-plugin:maven-plugin:3.7.1:runtime
[INFO]       org.apache.maven.plugins:maven-site-plugin:jar:3.7.1
[INFO]       org.apache.maven.reporting:maven-reporting-exec:jar:1.4
[INFO]       org.apache.maven.reporting:maven-reporting-api:jar:3.0
[INFO]       org.apache.maven:maven-artifact:jar:3.0
[INFO]       org.sonatype.aether:aether-util:jar:1.7
[INFO]       org.eclipse.aether:aether-util:jar:0.9.0.M2
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.1.0
[INFO]       org.apache.maven:maven-core:jar:3.0
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.0
[INFO]       org.apache.maven:maven-model-builder:jar:3.0
[INFO]       org.apache.maven:maven-aether-provider:jar:3.0
[INFO]       org.sonatype.aether:aether-impl:jar:1.7
[INFO]       org.sonatype.aether:aether-spi:jar:1.7
[INFO]       org.sonatype.aether:aether-api:jar:1.7
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.14
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.7.1
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-model:jar:3.0
[INFO]       org.apache.maven:maven-plugin-api:jar:3.0
[INFO]       org.apache.maven:maven-settings:jar:3.0
[INFO]       org.apache.maven:maven-settings-builder:jar:3.0
[INFO]       org.apache.maven:maven-archiver:jar:3.1.1
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.codehaus.plexus:plexus-archiver:jar:3.4
[INFO]       org.codehaus.plexus:plexus-io:jar:2.7.1
[INFO]       org.apache.commons:commons-compress:jar:1.11
[INFO]       org.iq80.snappy:snappy:jar:0.4
[INFO]       org.tukaani:xz:jar:1.5
[INFO]       org.codehaus.plexus:plexus-i18n:jar:1.0-beta-10
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.0.24
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.5.2
[INFO]       org.apache.maven.doxia:doxia-sink-api:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-logging-api:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-module-xhtml:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-core:jar:1.8
[INFO]       org.apache.httpcomponents:httpclient:jar:4.0.2
[INFO]       commons-codec:commons-codec:jar:1.3
[INFO]       org.apache.httpcomponents:httpcore:jar:4.0.1
[INFO]       org.apache.maven.doxia:doxia-module-apt:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-module-xdoc:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-module-fml:jar:1.8
[INFO]       org.apache.maven.doxia:doxia-module-markdown:jar:1.8
[INFO]       com.vladsch.flexmark:flexmark-all:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-abbreviation:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-anchorlink:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-aside:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-autolink:jar:0.18.4
[INFO]       org.nibor.autolink:autolink:jar:0.6.0
[INFO]       com.vladsch.flexmark:flexmark-ext-definition:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-emoji:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-escaped-character:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-footnotes:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-gfm-strikethrough:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-gfm-tables:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-gfm-tasklist:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-jekyll-front-matter:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-jekyll-tag:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-ins:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-xwiki-macros:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-spec-example:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-test-util:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-superscript:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-tables:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-toc:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-typographic:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-wikilink:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-ext-yaml-front-matter:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-formatter:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-html-parser:jar:0.18.4
[INFO]       org.jsoup:jsoup:jar:1.10.2
[INFO]       com.vladsch.flexmark:flexmark-jira-converter:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-pdf-converter:jar:0.18.4
[INFO]       com.openhtmltopdf:openhtmltopdf-core:jar:0.0.1-RC9
[INFO]       com.openhtmltopdf:openhtmltopdf-pdfbox:jar:0.0.1-RC9
[INFO]       org.apache.pdfbox:pdfbox:jar:2.0.4
[INFO]       org.apache.pdfbox:fontbox:jar:2.0.4
[INFO]       com.openhtmltopdf:openhtmltopdf-rtl-support:jar:0.0.1-RC9
[INFO]       com.ibm.icu:icu4j:jar:58.1
[INFO]       com.openhtmltopdf:openhtmltopdf-jsoup-dom-converter:jar:0.0.1-RC9
[INFO]       com.vladsch.flexmark:flexmark-profile-pegdown:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-util:jar:0.18.4
[INFO]       com.vladsch.flexmark:flexmark-youtrack-converter:jar:0.18.4
[INFO]       javax.servlet:servlet-api:jar:2.5
[INFO]       org.apache.maven.doxia:doxia-decoration-model:jar:1.8.1
[INFO]       org.apache.maven.doxia:doxia-site-renderer:jar:1.8.1
[INFO]       org.apache.maven.doxia:doxia-skin-model:jar:1.8.1
[INFO]       org.codehaus.plexus:plexus-container-default:jar:1.0-alpha-30
[INFO]       junit:junit:jar:3.8.1
[INFO]       org.codehaus.plexus:plexus-velocity:jar:1.2
[INFO]       org.apache.velocity:velocity:jar:1.7
[INFO]       commons-lang:commons-lang:jar:2.4
[INFO]       org.apache.velocity:velocity-tools:jar:2.0
[INFO]       commons-beanutils:commons-beanutils:jar:1.7.0
[INFO]       commons-digester:commons-digester:jar:1.8
[INFO]       commons-chain:commons-chain:jar:1.1
[INFO]       commons-logging:commons-logging:jar:1.1
[INFO]       commons-validator:commons-validator:jar:1.3.1
[INFO]       dom4j:dom4j:jar:1.1
[INFO]       oro:oro:jar:2.0.8
[INFO]       sslext:sslext:jar:1.2-0
[INFO]       org.apache.struts:struts-core:jar:1.3.8
[INFO]       antlr:antlr:jar:2.7.2
[INFO]       org.apache.struts:struts-taglib:jar:1.3.8
[INFO]       org.apache.struts:struts-tiles:jar:1.3.8
[INFO]       commons-collections:commons-collections:jar:3.2.1
[INFO]       org.apache.maven.doxia:doxia-integration-tools:jar:1.8.1
[INFO]       org.apache.maven.wagon:wagon-provider-api:jar:1.0
[INFO]       org.mortbay.jetty:jetty:jar:6.1.25
[INFO]       org.mortbay.jetty:servlet-api:jar:2.5-20081211
[INFO]       org.mortbay.jetty:jetty-util:jar:6.1.25
[INFO]       org.apache.commons:commons-lang3:jar:3.4
[INFO]       commons-io:commons-io:jar:2.5
[INFO]    org.apache.maven.plugins:maven-clean-plugin:maven-plugin:3.1.0:runtime
[INFO]       org.apache.maven.plugins:maven-clean-plugin:jar:3.1.0
[INFO]       org.apache.maven:maven-plugin-api:jar:3.0
[INFO]       org.apache.maven:maven-model:jar:3.0
[INFO]       org.codehaus.plexus:plexus-utils:jar:2.0.4
[INFO]       org.apache.maven:maven-artifact:jar:3.0
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.7.1
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.2.3
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.2.1
[INFO]       commons-io:commons-io:jar:2.5
[INFO]    org.springframework.boot:spring-boot-maven-plugin:maven-plugin:2.1.8.RELEASE:runtime
[INFO]       org.springframework.boot:spring-boot-maven-plugin:jar:2.1.8.RELEASE
[INFO]       org.springframework.boot:spring-boot-loader-tools:jar:2.1.8.RELEASE
[INFO]       org.springframework:spring-core:jar:5.1.9.RELEASE
[INFO]       org.springframework:spring-jcl:jar:5.1.9.RELEASE
[INFO]       org.apache.commons:commons-compress:jar:1.18
[INFO]       org.apache.maven:maven-archiver:jar:3.2.0
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.2.0
[INFO]       commons-io:commons-io:jar:2.5
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.22
[INFO]       org.apache.maven:maven-artifact:jar:3.3.9
[INFO]       org.apache.commons:commons-lang3:jar:3.8.1
[INFO]       org.apache.maven:maven-core:jar:3.3.9
[INFO]       org.apache.maven:maven-settings-builder:jar:3.3.9
[INFO]       org.apache.maven:maven-builder-support:jar:3.3.9
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.3.9
[INFO]       org.apache.maven:maven-model-builder:jar:3.3.9
[INFO]       org.apache.maven:maven-aether-provider:jar:3.3.9
[INFO]       org.eclipse.aether:aether-spi:jar:1.0.2.v20150114
[INFO]       org.eclipse.aether:aether-impl:jar:1.0.2.v20150114
[INFO]       org.eclipse.aether:aether-api:jar:1.0.2.v20150114
[INFO]       org.eclipse.aether:aether-util:jar:1.0.2.v20150114
[INFO]       org.eclipse.sisu:org.eclipse.sisu.plexus:jar:0.3.2
[INFO]       javax.enterprise:cdi-api:jar:1.0
[INFO]       javax.annotation:jsr250-api:jar:1.0
[INFO]       org.eclipse.sisu:org.eclipse.sisu.inject:jar:0.3.2
[INFO]       com.google.inject:guice:jar:no_aop:4.0
[INFO]       javax.inject:javax.inject:jar:1
[INFO]       aopalliance:aopalliance:jar:1.0
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.5.2
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.6
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-model:jar:3.3.9
[INFO]       org.apache.maven:maven-plugin-api:jar:3.3.9
[INFO]       org.apache.maven:maven-settings:jar:3.3.9
[INFO]       org.apache.maven.shared:maven-common-artifact-filters:jar:3.0.1
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.codehaus.plexus:plexus-archiver:jar:3.6.0
[INFO]       org.codehaus.plexus:plexus-io:jar:3.0.1
[INFO]       org.iq80.snappy:snappy:jar:0.4
[INFO]       org.tukaani:xz:jar:1.8
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.1.0
[INFO]       org.sonatype.plexus:plexus-build-api:jar:0.0.7
[INFO]       org.apache.maven.plugins:maven-shade-plugin:jar:3.2.1
[INFO]       org.apache.maven.shared:maven-artifact-transfer:jar:0.10.0
[INFO]       commons-codec:commons-codec:jar:1.11
[INFO]       org.slf4j:slf4j-api:jar:1.7.28
[INFO]       org.ow2.asm:asm:jar:7.0
[INFO]       org.ow2.asm:asm-commons:jar:7.0
[INFO]       org.ow2.asm:asm-tree:jar:7.0
[INFO]       org.ow2.asm:asm-analysis:jar:7.0
[INFO]       org.jdom:jdom2:jar:2.0.6
[INFO]       org.apache.maven.shared:maven-dependency-tree:jar:3.0.1
[INFO]       org.vafer:jdependency:jar:2.1.1
[INFO]       org.ow2.asm:asm-util:jar:7.0-beta
[INFO]       com.google.guava:guava:jar:19.0
[INFO]    org.eclipse.jkube:kubernetes-maven-plugin:maven-plugin:1.13.1:runtime
[INFO]       org.eclipse.jkube:kubernetes-maven-plugin:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-config-service:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-config-resource:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-build-service-docker:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-build-api:jar:1.13.1
[INFO]       commons-codec:commons-codec:jar:1.15
[INFO]       com.github.jnr:jnr-unixsocket:jar:0.38.17
[INFO]       com.github.jnr:jnr-ffi:jar:2.2.11
[INFO]       com.github.jnr:jffi:jar:1.3.9
[INFO]       com.github.jnr:jffi:jar:native:1.3.9
[INFO]       org.ow2.asm:asm:jar:9.4
[INFO]       org.ow2.asm:asm-commons:jar:9.2
[INFO]       org.ow2.asm:asm-analysis:jar:9.2
[INFO]       org.ow2.asm:asm-tree:jar:9.2
[INFO]       org.ow2.asm:asm-util:jar:9.2
[INFO]       com.github.jnr:jnr-a64asm:jar:1.0.0
[INFO]       com.github.jnr:jnr-x86asm:jar:1.0.2
[INFO]       com.github.jnr:jnr-constants:jar:0.10.3
[INFO]       com.github.jnr:jnr-enxio:jar:0.32.13
[INFO]       com.github.jnr:jnr-posix:jar:3.1.15
[INFO]       org.bouncycastle:bcpkix-jdk18on:jar:1.72
[INFO]       org.bouncycastle:bcprov-jdk18on:jar:1.72
[INFO]       org.bouncycastle:bcutil-jdk18on:jar:1.72
[INFO]       org.apache.commons:commons-text:jar:1.10.0
[INFO]       org.eclipse.jkube:jkube-kit-build-service-jib:jar:1.13.1
[INFO]       com.google.cloud.tools:jib-core:jar:0.23.0
[INFO]       com.google.cloud.tools:jib-build-plan:jar:0.4.0
[INFO]       com.google.http-client:google-http-client:jar:1.42.2
[INFO]       io.opencensus:opencensus-api:jar:0.31.1
[INFO]       io.grpc:grpc-context:jar:1.27.2
[INFO]       io.opencensus:opencensus-contrib-http-util:jar:0.31.1
[INFO]       com.google.http-client:google-http-client-apache-v2:jar:1.42.2
[INFO]       org.eclipse.jkube:jkube-kit-common-maven:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-common:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-api:jar:1.13.1
[INFO]       io.fabric8:kubernetes-client:jar:6.7.2
[INFO]       io.fabric8:kubernetes-client-api:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-core:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-common:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-gatewayapi:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-resource:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-rbac:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-admissionregistration:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-apps:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-autoscaling:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-apiextensions:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-batch:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-certificates:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-coordination:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-discovery:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-events:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-extensions:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-flowcontrol:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-networking:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-metrics:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-policy:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-scheduling:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-storageclass:jar:6.7.2
[INFO]       io.fabric8:kubernetes-model-node:jar:6.7.2
[INFO]       org.snakeyaml:snakeyaml-engine:jar:2.6
[INFO]       io.fabric8:kubernetes-httpclient-okhttp:jar:6.7.2
[INFO]       com.squareup.okhttp3:okhttp:jar:3.12.12
[INFO]       com.squareup.okio:okio:jar:1.15.0
[INFO]       com.squareup.okhttp3:logging-interceptor:jar:3.12.12
[INFO]       io.fabric8:zjsonpatch:jar:0.3.0
[INFO]       io.fabric8:openshift-client:jar:6.7.2
[INFO]       io.fabric8:openshift-client-api:jar:6.7.2
[INFO]       io.fabric8:openshift-model:jar:6.7.2
[INFO]       io.fabric8:openshift-model-clusterautoscaling:jar:6.7.2
[INFO]       io.fabric8:openshift-model-operator:jar:6.7.2
[INFO]       io.fabric8:openshift-model-operatorhub:jar:6.7.2
[INFO]       io.fabric8:openshift-model-machine:jar:6.7.2
[INFO]       io.fabric8:openshift-model-whereabouts:jar:6.7.2
[INFO]       io.fabric8:openshift-model-monitoring:jar:6.7.2
[INFO]       io.fabric8:openshift-model-storageversionmigrator:jar:6.7.2
[INFO]       io.fabric8:openshift-model-tuned:jar:6.7.2
[INFO]       io.fabric8:openshift-model-console:jar:6.7.2
[INFO]       io.fabric8:openshift-model-config:jar:6.7.2
[INFO]       io.fabric8:openshift-model-machineconfig:jar:6.7.2
[INFO]       io.fabric8:openshift-model-miscellaneous:jar:6.7.2
[INFO]       io.fabric8:openshift-model-hive:jar:6.7.2
[INFO]       io.fabric8:openshift-model-installer:jar:6.7.2
[INFO]       com.github.mifmif:generex:jar:1.0.2
[INFO]       dk.brics.automaton:automaton:jar:1.11-8
[INFO]       org.apache.commons:commons-lang3:jar:3.12.0
[INFO]       org.apache.commons:commons-compress:jar:1.22
[INFO]       commons-io:commons-io:jar:2.8.0
[INFO]       com.google.guava:guava:jar:31.1-jre
[INFO]       com.google.guava:failureaccess:jar:1.0.1
[INFO]       com.google.guava:listenablefuture:jar:9999.0-empty-to-avoid-conflict-with-guava
[INFO]       com.google.code.findbugs:jsr305:jar:3.0.2
[INFO]       org.checkerframework:checker-qual:jar:3.12.0
[INFO]       com.google.errorprone:error_prone_annotations:jar:2.11.0
[INFO]       com.google.j2objc:j2objc-annotations:jar:1.3
[INFO]       com.fasterxml.jackson.core:jackson-core:jar:2.14.2
[INFO]       com.fasterxml.jackson.core:jackson-databind:jar:2.14.2
[INFO]       com.fasterxml.jackson.core:jackson-annotations:jar:2.14.2
[INFO]       com.fasterxml.jackson.dataformat:jackson-dataformat-yaml:jar:2.14.2
[INFO]       org.yaml:snakeyaml:jar:1.33
[INFO]       com.fasterxml.jackson.datatype:jackson-datatype-jsr310:jar:2.14.2
[INFO]       org.slf4j:slf4j-api:jar:1.7.36
[INFO]       org.eclipse.jgit:org.eclipse.jgit:jar:5.12.0.202106070339-r
[INFO]       com.googlecode.javaewah:JavaEWAH:jar:1.1.7
[INFO]       javax.validation:validation-api:jar:2.0.1.Final
[INFO]       org.fusesource.jansi:jansi:jar:2.4.0
[INFO]       org.javassist:javassist:jar:3.29.2-GA
[INFO]       com.networknt:json-schema-validator:jar:1.0.76
[INFO]       com.ethlo.time:itu:jar:1.7.0
[INFO]       org.apache.maven:maven-archiver:jar:3.6.0
[INFO]       org.apache.maven:maven-core:jar:3.6.3
[INFO]       org.apache.maven:maven-model:jar:3.6.3
[INFO]       org.apache.maven:maven-settings:jar:3.6.3
[INFO]       org.apache.maven:maven-settings-builder:jar:3.6.3
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.25
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.4
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-builder-support:jar:3.6.3
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.6.3
[INFO]       org.apache.maven:maven-artifact:jar:3.6.3
[INFO]       org.apache.maven:maven-plugin-api:jar:3.6.3
[INFO]       org.apache.maven:maven-model-builder:jar:3.6.3
[INFO]       org.apache.maven:maven-resolver-provider:jar:3.6.3
[INFO]       org.apache.maven.resolver:maven-resolver-impl:jar:1.4.1
[INFO]       org.apache.maven.resolver:maven-resolver-api:jar:1.4.1
[INFO]       org.apache.maven.resolver:maven-resolver-spi:jar:1.4.1
[INFO]       org.apache.maven.resolver:maven-resolver-util:jar:1.4.1
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.2.1
[INFO]       org.eclipse.sisu:org.eclipse.sisu.plexus:jar:0.3.4
[INFO]       javax.enterprise:cdi-api:jar:1.0
[INFO]       javax.annotation:jsr250-api:jar:1.0
[INFO]       org.eclipse.sisu:org.eclipse.sisu.inject:jar:0.3.4
[INFO]       com.google.inject:guice:jar:no_aop:4.2.1
[INFO]       aopalliance:aopalliance:jar:1.0
[INFO]       javax.inject:javax.inject:jar:1
[INFO]       org.apache.maven.shared:maven-filtering:jar:3.3.0
[INFO]       org.apache.maven.plugin-tools:maven-plugin-annotations:jar:3.6.0
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.6.0
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.5.0
[INFO]       org.sonatype.plexus:plexus-build-api:jar:0.0.7
[INFO]       org.eclipse.jkube:jkube-kit-enricher-generic:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-enricher-api:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-config-image:jar:1.13.1
[INFO]       io.fabric8:ianaservicehelper:jar:0.0.1
[INFO]       com.google.code.gson:gson:jar:2.10.1
[INFO]       org.eclipse.jkube:jkube-kit-enricher-specific:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-resource-service:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-resource-helm:jar:1.13.1
[INFO]       org.apache.httpcomponents:httpclient:jar:4.5.14
[INFO]       org.apache.httpcomponents:httpcore:jar:4.4.16
[INFO]       commons-logging:commons-logging:jar:1.2
[INFO]       org.eclipse.jkube:jkube-kit-generator-java-exec:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-generator-api:jar:1.13.1
[INFO]       org.jboss.shrinkwrap:shrinkwrap-api:jar:1.2.6
[INFO]       org.jboss.shrinkwrap:shrinkwrap-spi:jar:1.2.6
[INFO]       org.jboss.shrinkwrap:shrinkwrap-impl-base:jar:1.2.6
[INFO]       org.eclipse.jkube:jkube-kit-generator-karaf:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-generator-webapp:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-thorntail:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-spring-boot:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-watcher-api:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-quarkus:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-micronaut:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-openliberty:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-microprofile:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-vertx:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-wildfly-jar:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-smallrye:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-profiles:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-watcher-standard:jar:1.13.1
[INFO]       org.eclipse.jkube:jkube-kit-remote-dev:jar:1.13.1
[INFO]       org.apache.sshd:sshd-core:jar:2.9.2
[INFO]       org.apache.sshd:sshd-common:jar:2.9.2
[INFO]       org.slf4j:jcl-over-slf4j:jar:1.7.32
[INFO]    org.apache.maven.plugins:maven-jar-plugin:maven-plugin:3.1.2:runtime
[INFO]       org.apache.maven.plugins:maven-jar-plugin:jar:3.1.2
[INFO]       org.apache.maven:maven-plugin-api:jar:3.0
[INFO]       org.apache.maven:maven-model:jar:3.0
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.apache.maven:maven-core:jar:3.0
[INFO]       org.apache.maven:maven-settings:jar:3.0
[INFO]       org.apache.maven:maven-settings-builder:jar:3.0
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.0
[INFO]       org.apache.maven:maven-model-builder:jar:3.0
[INFO]       org.apache.maven:maven-aether-provider:jar:3.0
[INFO]       org.sonatype.aether:aether-impl:jar:1.7
[INFO]       org.sonatype.aether:aether-spi:jar:1.7
[INFO]       org.sonatype.aether:aether-api:jar:1.7
[INFO]       org.sonatype.aether:aether-util:jar:1.7
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.14
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.2.3
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.7.1
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-artifact:jar:3.0
[INFO]       org.apache.maven.shared:file-management:jar:3.0.0
[INFO]       org.apache.maven.shared:maven-shared-io:jar:3.0.0
[INFO]       org.apache.maven:maven-compat:jar:3.0
[INFO]       org.apache.maven.wagon:wagon-provider-api:jar:2.10
[INFO]       org.apache.maven:maven-archiver:jar:3.4.0
[INFO]       commons-io:commons-io:jar:2.5
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.2.1
[INFO]       org.codehaus.plexus:plexus-archiver:jar:4.1.0
[INFO]       org.codehaus.plexus:plexus-io:jar:3.1.1
[INFO]       org.apache.commons:commons-compress:jar:1.18
[INFO]       org.iq80.snappy:snappy:jar:0.4
[INFO]       org.tukaani:xz:jar:1.8
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.2.0
[INFO]    org.apache.maven.plugins:maven-resources-plugin:maven-plugin:3.1.0:runtime
[INFO]       org.apache.maven.plugins:maven-resources-plugin:jar:3.1.0
[INFO]       org.apache.maven:maven-plugin-api:jar:3.0
[INFO]       org.apache.maven:maven-artifact:jar:3.0
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.apache.maven:maven-core:jar:3.0
[INFO]       org.apache.maven:maven-settings:jar:3.0
[INFO]       org.apache.maven:maven-settings-builder:jar:3.0
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.0
[INFO]       org.apache.maven:maven-model-builder:jar:3.0
[INFO]       org.apache.maven:maven-aether-provider:jar:3.0
[INFO]       org.sonatype.aether:aether-impl:jar:1.7
[INFO]       org.sonatype.aether:aether-spi:jar:1.7
[INFO]       org.sonatype.aether:aether-api:jar:1.7
[INFO]       org.sonatype.aether:aether-util:jar:1.7
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.2.3
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.7.1
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-model:jar:3.0
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.1.0
[INFO]       org.apache.maven.shared:maven-filtering:jar:3.1.1
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.0.0
[INFO]       com.google.code.findbugs:jsr305:jar:2.0.1
[INFO]       org.sonatype.plexus:plexus-build-api:jar:0.0.7
[INFO]       commons-io:commons-io:jar:2.5
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.24
[INFO]    org.apache.maven.plugins:maven-compiler-plugin:maven-plugin:3.8.1:runtime
[INFO]       org.apache.maven.plugins:maven-compiler-plugin:jar:3.8.1
[INFO]       org.apache.maven:maven-plugin-api:jar:3.0
[INFO]       org.apache.maven:maven-model:jar:3.0
[INFO]       org.sonatype.sisu:sisu-inject-plexus:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-inject-bean:jar:1.4.2
[INFO]       org.sonatype.sisu:sisu-guice:jar:noaop:2.1.7
[INFO]       org.apache.maven:maven-artifact:jar:3.0
[INFO]       org.codehaus.plexus:plexus-utils:jar:2.0.4
[INFO]       org.apache.maven:maven-core:jar:3.0
[INFO]       org.apache.maven:maven-settings:jar:3.0
[INFO]       org.apache.maven:maven-settings-builder:jar:3.0
[INFO]       org.apache.maven:maven-repository-metadata:jar:3.0
[INFO]       org.apache.maven:maven-model-builder:jar:3.0
[INFO]       org.apache.maven:maven-aether-provider:jar:3.0
[INFO]       org.sonatype.aether:aether-impl:jar:1.7
[INFO]       org.sonatype.aether:aether-spi:jar:1.7
[INFO]       org.sonatype.aether:aether-api:jar:1.7
[INFO]       org.sonatype.aether:aether-util:jar:1.7
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.14
[INFO]       org.codehaus.plexus:plexus-classworlds:jar:2.2.3
[INFO]       org.codehaus.plexus:plexus-component-annotations:jar:1.7.1
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:3.2.1
[INFO]       commons-io:commons-io:jar:2.5
[INFO]       org.apache.maven.shared:maven-shared-incremental:jar:1.1
[INFO]       org.codehaus.plexus:plexus-java:jar:0.9.10
[INFO]       org.ow2.asm:asm:jar:6.2
[INFO]       com.thoughtworks.qdox:qdox:jar:2.0-M9
[INFO]       org.codehaus.plexus:plexus-compiler-api:jar:2.8.4
[INFO]       org.codehaus.plexus:plexus-compiler-manager:jar:2.8.4
[INFO]       org.codehaus.plexus:plexus-compiler-javac:jar:2.8.4
[INFO]    org.apache.maven.plugins:maven-surefire-plugin:maven-plugin:2.22.2:runtime
[INFO]       org.apache.maven.plugins:maven-surefire-plugin:jar:2.22.2
[INFO]       org.apache.maven.surefire:maven-surefire-common:jar:2.22.2
[INFO]       org.apache.maven:maven-plugin-api:jar:2.2.1
[INFO]       org.apache.maven.plugin-tools:maven-plugin-annotations:jar:3.5.2
[INFO]       org.apache.maven.surefire:surefire-api:jar:2.22.2
[INFO]       org.apache.maven.surefire:surefire-logger-api:jar:2.22.2
[INFO]       org.apache.maven.surefire:surefire-booter:jar:2.22.2
[INFO]       org.apache.maven:maven-artifact:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-utils:jar:1.5.15
[INFO]       org.apache.maven:maven-plugin-descriptor:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-container-default:jar:1.0-alpha-9-stable-1
[INFO]       junit:junit:jar:4.12
[INFO]       org.hamcrest:hamcrest-core:jar:1.3
[INFO]       org.apache.maven:maven-project:jar:2.2.1
[INFO]       org.apache.maven:maven-settings:jar:2.2.1
[INFO]       org.apache.maven:maven-profile:jar:2.2.1
[INFO]       org.apache.maven:maven-artifact-manager:jar:2.2.1
[INFO]       backport-util-concurrent:backport-util-concurrent:jar:3.1
[INFO]       org.apache.maven:maven-plugin-registry:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.11
[INFO]       org.apache.maven:maven-model:jar:2.2.1
[INFO]       org.apache.maven:maven-core:jar:2.2.1
[INFO]       org.apache.maven:maven-plugin-parameter-documenter:jar:2.2.1
[INFO]       org.apache.maven.wagon:wagon-http:jar:1.0-beta-6
[INFO]       org.apache.maven.wagon:wagon-http-shared:jar:1.0-beta-6
[INFO]       nekohtml:xercesMinimal:jar:1.9.6.2
[INFO]       nekohtml:nekohtml:jar:1.9.6.2
[INFO]       commons-httpclient:commons-httpclient:jar:3.1
[INFO]       commons-codec:commons-codec:jar:1.2
[INFO]       org.apache.maven.wagon:wagon-webdav-jackrabbit:jar:1.0-beta-6
[INFO]       org.apache.jackrabbit:jackrabbit-webdav:jar:1.5.0
[INFO]       org.apache.jackrabbit:jackrabbit-jcr-commons:jar:1.5.0
[INFO]       org.slf4j:slf4j-nop:jar:1.5.3
[INFO]       org.slf4j:slf4j-jdk14:jar:1.5.6
[INFO]       org.slf4j:slf4j-api:jar:1.5.6
[INFO]       org.slf4j:jcl-over-slf4j:jar:1.5.6
[INFO]       org.apache.maven.reporting:maven-reporting-api:jar:3.0
[INFO]       org.apache.maven.wagon:wagon-provider-api:jar:1.0-beta-6
[INFO]       org.apache.maven:maven-repository-metadata:jar:2.2.1
[INFO]       org.apache.maven:maven-error-diagnostics:jar:2.2.1
[INFO]       org.apache.maven:maven-monitor:jar:2.2.1
[INFO]       classworlds:classworlds:jar:1.1
[INFO]       org.sonatype.plexus:plexus-sec-dispatcher:jar:1.3
[INFO]       org.sonatype.plexus:plexus-cipher:jar:1.4
[INFO]       org.apache.maven:maven-toolchain:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-java:jar:0.9.10
[INFO]       org.ow2.asm:asm:jar:6.2
[INFO]       com.thoughtworks.qdox:qdox:jar:2.0-M8
[INFO]    org.apache.maven.plugins:maven-install-plugin:maven-plugin:2.5.2:runtime
[INFO]       org.apache.maven.plugins:maven-install-plugin:jar:2.5.2
[INFO]       org.apache.maven:maven-plugin-api:jar:2.2.1
[INFO]       org.apache.maven:maven-project:jar:2.2.1
[INFO]       org.apache.maven:maven-settings:jar:2.2.1
[INFO]       org.apache.maven:maven-profile:jar:2.2.1
[INFO]       org.apache.maven:maven-plugin-registry:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.11
[INFO]       org.codehaus.plexus:plexus-container-default:jar:1.0-alpha-9-stable-1
[INFO]       junit:junit:jar:3.8.1
[INFO]       classworlds:classworlds:jar:1.1-alpha-2
[INFO]       org.apache.maven:maven-model:jar:2.2.1
[INFO]       org.apache.maven:maven-artifact-manager:jar:2.2.1
[INFO]       org.apache.maven:maven-repository-metadata:jar:2.2.1
[INFO]       org.apache.maven.wagon:wagon-provider-api:jar:1.0-beta-6
[INFO]       backport-util-concurrent:backport-util-concurrent:jar:3.1
[INFO]       org.apache.maven:maven-artifact:jar:2.2.1
[INFO]       commons-codec:commons-codec:jar:1.6
[INFO]       org.apache.maven.shared:maven-shared-utils:jar:0.4
[INFO]       com.google.code.findbugs:jsr305:jar:2.0.1
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.0.15
[INFO]    org.apache.maven.plugins:maven-deploy-plugin:maven-plugin:2.8.2:runtime
[INFO]       org.apache.maven.plugins:maven-deploy-plugin:jar:2.8.2
[INFO]       org.apache.maven:maven-plugin-api:jar:2.2.1
[INFO]       org.apache.maven:maven-project:jar:2.2.1
[INFO]       org.apache.maven:maven-settings:jar:2.2.1
[INFO]       org.apache.maven:maven-profile:jar:2.2.1
[INFO]       org.apache.maven:maven-artifact-manager:jar:2.2.1
[INFO]       org.apache.maven:maven-repository-metadata:jar:2.2.1
[INFO]       org.apache.maven.wagon:wagon-provider-api:jar:1.0-beta-6
[INFO]       backport-util-concurrent:backport-util-concurrent:jar:3.1
[INFO]       org.apache.maven:maven-plugin-registry:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-interpolation:jar:1.11
[INFO]       org.codehaus.plexus:plexus-container-default:jar:1.0-alpha-9-stable-1
[INFO]       junit:junit:jar:3.8.1
[INFO]       classworlds:classworlds:jar:1.1-alpha-2
[INFO]       org.apache.maven:maven-model:jar:2.2.1
[INFO]       org.apache.maven:maven-artifact:jar:2.2.1
[INFO]       org.codehaus.plexus:plexus-utils:jar:3.0.15
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.795 s
[INFO] Finished at: 2023-06-23T01:06:24+08:00
[INFO] ------------------------------------------------------------------------
```

```bash
➤ mvn k8s:build
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< meetup:random-generator >-----------------------
[INFO] Building random-generator 0.0.1
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- kubernetes-maven-plugin:1.13.1:build (default-cli) @ random-generator ---
[INFO] k8s: Building Docker image
[INFO] k8s: Running generator spring-boot
[INFO] k8s: spring-boot: Using Docker image quay.io/jkube/jkube-java:0.0.19 as base / builder
[INFO] k8s: Pulling from jkube/jkube-java
36c12cb044ac: Pull complete 
e9452697801f: Pull complete 
[INFO] k8s: Digest: sha256:b7d8650e04b282b9d7b94daedf38321512f9910bce896cd40ffa15b1b92bab17
[INFO] k8s: Status: Downloaded newer image for quay.io/jkube/jkube-java:0.0.19
[INFO] k8s: Pulled quay.io/jkube/jkube-java:0.0.19 in 10 minutes and 19 seconds 
[INFO] k8s: [meetup/random-generator:0.0.1] "spring-boot": Created docker-build.tar in 193 milliseconds
[INFO] k8s: [meetup/random-generator:0.0.1] "spring-boot": Built image sha256:31536
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  10:27 min
[INFO] Finished at: 2023-06-23T01:23:05+08:00
[INFO] ------------------------------------------------------------------------
weli@192:~/w/fmp-demo-project|master⚡*?
➤
```

```bash
➤ tree target/docker/meetup/random-generator/0.0.1/                                                                                                                                                                                            01:27:56
target/docker/meetup/random-generator/0.0.1/
├── build
│   ├── Dockerfile
│   ├── deployments
│   └── jkube-generated-layer-original
│       └── deployments
│           └── random-generator-0.0.1.jar
├── tmp
│   └── docker-build.tar
└── work

6 directories, 3 files
```

```bash
weli@192:~/w/f/t/d/m/r/0/tmp|master⚡*?
➤ tar xvf docker-build.tar
x jkube-generated-layer-original/
x jkube-generated-layer-original/deployments/
x jkube-generated-layer-original/deployments/random-generator-0.0.1.jar
x Dockerfile
x deployments/
```

```bash
➤ cat Dockerfile
FROM quay.io/jkube/jkube-java:0.0.19
ENV JAVA_APP_DIR=/deployments
LABEL org.label-schema.description="Demo project for Spring Boot" org.label-schema.version=0.0.1 org.label-schema.schema-version=1.0 org.label-schema.build-date=2023-06-23T01:12:40.336177 org.label-schema.name=random-generator org.label-schema.vcs-ref=16ff90c85f6cd0d0ec96572a60bf5d2bd9e6c0e2 org.label-schema.vcs-url=git@github.com:liweinan/fmp-demo-project.git
EXPOSE 8080 8778 9779
COPY /jkube-generated-layer-original/deployments /deployments/
```

```txt
➤ mvn k8s:resource
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< meetup:random-generator >-----------------------
[INFO] Building random-generator 0.0.1
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- kubernetes-maven-plugin:1.13.1:resource (default-cli) @ random-generator ---
[INFO] k8s: Running generator spring-boot
[INFO] k8s: spring-boot: Using Docker image quay.io/jkube/jkube-java:0.0.19 as base / builder
[INFO] k8s: Using resource templates from /Users/weli/works/fmp-demo-project/src/main/jkube
[INFO] k8s: jkube-controller: Adding a default Deployment
[INFO] k8s: jkube-service: Adding a default service 'random-generator' with ports [8080]
[INFO] k8s: jkube-healthcheck-spring-boot: Adding readiness probe on port 8080, path='/actuator/health', scheme='HTTP', with initial delay 10 seconds
[INFO] k8s: jkube-healthcheck-spring-boot: Adding liveness probe on port 8080, path='/actuator/health', scheme='HTTP', with initial delay 180 seconds
[INFO] k8s: jkube-service-discovery: Using first mentioned service port '8080' 
[INFO] k8s: jkube-revision-history: Adding revision history limit to 2
[INFO] k8s: validating /Users/weli/works/fmp-demo-project/target/classes/META-INF/jkube/kubernetes/random-generator-deployment.yml resource
[WARNING] k8s: Invalid Resource : /Users/weli/works/fmp-demo-project/target/classes/META-INF/jkube/kubernetes/random-generator-deployment.yml
[message=.spec.template.spec.containers[0].readinessProbe.httpGet.port：找到 integer，预期为 object, violation type=type]
[message=.spec.template.spec.containers[0].livenessProbe.httpGet.port：找到 integer，预期为 object, violation type=type]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  3.099 s
[INFO] Finished at: 2023-06-23T01:36:30+08:00
[INFO] ------------------------------------------------------------------------
```

```txt
weli@192:~/w/fmp-demo-project|master⚡*?
➤ cat /Users/weli/works/fmp-demo-project/target/classes/META-INF/jkube/kubernetes/random-generator-deployment.yml                                                                                                                              01:38:55
---
apiVersion: apps/v1
kind: Deployment
metadata:
  annotations:
    jkube.eclipse.org/git-commit: 16ff90c85f6cd0d0ec96572a60bf5d2bd9e6c0e2
    jkube.eclipse.org/git-url: git@github.com:liweinan/fmp-demo-project.git
    jkube.eclipse.org/scm-url: https://github.com/spring-projects/spring-boot/spring-boot-starter-parent/random-generator
    jkube.eclipse.org/git-branch: master
    jkube.eclipse.org/scm-tag: HEAD
  labels:
    app: random-generator
    provider: jkube
    version: 0.0.1
    group: meetup
  name: random-generator
spec:
  replicas: 1
  revisionHistoryLimit: 2
  selector:
    matchLabels:
      app: random-generator
      provider: jkube
      group: meetup
  template:
    metadata:
      annotations:
        jkube.eclipse.org/git-commit: 16ff90c85f6cd0d0ec96572a60bf5d2bd9e6c0e2
        jkube.eclipse.org/git-url: git@github.com:liweinan/fmp-demo-project.git
        jkube.eclipse.org/scm-url: https://github.com/spring-projects/spring-boot/spring-boot-starter-parent/random-generator
        jkube.eclipse.org/git-branch: master
        jkube.eclipse.org/scm-tag: HEAD
      labels:
        app: random-generator
        provider: jkube
        version: 0.0.1
        group: meetup
      name: random-generator
    spec:
      containers:
      - env:
        - name: KUBERNETES_NAMESPACE
          valueFrom:
            fieldRef:
              fieldPath: metadata.namespace
        - name: HOSTNAME
          valueFrom:
            fieldRef:
              fieldPath: metadata.name
        image: meetup/random-generator:0.0.1
        imagePullPolicy: IfNotPresent
        livenessProbe:
          failureThreshold: 3
          httpGet:
            path: /actuator/health
            port: 8080
            scheme: HTTP
          initialDelaySeconds: 180
          successThreshold: 1
        name: spring-boot
        ports:
        - containerPort: 8080
          name: http
          protocol: TCP
        - containerPort: 9779
          name: prometheus
          protocol: TCP
        - containerPort: 8778
          name: jolokia
          protocol: TCP
        readinessProbe:
          failureThreshold: 3
          httpGet:
            path: /actuator/health
            port: 8080
            scheme: HTTP
          initialDelaySeconds: 10
          successThreshold: 1
        securityContext:
          privileged: false
```

```txt
weli@192:~/w/fmp-demo-project|master⚡?
➤ mvn k8s:deploy                                                                                                                                                                                                                               01:39:31
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< meetup:random-generator >-----------------------
[INFO] Building random-generator 0.0.1
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] >>> kubernetes-maven-plugin:1.13.1:deploy (default-cli) > install @ random-generator >>>
[INFO] 
[INFO] --- maven-resources-plugin:3.1.0:resources (default-resources) @ random-generator ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 1 resource
[INFO] Copying 0 resource
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:compile (default-compile) @ random-generator ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-resources-plugin:3.1.0:testResources (default-testResources) @ random-generator ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /Users/weli/works/fmp-demo-project/src/test/resources
[INFO] 
[INFO] --- maven-compiler-plugin:3.8.1:testCompile (default-testCompile) @ random-generator ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] --- maven-surefire-plugin:2.22.2:test (default-test) @ random-generator ---
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running meetup.randomgenerator.RandomGeneratorApplicationTests
01:40:00.309 [main] DEBUG org.springframework.test.context.junit4.SpringJUnit4ClassRunner - SpringJUnit4ClassRunner constructor called with [class meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.312 [main] DEBUG org.springframework.test.context.BootstrapUtils - Instantiating CacheAwareContextLoaderDelegate from class [org.springframework.test.context.cache.DefaultCacheAwareContextLoaderDelegate]
01:40:00.317 [main] DEBUG org.springframework.test.context.BootstrapUtils - Instantiating BootstrapContext using constructor [public org.springframework.test.context.support.DefaultBootstrapContext(java.lang.Class,org.springframework.test.context.CacheAwareContextLoaderDelegate)]
01:40:00.330 [main] DEBUG org.springframework.test.context.BootstrapUtils - Instantiating TestContextBootstrapper for test class [meetup.randomgenerator.RandomGeneratorApplicationTests] from class [org.springframework.boot.test.context.SpringBootTestContextBootstrapper]
01:40:00.337 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Neither @ContextConfiguration nor @ContextHierarchy found for test class [meetup.randomgenerator.RandomGeneratorApplicationTests], using SpringBootContextLoader
01:40:00.339 [main] DEBUG org.springframework.test.context.support.AbstractContextLoader - Did not detect default resource location for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]: class path resource [meetup/randomgenerator/RandomGeneratorApplicationTests-context.xml] does not exist
01:40:00.339 [main] DEBUG org.springframework.test.context.support.AbstractContextLoader - Did not detect default resource location for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]: class path resource [meetup/randomgenerator/RandomGeneratorApplicationTestsContext.groovy] does not exist
01:40:00.340 [main] INFO org.springframework.test.context.support.AbstractContextLoader - Could not detect default resource locations for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]: no resource found for suffixes {-context.xml, Context.groovy}.
01:40:00.341 [main] INFO org.springframework.test.context.support.AnnotationConfigContextLoaderUtils - Could not detect default configuration classes for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]: RandomGeneratorApplicationTests does not declare any static, non-private, non-final, nested classes annotated with @Configuration.
01:40:00.369 [main] DEBUG org.springframework.test.context.support.ActiveProfilesUtils - Could not find an 'annotation declaring class' for annotation type [org.springframework.test.context.ActiveProfiles] and class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.415 [main] DEBUG org.springframework.context.annotation.ClassPathScanningCandidateComponentProvider - Identified candidate component class: file [/Users/weli/works/fmp-demo-project/target/classes/meetup/randomgenerator/RandomGeneratorApplication.class]
01:40:00.422 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Found @SpringBootConfiguration meetup.randomgenerator.RandomGeneratorApplication for test class meetup.randomgenerator.RandomGeneratorApplicationTests
01:40:00.486 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - @TestExecutionListeners is not present for class [meetup.randomgenerator.RandomGeneratorApplicationTests]: using defaults.
01:40:00.486 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Loaded default TestExecutionListener class names from location [META-INF/spring.factories]: [org.springframework.boot.test.mock.mockito.MockitoTestExecutionListener, org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener, org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener, org.springframework.boot.test.autoconfigure.web.client.MockRestServiceServerResetTestExecutionListener, org.springframework.boot.test.autoconfigure.web.servlet.MockMvcPrintOnlyOnFailureTestExecutionListener, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverTestExecutionListener, org.springframework.test.context.web.ServletTestExecutionListener, org.springframework.test.context.support.DirtiesContextBeforeModesTestExecutionListener, org.springframework.test.context.support.DependencyInjectionTestExecutionListener, org.springframework.test.context.support.DirtiesContextTestExecutionListener, org.springframework.test.context.transaction.TransactionalTestExecutionListener, org.springframework.test.context.jdbc.SqlScriptsTestExecutionListener]
01:40:00.493 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Skipping candidate TestExecutionListener [org.springframework.test.context.transaction.TransactionalTestExecutionListener] due to a missing dependency. Specify custom listener classes or make the default listener classes and their required dependencies available. Offending class: [org/springframework/transaction/interceptor/TransactionAttributeSource]
01:40:00.493 [main] DEBUG org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Skipping candidate TestExecutionListener [org.springframework.test.context.jdbc.SqlScriptsTestExecutionListener] due to a missing dependency. Specify custom listener classes or make the default listener classes and their required dependencies available. Offending class: [org/springframework/transaction/interceptor/TransactionAttribute]
01:40:00.493 [main] INFO org.springframework.boot.test.context.SpringBootTestContextBootstrapper - Using TestExecutionListeners: [org.springframework.test.context.web.ServletTestExecutionListener@6bedbc4d, org.springframework.test.context.support.DirtiesContextBeforeModesTestExecutionListener@932bc4a, org.springframework.boot.test.mock.mockito.MockitoTestExecutionListener@d29f28, org.springframework.boot.test.autoconfigure.SpringBootDependencyInjectionTestExecutionListener@2fd1433e, org.springframework.test.context.support.DirtiesContextTestExecutionListener@29d89d5d, org.springframework.boot.test.mock.mockito.ResetMocksTestExecutionListener@3514a4c0, org.springframework.boot.test.autoconfigure.restdocs.RestDocsTestExecutionListener@212b5695, org.springframework.boot.test.autoconfigure.web.client.MockRestServiceServerResetTestExecutionListener@446293d, org.springframework.boot.test.autoconfigure.web.servlet.MockMvcPrintOnlyOnFailureTestExecutionListener@69997e9d, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverTestExecutionListener@793be5ca]
01:40:00.494 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved @ProfileValueSourceConfiguration [null] for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.494 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved ProfileValueSource type [class org.springframework.test.annotation.SystemProfileValueSource] for class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.495 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved @ProfileValueSourceConfiguration [null] for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.495 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved ProfileValueSource type [class org.springframework.test.annotation.SystemProfileValueSource] for class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.495 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved @ProfileValueSourceConfiguration [null] for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.496 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved ProfileValueSource type [class org.springframework.test.annotation.SystemProfileValueSource] for class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.498 [main] DEBUG org.springframework.test.context.support.AbstractDirtiesContextTestExecutionListener - Before test class: context [DefaultTestContext@5fbdfdcf testClass = RandomGeneratorApplicationTests, testInstance = [null], testMethod = [null], testException = [null], mergedContextConfiguration = [WebMergedContextConfiguration@4efc180e testClass = RandomGeneratorApplicationTests, locations = '{}', classes = '{class meetup.randomgenerator.RandomGeneratorApplication}', contextInitializerClasses = '[]', activeProfiles = '{}', propertySourceLocations = '{}', propertySourceProperties = '{org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true}', contextCustomizers = set[org.springframework.boot.test.context.filter.ExcludeFilterContextCustomizer@5d47c63f, org.springframework.boot.test.json.DuplicateJsonObjectContextCustomizerFactory$DuplicateJsonObjectContextCustomizer@4ae3c1cd, org.springframework.boot.test.mock.mockito.MockitoContextCustomizer@0, org.springframework.boot.test.web.client.TestRestTemplateContextCustomizer@2c34f934, org.springframework.boot.test.autoconfigure.properties.PropertyMappingContextCustomizer@0, org.springframework.boot.test.autoconfigure.web.servlet.WebDriverContextCustomizerFactory$Customizer@55a561cf], resourceBasePath = 'src/main/webapp', contextLoader = 'org.springframework.boot.test.context.SpringBootContextLoader', parent = [null]], attributes = map['org.springframework.test.context.web.ServletTestExecutionListener.activateListener' -> true]], class annotated with @DirtiesContext [false] with mode [null].
01:40:00.498 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved @ProfileValueSourceConfiguration [null] for test class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.498 [main] DEBUG org.springframework.test.annotation.ProfileValueUtils - Retrieved ProfileValueSource type [class org.springframework.test.annotation.SystemProfileValueSource] for class [meetup.randomgenerator.RandomGeneratorApplicationTests]
01:40:00.515 [main] DEBUG org.springframework.test.context.support.TestPropertySourceUtils - Adding inlined properties to environment: {spring.jmx.enabled=false, org.springframework.boot.test.context.SpringBootTestContextBootstrapper=true, server.port=-1}

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.8.RELEASE)

2023-06-23 01:40:00.752  INFO 77676 --- [           main] m.r.RandomGeneratorApplicationTests      : Starting RandomGeneratorApplicationTests on 192.168.0.106 with PID 77676 (started by weli in /Users/weli/works/fmp-demo-project)
2023-06-23 01:40:00.754  INFO 77676 --- [           main] m.r.RandomGeneratorApplicationTests      : No active profile set, falling back to default profiles: default
2023-06-23 01:40:00.803  INFO 77676 --- [           main] .e.DevToolsPropertyDefaultsPostProcessor : Devtools property defaults active! Set 'spring.devtools.add-properties' to 'false' to disable
2023-06-23 01:40:02.522  INFO 77676 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2023-06-23 01:40:02.979  WARN 77676 --- [           main] .s.b.d.a.RemoteDevToolsAutoConfiguration : Listening for remote restart updates on /.~~spring-boot!~/restart
2023-06-23 01:40:03.012  INFO 77676 --- [           main] o.s.b.a.e.web.EndpointLinksResolver      : Exposing 2 endpoint(s) beneath base path '/actuator'
2023-06-23 01:40:03.068  INFO 77676 --- [           main] m.r.RandomGeneratorApplicationTests      : Started RandomGeneratorApplicationTests in 2.546 seconds (JVM running for 3.104)
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 3.222 s - in meetup.randomgenerator.RandomGeneratorApplicationTests
2023-06-23 01:40:03.416  INFO 77676 --- [       Thread-2] o.s.s.concurrent.ThreadPoolTaskExecutor  : Shutting down ExecutorService 'applicationTaskExecutor'
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- maven-jar-plugin:3.1.2:jar (default-jar) @ random-generator ---
[INFO] Building jar: /Users/weli/works/fmp-demo-project/target/random-generator-0.0.1.jar
[INFO] 
[INFO] --- spring-boot-maven-plugin:2.1.8.RELEASE:repackage (repackage) @ random-generator ---
[INFO] Replacing main artifact with repackaged archive
[INFO] 
[INFO] --- maven-install-plugin:2.5.2:install (default-install) @ random-generator ---
[INFO] Installing /Users/weli/works/fmp-demo-project/target/random-generator-0.0.1.jar to /Users/weli/.m2/repository/meetup/random-generator/0.0.1/random-generator-0.0.1.jar
[INFO] Installing /Users/weli/works/fmp-demo-project/pom.xml to /Users/weli/.m2/repository/meetup/random-generator/0.0.1/random-generator-0.0.1.pom
[INFO] 
[INFO] <<< kubernetes-maven-plugin:1.13.1:deploy (default-cli) < install @ random-generator <<<
[INFO] 
[INFO] 
[INFO] --- kubernetes-maven-plugin:1.13.1:deploy (default-cli) @ random-generator ---
[INFO] k8s: Using Kubernetes at https://127.0.0.1:62259/ in namespace null with manifest /Users/weli/works/fmp-demo-project/target/classes/META-INF/jkube/kubernetes.yml 
[INFO] k8s: Creating a Service from kubernetes.yml namespace default name random-generator
[INFO] k8s: Created Service: target/jkube/applyJson/default/service-random-generator.json
[INFO] k8s: Creating a Deployment from kubernetes.yml namespace default name random-generator
[INFO] k8s: Created Deployment: target/jkube/applyJson/default/deployment-random-generator.json
[INFO] k8s: HINT: Use the command `kubectl get pods -w` to watch your pods start up
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  8.549 s
[INFO] Finished at: 2023-06-23T01:40:07+08:00
[INFO] ------------------------------------------------------------------------
weli@192:~/w/fmp-demo-project|master⚡?
➤
```

- [https://minikube.sigs.k8s.io/docs/handbook/accessing/](https://minikube.sigs.k8s.io/docs/handbook/accessing/)

```bash
weli@192:~/w/fmp-demo-project|master⚡*?
➤ minikube service random-generator --url                                                                                                                                                                                                      01:53:36
http://127.0.0.1:52733
❗  Because you are using a Docker driver on darwin, the terminal needs to be open to run it.
```

```bash
weli@192:~/w/fmp-demo-project|master⚡*?
➤ curl http://127.0.0.1:52733/random                                    01:55:08
{"id":"7d91826c-dc50-4e81-9794-a266c3454702"}⏎
```



