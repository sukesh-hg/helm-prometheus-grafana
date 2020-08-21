FROM openjdk:8
COPY . /app
WORKDIR /app
ENV JAVA_TOOL_OPTIONS -agentlib:jdwp=transport=dt_socket,address=8000,server=y,suspend=n
#ENTRYPOINT ["java", "-cp", "remote-debug.jar", "remote.RemoteDebug"]
EXPOSE 8080
CMD ["java","-javaagent:jmx_prometheus_javaagent-0.13.0.jar=8080:config.yaml","-jar","remote-debug.jar"]
