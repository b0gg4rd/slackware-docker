FROM vbatts/slackware-base:14.1

MAINTAINER Fernando Cruz <boggard@hotmail.com>

RUN export JRE_FILE_NAME=jre-8u74-linux-x64.tar.gz && \
    wget --no-check-certificate --no-cookies \
      --header "Cookie: oraclelicense=accept-securebackup-cookie" \
      http://download.oracle.com/otn-pub/java/jdk/8u74-b02/$JRE_FILE_NAME \
      -O /tmp/$JRE_FILE_NAME && \
    tar zxvf /tmp/$JRE_FILE_NAME -C /usr/share && \
    rm /tmp/$JRE_FILE_NAME && \
    export JRE_PROFILE=/etc/profile.d/jre.sh && \
    echo '#!/bin/sh' >> $JRE_PROFILE && \
    echo 'export JAVA_HOME=/usr/share/jre1.8.0_74' >> $JRE_PROFILE && \
    echo 'export PATH=$PATH:$JAVA_HOME/bin' >> $JRE_PROFILE && \
    chmod +x $JRE_PROFILE

