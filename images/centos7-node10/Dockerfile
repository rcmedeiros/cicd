FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
RUN yum install -y openssl git

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
