FROM ubuntu:trusty

MAINTAINER alljoynsville

RUN apt-get -q update && \
	apt-get -yqq install openjdk-7-jdk libswt-gtk-3-java lib32z1 lib32ncurses5 lib32stdc++6 ant wget vim less && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget -qO- "http://dl.google.com/android/android-sdk_r24.4.1-linux.tgz" | tar -zx -C /usr/local/

ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV PATH ${JAVA_HOME}/bin:${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

RUN (while :; do echo 'y'; sleep 3; done) | android update sdk --no-ui --filter platform,tool,platform-tool --force

RUN (while :; do echo 'y'; sleep 3; done) | android update sdk --no-ui --filter platform,tool,platform-tool --force

RUN (while :; do echo 'y'; sleep 3; done) | android update sdk --no-ui --filter 1    


WORKDIR  /root/

VOLUME /usr/local/android-sdk-linux
