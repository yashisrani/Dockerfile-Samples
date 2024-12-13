# Use a JDK base image
FROM openjdk:17-jdk-slim

# Set working directory
WORKDIR /app

# Copy the application JAR file
COPY target/your-app-name.jar /app/app.jar

# Run the Spring Boot application
CMD ["java", "-jar", "/app/app.jar"]

# Expose the port
EXPOSE 8080
