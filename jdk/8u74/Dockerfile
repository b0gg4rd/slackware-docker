FROM vbatts/slackware-base:14.1

MAINTAINER Fernando Cruz <boggard@hotmail.com>

RUN export JDK_FILE_NAME=jdk-8u74-linux-x64.tar.gz && \
    wget --no-check-certificate --no-cookies \
      --header "Cookie: oraclelicense=accept-securebackup-cookie" \
      http://download.oracle.com/otn-pub/java/jdk/8u74-b02/$JDK_FILE_NAME \
      -O /tmp/$JDK_FILE_NAME && \
    tar zxvf /tmp/$JDK_FILE_NAME -C /usr/share && \
    rm /tmp/$JDK_FILE_NAME && \
    export JDK_PROFILE=/etc/profile.d/jdk.sh && \
    echo '#!/bin/sh' >> $JDK_PROFILE && \
    echo 'export JAVA_HOME=/usr/share/jdk1.8.0_74' >> $JDK_PROFILE && \
    echo 'export PATH=$PATH:$JAVA_HOME/bin' >> $JDK_PROFILE && \
    chmod +x $JDK_PROFILE

