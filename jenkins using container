FROM debian

RUN apt update
RUN apt install fontconfig openjdk-21-jre -y
#java -version

RUN apt install wget -y
RUN wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key

#RUN apt install echo -y
RUN echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null

RUN apt update
RUN apt install jenkins -y

EXPOSE 8080
CMD ["java", "-jar", "/usr/share/java/jenkins.war", "--httpPort=8080"]
