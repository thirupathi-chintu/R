FROM thirupathip/amazoncorretto



RUN addgroup -S spring && adduser -S spring -G spring
USER spring:spring
ARG JAR_FILE=/application/build/libs/*.jar
RUN cp ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]