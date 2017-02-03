FROM ubuntu:xenial

MAINTAINER alljoynsville

RUN apt-get -q update && \
	apt-get -y install -qq openjdk-8-jdk-headless libswt-gtk-3-java lib32z1 lib32ncurses5 lib32stdc++6 ant wget vim less unzip && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget -q https://dl.google.com/android/repository/tools_r25.2.3-linux.zip -O sdk.zip && \
	unzip -qq -d /usr/local/android-sdk-linux sdk.zip && rm sdk.zip

ENV ANDROID_HOME /usr/local/android-sdk-linux
ENV PATH ${JAVA_HOME}/bin:${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools

WORKDIR  /root/
