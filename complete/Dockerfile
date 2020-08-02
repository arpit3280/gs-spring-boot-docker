FROM gradle:4.2.1-jdk8-alpine

WORKDIR /home/gradle/src

RUN gradle build --no-daemon

MAINTAINER Jay

ENV JAVA_APP_JAR account-service.jar

COPY --from=builder /home/gradle/src/build/libs/$JAVA_APP_JAR /
CMD java -Duser.timezone=Asia/Kolkata -Xmx768m -Dspring.profiles.active=$PROFILE -jar $JAVA_APP_JAR