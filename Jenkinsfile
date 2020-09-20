FROM ubuntu:latest

#Oracle Java7 install
RUN apt-get install software-properties-common -y
RUN apt-get update
RUN add-apt-repository -y ppa:webupd8team/java
RUN apt-get update
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN apt-get install -y oracle-java7-installer

#Jenkins install
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -
RUN sudo echo "deb http://pkg.jenkins-ci.org/debian binary/" >>     /etc/apt/sources.list
RUN apt-get update
RUN apt-get install --force-yes -y jenkins

#Zip support install
RUN apt-get update
RUN apt-get -y install zip

#Unzip hang.zip
#RUN cp /shared/hang.zip /var/lib/jenkins
#RUN unzip -o /var/jenkins/hang.zip -d /var/lib/jenkins/

#Restart jenkins server
RUN service jenkins start

EXPOSE 8080

