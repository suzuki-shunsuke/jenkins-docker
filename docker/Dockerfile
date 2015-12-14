FROM debian:8.2
COPY locale.gen /etc/locale.gen
RUN apt-get update
RUN apt-get install -y sudo python python3 wget locales supervisor
RUN wget -q -O - http://pkg.jenkins-ci.org/debian/jenkins-ci.org.key | apt-key add -
RUN echo "deb http://pkg.jenkins-ci.org/debian binary/" >> /etc/apt/sources.list
RUN apt-get update
RUN apt-get install -y jenkins
RUN rm -rf /var/lib/apt/lists/*
RUN locale-gen
RUN update-locale LANG=ja_JP.UTF-8
RUN wget https://raw.github.com/pypa/pip/master/contrib/get-pip.py
RUN python3 get-pip.py
RUN python get-pip.py
RUN rm get-pip.py
RUN useradd -m debian
RUN gpasswd -a debian sudo
RUN /etc/init.d/jenkins start
WORKDIR /root
ENV LANG=ja_JP.UTF-8 TERM=xterm
EXPOSE 8080
