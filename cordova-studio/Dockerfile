FROM alljoynsville/cordova

MAINTAINER alljoynsville

ENV ANDROID_STUDIO_URL https://dl.google.com/dl/android/studio/ide-zips/1.5.0.4/android-studio-ide-141.2422023-linux.zip

RUN apt-get update \
 && apt-get install -y curl openssh-server xorg libgtk2.0-0 libssl-dev build-essential scons subversion git-core valgrind cmake \
 && mkdir /var/run/sshd \
 && curl -L https://dl.google.com/dl/android/studio/ide-zips/1.5.0.4/android-studio-ide-141.2422023-linux.zip -o /tmp/android-studio.zip \
 && unzip /tmp/android-studio.zip -d /usr/local \
 && rm /tmp/android-studio.zip \
 && adduser --disabled-password --quiet --gecos '' studio \
 && echo 'studio:studio' | chpasswd \
 && chown -R root:studio /usr/local/android-studio \
 && chmod -R 775 /usr/local/android-studio \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD ["/usr/sbin/sshd", "-D"]

