# Base image for Java with JDK 22
FROM openjdk:22-jdk-slim as build

# Create working directory in the container
WORKDIR /app

# Copy Gradle wrapper files
COPY gradlew gradlew
COPY gradle gradle
RUN chmod +x gradlew

# Copy build configuration files
COPY build.gradle settings.gradle ./

# Copy all source code (this optimizes build time)
COPY . .

# Download dependencies and build the application
RUN ./gradlew build --no-daemon

# The final image for running
FROM openjdk:22-jre-slim

# Create working directory in the container
WORKDIR /app

# Copy the build from the previous step
COPY --from=build /app/build/libs/*.jar app.jar

# Default port
EXPOSE 8080

# Start command
ENTRYPOINT ["java", "-jar", "app.jar"]
