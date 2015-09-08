FROM debian:jessie

MAINTAINER CloudOfThings

RUN apt-get update && \
	apt-get -y install libswt-gtk-3-java lib32z1 lib32ncurses5 lib32stdc++6 ant wget vim less && \
	apt-get clean && \
	rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN wget -qO- "http://dl.google.com/android/android-sdk_r24.3.4-linux.tgz" | tar -zxv -C /opt/

ENV ANDROID_HOME /opt/android-sdk-linux
ENV PATH ${JAVA_HOME}/bin:${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/platform-tools
RUN echo ${JAVA_HOME}

RUN echo y | \
    android update sdk --no-ui --all --filter platform-tools,android-16,android-19 --force
RUN echo y | \
	android update sdk --no-ui --filter 1,2

WORKDIR  /root/
