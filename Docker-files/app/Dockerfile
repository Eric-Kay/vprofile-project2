FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN https://github.com/Eric-Kay/vprofile-project.git
RUN cd vproile-project && git checkout docker && mvn install

FROM tomcat:9-jre11 
LABEL "Porject"="Vprofile"
LABEL "Author"="Eric"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
WORKDIR /usr/local/tomcat/
VOLUME /usr/local/tomcat/webapps 