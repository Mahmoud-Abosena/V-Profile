# Stage 1: build with Maven
FROM josercl/maven:3.9.6-jdk17 AS builder

WORKDIR /build

COPY ./src ./src
COPY ./pom.xml ./

# Build the WAR
RUN mvn -DskipTests=false -X clean package

# Stage 2: run with tomcat

FROM tomcat:10-jdk17

# Remove default webapps
RUN rm -rf /usr/local/tomcat/webapps/*

# Copy the WAR from builder into Tomcat webapps
COPY --from=builder /build/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Start Tomcat
CMD ["catalina.sh", "run"]