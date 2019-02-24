FROM jenkins/jenkins:latest

# Install jenkins job builder as root
USER root
RUN apt-get update && apt-get -y upgrade && apt-get -y install python-pip
RUN pip install jenkins-job-builder


# switch back to jen kins user and configure plugins
USER jenkins

RUN /usr/local/bin/install-plugins.sh git mstest matrix-auth workflow-aggregator docker-workflow blueocean credentials-binding

ENV JENKINS_USER admin
ENV JENKINS_PASS admin

# Skip initial setup
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

COPY executors.groovy /usr/share/jenkins/ref/init.groovy.d/
COPY default-user.groovy /usr/share/jenkins/ref/init.groovy.d/

VOLUME /var/jenkins_home