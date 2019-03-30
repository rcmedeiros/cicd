FROM centos:7.4.1708

# =================================== EPEL
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
	
# =================================== Node
RUN yum -y install curl
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum -y install nodejs

RUN node --version
RUN npm --version 

