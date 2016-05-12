FROM java:8

MAINTAINER erwin <docker.image@vii.ch> 

LABEL version="1.0"
LABEL description="This text illustrates \
                   that label-values can span multiple lines."

ENV DOWNLOAD http://www.h2database.com/h2-2016-01-21.zip
ENV H2_VERSION 1.4.191
ENV H2_DIR /opt
ENV DATA_DIR /opt/h2/data

VOLUME ${DATA_DIR}


RUN curl ${DOWNLOAD} -o h2.zip \
    && mkdir -p ${DATA_DIR} \
    && unzip h2.zip h2/bin/h2-${H2_VERSION}.jar -d ${H2_DIR}/ \
    && rm h2.zip \
    && ls ${H2_DIR} \
    && ls ${H2_DIR}/h2/bin
    

EXPOSE 81 1521

CMD ["java", "-jar", "/opt/h2/bin/h2-1.4.191.jar", \gg
 	"-web", "-webAllowOthers", "-webPort", "81", \
 	"-tcp", "-tcpAllowOthers", "-tcpPort", "1521", \
 	"-baseDir", "/opt/h2/data"] 