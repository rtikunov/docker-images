FROM centos:7

RUN yum -y install epel-release && \
    yum -y install curl strace telnet tcpdump nginx iproute nmap-ncat \
    gettext bash-completion vim-enhanced jq less bind-utils rsync && \
    yum clean all

COPY ./nginx.conf /etc/nginx/
