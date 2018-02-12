FROM jenkins/jenkins:lts
COPY files /
USER root

RUN apt-get update --fix-missing && \
    apt-get -y \
    install \
    telnet \
    net-tools \
    less \
    vim && \
    apt-get -y clean && \
    apt-get -q -y autoremove
RUN /usr/local/bin/install-plugins.sh < /usr/share/jenkins/ref/plugins.txt

ENV JAVA_OPTS -Djava.util.logging.config.file=/usr/share/jenkins/log.properties