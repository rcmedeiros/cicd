FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
RUN yum install -y openssl git tree jq

# ==================================== Java 8
RUN yum -y install java-1.8.0-openjdk-devel

# ==================================== AWS Cli
RUN yum install -y python-pip && \
	pip install --upgrade pip && \
	pip install awscli --upgrade
