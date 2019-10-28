FROM docker.io/centos:7

COPY kubernetes.repo /etc/yum.repos.d/
COPY reqs.txt /tmp/
COPY kubectl-aliases.sh /etc/profile.d/

RUN yum -y install epel-release && \
    yum -y install python36 python36-pip kubectl-1.12.10 gettext bash-completion vim-enhanced jq git && \
    yum clean all

RUN pip3 install -Ur /tmp/reqs.txt
RUN kubectl completion bash > /etc/bash_completion.d/kubectl.bash
