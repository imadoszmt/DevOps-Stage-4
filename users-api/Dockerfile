FROM maven:3.8-openjdk-11 AS builder

WORKDIR /app

# Copy pom.xml first for better caching
COPY pom.xml .

# Download dependencies
RUN mvn dependency:go-offline -B

# Copy source code
COPY src ./src

# Build the application
RUN mvn package -DskipTests

# Final image
FROM openjdk:8-jre-slim

WORKDIR /app

# Copy the built JAR file
COPY --from=builder /app/target/*.jar UsersApi.jar

# Expose port
EXPOSE 8083

ENTRYPOINT ["java", "-jar", "UsersApi.jar"]