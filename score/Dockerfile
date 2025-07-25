FROM gradle:8.7.0-jdk17 AS builder
WORKDIR /app
COPY . .
RUN gradle build --no-daemon

FROM eclipse-temurin:17
WORKDIR /app
COPY --from=builder /app/build/libs/*.jar app.jar
EXPOSE 8080
ENV PORT 8080
CMD ["java", "-jar", "app.jar"]
