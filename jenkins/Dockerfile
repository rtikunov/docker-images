FROM docker.io/jenkins

# Set the locale
ENV LANG en_US.UTF-8  
ENV LANGUAGE en_US:en  
ENV LC_ALL en_US.UTF-8
ENV TZ Europe/Moscow

COPY ./reqs.txt /tmp/
COPY ./locale.gen /etc/

USER root
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update && \
    apt-get -y install python3 python3-pip gettext locales wget && \
    apt-get clean all

RUN locale-gen

RUN pip3 install -Ur /tmp/reqs.txt

RUN wget https://github.com/openshift/origin/releases/download/v3.6.1/openshift-origin-client-tools-v3.6.1-008f2d5-linux-64bit.tar.gz -O /tmp/openshift-origin-client-tools.tar.gz && \
    tar zxvf /tmp/openshift-origin-client-tools.tar.gz -C /tmp/ && \
    cp /tmp/openshift-origin-client-tools-v3.6.1-008f2d5-linux-64bit/oc /usr/bin/ && \
    rm -rf /tmp/openshift-origin-client-tools-v3.6.1-008f2d5-linux-64bit /tmp/openshift-origin-client-tools.tar.gz

USER jenkins
