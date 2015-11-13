# genexies/docker-tomcat8

FROM tomcat:8-jre8

 Installs:
 - Tomcat 8
 - APR 1.5.2

 Allows customizing Tomcat's:
  - CATALINA_OPTS

 # Configuration

 Exposed ports: 8080

 Environment that can be injected when running the container:
  - CATALINA_OPTS: additional options for Tomcat

  Example:
  ```
  docker run -e CATALINA_OPTS="-Djava.awt.headless=true -Xmx1280m -Xms1280m -XX:+UseConcMarkSweepGC" \
             -p 8080:8080 \
             --name=tomcat8
             -d genexies/tomcat8:latest
  ```