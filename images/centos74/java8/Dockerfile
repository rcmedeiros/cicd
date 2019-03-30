FROM centos:7.4.1708

# =================================== EPEL
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
	
# ==================================== Java 8
RUN yum -y install java-1.8.0-openjdk-devel
RUN java -version
