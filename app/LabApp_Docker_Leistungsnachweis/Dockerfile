# Verwende das offizielle OpenJDK-Image
FROM openjdk:22-jdk-slim

# Setze das Arbeitsverzeichnis
WORKDIR LabApp_Docker_Leistungsnachweis

# Kopiere die gradle und gradlew-Dateien
COPY gradlew .
COPY gradle/ gradle/

# Kopiere die build.gradle und settings.gradle Dateien
COPY LabApp_Docker_Leistungsnachweis/build.gradle.kts .
COPY LabApp_Docker_Leistungsnachweis/settings.gradle.kts .

# Kopiere den Quellcode
COPY LabApp_Docker_Leistungsnachweis/src/ src/

# Erlaube die Ausführung von gradlew
RUN chmod +x gradlew

# Führe den Gradle-Build aus
RUN ./gradlew build

# Gebe den Port an, auf dem die Anwendung läuft
EXPOSE 8080

# Definiere den Startbefehl für die Anwendung
CMD ["java", "-jar", "build/libs/LabApp_Docker_Leistungsnachweis"]
