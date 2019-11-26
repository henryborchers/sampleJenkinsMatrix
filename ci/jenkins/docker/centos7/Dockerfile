FROM centos:7
RUN yum -y update && \
    yum groupinstall -y "Development Tools" && \
    yum install -y epel-release && \
    yum install -y cmake3
RUN cmake3 --version
