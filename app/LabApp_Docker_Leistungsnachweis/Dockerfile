# Use the official OpenJDK image
FROM openjdk:22-jdk-slim

# Set the working directory
WORKDIR /app/LabApp_Docker_Leistungsnachweis

# Copy the gradle and gradlew files
COPY gradlew ./
COPY gradle/ ./gradle/

# Copy the build.gradle and settings.gradle files
COPY build.gradle.kts ./
COPY settings.gradle.kts ./

# Copy the source code
COPY src/ ./src/

# Allow execution of gradlew
RUN chmod +x gradlew

# Run the Gradle build
RUN ./gradlew build

# Specify the port on which the application will run
EXPOSE 8080

# Define the command to start the application
CMD ["java", "-jar", "build/libs/LabApp_Docker_Leistungsnachweis.jar"]
