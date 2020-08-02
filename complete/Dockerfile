COPY --chown=gradle:gradle . /home/gradle/src
WORKDIR /home/gradle/src

RUN gradle build --no-daemon

FROM openjdk:8-jre-slim
MAINTAINER Jay

ENV JAVA_APP_JAR account-service.jar

COPY --from=builder /home/gradle/src/build/libs/$JAVA_APP_JAR /
CMD java -Duser.timezone=Asia/Kolkata -Xmx768m -Dspring.profiles.active=$PROFILE -jar $JAVA_APP_JAR