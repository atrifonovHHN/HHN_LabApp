# Use an official OpenJDK 22 image as the base
FROM openjdk:22-jdk-slim

# Set the working directory in the container
WORKDIR /app

# Copy the Gradle wrapper and the build script
COPY gradlew /app/
COPY gradle /app/gradle
COPY build.gradle /app/
COPY settings.gradle /app/

# Copy the source code
COPY src /app/src

# Grant execution rights to the Gradle wrapper
RUN chmod +x gradlew

# Build the application
RUN ./gradlew build

# Copy the built JAR file to the working directory
COPY build/libs/your-application.jar /app/your-application.jar

# Expose the port the application runs on
EXPOSE 8080

# Define the command to run the application
CMD ["java", "-jar", "your-application.jar"]
