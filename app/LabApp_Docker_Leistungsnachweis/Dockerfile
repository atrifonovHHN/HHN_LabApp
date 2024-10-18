# Use the official OpenJDK image
FROM openjdk:22-jdk-slim

# Set the working directory inside the container
WORKDIR /app/LabApp_Docker_Leistungsnachweis

# Copy the gradlew file and make it executable
COPY LabApp_Docker_Leistungsnachweis/gradlew ./
COPY LabApp_Docker_Leistungsnachweis/gradle/ ./gradle/

# Copy the build.gradle and settings.gradle files
COPY LabApp_Docker_Leistungsnachweis/build.gradle.kts ./
COPY LabApp_Docker_Leistungsnachweis/settings.gradle.kts ./

# Copy the source code
COPY LabApp_Docker_Leistungsnachweis/src/ ./src/

# Allow execution of gradlew
RUN chmod +x gradlew

# Run the Gradle build
RUN ./gradlew build

# Specify the port on which the application will run
EXPOSE 8080

# Define the command to start the application
CMD ["java", "-jar", "build/libs/LabApp_Docker_Leistungsnachweis.jar"]
