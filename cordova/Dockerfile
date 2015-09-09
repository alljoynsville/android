FROM alljoynsville/android

MAINTAINER CloudOfThings

RUN nodeVersion=node-v4.0.0-linux-x64 && \
    wget -qO- https://nodejs.org/dist/latest/$nodeVersion.tar.gz | tar -zx -C /opt/ && \
    ln -s /opt/$nodeVersion/bin/node /usr/bin/node && \
    ln -s /opt/$nodeVersion/bin/npm /usr/bin/npm

RUN npm install -g cordova && ln -s /opt/$nodeVersion/lib/node_modules/cordova/bin/cordova /usr/bin/cordova

