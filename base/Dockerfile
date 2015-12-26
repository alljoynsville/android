FROM debian:jessie

MAINTAINER alljoynsville

RUN apt-get update && \
	apt-get -y install openjdk-7-jdk libswt-gtk-3-java lib32z1 lib32ncurses5 lib32stdc++6 ant wget vim less && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget -qO- "http://dl.google.com/android/android-sdk_r24.4.1-linux.tgz" | tar -zxv -C /usr/local/

ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV PATH ${JAVA_HOME}/bin:${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

RUN echo y | \
    android update sdk --no-ui --all --filter platform,tool,platform-tool --force

RUN echo y | \
    android update sdk --no-ui --all --filter platform,tool,platform-tool --force

WORKDIR  /root/

VOLUME /usr/local/android-sdk-linux
