FROM gradle:4.4.1-jdk9
WORKDIR /srv
COPY build.gradle .
COPY src ./src/
USER root
CMD gradle build