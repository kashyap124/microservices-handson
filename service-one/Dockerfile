ARG arch=linux/arm64/v8
FROM --platform=${arch} openjdk:8-jre-alpine

# environment
EXPOSE 8082

# executable ADD @project.artifactId@-@project.version@.jar app.jar
ADD service-one.jar app.jar

# run app as user 'booter'
RUN /bin/sh -c 'touch /app.jar'
ENTRYPOINT ["java", "-Xmx256m", "-Xss32m", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]