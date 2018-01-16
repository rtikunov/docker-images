FROM docker.io/centos:7

#COPY ./openshift-origin-client-tools-v1.3.3-bc17c1527938fa03b719e1a117d584442e3727b8-linux-64bit/oc /usr/local/bin/
COPY CentOS-OpenShift-Origin.repo /etc/yum.repos.d/
COPY RPM-GPG-KEY-CentOS-SIG-PaaS /etc/pki/rpm-gpg/
COPY ./reqs.txt /tmp/

RUN yum -y install epel-release && \
    yum -y install python34 python34-pip origin-clients gettext bash-completion vim-enhanced jq && \
    yum clean all

RUN pip3 install -Ur /tmp/reqs.txt
