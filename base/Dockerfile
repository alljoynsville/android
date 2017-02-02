FROM ubuntu:xenial

MAINTAINER alljoynsville

RUN apt-get -q update && \
	apt-get -y install -qq openjdk-8-jdk libswt-gtk-3-java lib32z1 lib32ncurses5 lib32stdc++6 ant wget vim less && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget -qO- "https://dl.google.com/android/repository/tools_r25.2.3-linux.zip" | tar -zx -C /usr/local/

ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV PATH ${JAVA_HOME}/bin:${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

WORKDIR  /root/
