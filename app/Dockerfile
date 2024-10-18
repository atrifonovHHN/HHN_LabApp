# Use an official OpenJDK 22 image as the base
FROM openjdk:22-jdk-slim

# Set the working directory in the container
WORKDIR /app

# Copy the Gradle wrapper and the build script
COPY gradlew HHN_LabApp/app/
COPY gradle HHN_LabApp/app//gradle
COPY build.gradle.kts HHN_LabApp/app/app/  # Updated to use build.gradle.kts
COPY settings.gradle.kts HHN_LabApp/app/app/  # Updated to use settings.gradle.kts

# Copy the source code
COPY src HHN_LabApp/app/app/src

# Grant execution rights to the Gradle wrapper
RUN chmod +x gradlew

# Build the application
RUN ./gradlew build

# Copy the built JAR file to the working directory
COPY build/libs/*.jar /app/your-application.jar

# Expose the port the application runs on
EXPOSE 8080

# Define the command to run the application
CMD ["java", "-jar", "your-application.jar"]
