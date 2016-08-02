FROM boggard/slackware-jre:8u74

MAINTAINER Fernando Cruz <boggard@hotmail.com>

RUN slackpkg -batch=on -default_answer=y update && \
    slackpkg -batch=on -default_answer=y install infozip-6.0 && \

    export ARTIFACTORY_VERSION=4.8.0 %% \
    export ARTIFACTORY_OSS=artifactory-oss-$ARTIFACTORY_VERSION && \
    export ARTIFACTORY_FILE_NAME=jfrog-$ARTIFACTORY_OSS.zip && \
    wget --no-check-certificate \
      https://bintray.com/jfrog/artifactory/download_file?file_path=$ARTIFACTORY_FILE_NAME \
      -O /tmp/$ARTIFACTORY_FILE_NAME && \
    cd /tmp && unzip $ARTIFACTORY_FILE_NAME && \
    mv $ARTIFACTORY_OSS /usr/share && \
    rm /tmp/$ARTIFACTORY_FILE_NAME && \
    slackpkg -batch=on -default_answer=y remove infozip-6.0

EXPOSE 8081

CMD ["sh", "-l", "-c", "/usr/share/artifactory-oss-4.5.1/bin/artifactory.sh"]
