FROM vbatts/slackware-base:14.1

MAINTAINER Fernando Cruz <boggard@hotmail.com>

RUN slackpkg -batch=on -default_answer=y update && \
    slackpkg -batch=on -default_answer=y install nginx && \
    
    export WEBSVN_VERSION=2.3.3 && \
    wget http://websvn.tigris.org/files/documents/1380/49056/websvn-$WEBSVN_VERSION.tar.gz && \
    tar zxvf websvn-2.3.3.tar.gz && \
    rm websvn-2.3.3.tar.gz
