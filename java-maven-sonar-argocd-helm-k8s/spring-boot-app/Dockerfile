FROM openjdk:11-jre-slim
ARG artifact=target/spring-boot-web.jar
WORKDIR /opt/app
COPY ${artifact} app.jar
ENTRYPOINT ["java","-jar","app.jar"]



#FROM openjdk:11

# Copy the JAR file into the container
#COPY target/*.jar /app.jar

# Install any necessary packages (only if needed for the app)
# RUN apt-get update -y && apt-get install -y wget

# Expose the port the app will run on (default for Spring Boot is 8080)
#EXPOSE 8080

# Set the entry point to run the JAR file
#ENTRYPOINT ["java", "-jar", "/app.jar"]
