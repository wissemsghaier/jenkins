FROM jenkins/jenkins:2.393
LABEL maintainer=”mstewart@riotgames.com”
USER root
RUN mkdir /var/log/jenkins
RUN chown -R jenkins:jenkins /var/log/jenkins
RUN apt-get update && \
    apt-get install -y apt-utils && \
    apt-get update && \
    apt-get install -y software-properties-common && \
    apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E5267A6C && \
    add-apt-repository ppa:ondrej/php && \
    sed -i 's/lunar/focal/g' /etc/apt/sources.list.d/ondrej-ubuntu-php*.list && \
    apt-get update && \
    apt-get install -y php8.1-cli php8.1-xml php8.1-curl
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
USER jenkins
