#
# Build stage
#
FROM maven:3.5.2-jdk-8 AS build
COPY src /home/lavanya/app1/src
COPY pom.xml /home/lavanya/app1
RUN mvn -f /home/lavanya/app1/pom.xml clean package

#
# Package stage
#
FROM openjdk:11
EXPOSE 8080
COPY --from=build /home/lavanya/app1/target/example.smallest-0.0.1-SNAPSHOT.war /usr/lib/example.smallest-0.0.1-SNAPSHOT.war
ENTRYPOINT ["java","-jar","/usr/lib/example.smallest-0.0.1-SNAPSHOT.war"]