FROM docker.io/centos:7

COPY CentOS-OpenShift-Origin.repo /etc/yum.repos.d/
COPY RPM-GPG-KEY-CentOS-SIG-PaaS /etc/pki/rpm-gpg/
COPY ./reqs.txt /tmp/

RUN yum -y install epel-release && \
    yum -y install python34 python34-pip origin-clients gettext bash-completion vim-enhanced jq && \
    yum clean all

RUN pip3 install -Ur /tmp/reqs.txt
