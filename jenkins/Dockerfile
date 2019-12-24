FROM jenkins/jenkins
USER root

RUN apt update -q && apt install -y zip unzip

RUN apt update -q  &&\
    apt install -y apt-transport-https lsb-release ca-certificates &&\
    apt install software-properties-common -y && \
    wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg && \
    sh -c 'echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list' && \
    apt update -q && \
    apt install -y php7.2 php7.2-common php7.2-cli php7.2-fpm php7.2-mysql php7.2-xml php7.2-curl php7.2-mbstring php7.2-zip php7.2-gd && \
    apt install -y curl

RUN apt update -q && apt install -y  maven

RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/bin/ --filename=composer

RUN composer --version

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -

RUN apt-get install nodejs -y

RUN nodejs --version

RUN apt install npm

RUN npm --version

RUN npm install -g @angular/cli -y
