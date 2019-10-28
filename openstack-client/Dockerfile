FROM docker.io/centos:7

COPY reqs.txt /tmp/

RUN yum -y install epel-release && \
    yum -y install gcc make openssl-devel python36 python36-pip python36-devel gettext bash-completion vim-enhanced jq git && \
    yum clean all

RUN pip3 install -Ur /tmp/reqs.txt
