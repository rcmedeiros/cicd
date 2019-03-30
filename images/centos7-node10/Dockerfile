FROM centos:7.6.1810

# =================================== EPEL
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all

# =================================== Node
RUN yum -y install curl
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum -y install nodejs

RUN node --version
RUN npm --version

# ==================================== AWS Cli
RUN yum install -y python-pip && \
	pip install --upgrade pip && \
	pip install awscli --upgrade

