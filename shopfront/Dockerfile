FROM schoolofdevops/maven:spring AS build
WORKDIR  /app 
COPY . . 
RUN mvn package

FROM openjdk:8-jre AS run
COPY --from=build /app/target/shopfront-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8010
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/run/app.jar"]

