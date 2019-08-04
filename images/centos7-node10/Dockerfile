FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
RUN yum install -y openssl openssh-client git tree jq zip unzip libxml2-utils wget curl

# =================================== Node
RUN yum -y install curl
RUN curl -sL https://rpm.nodesource.com/setup_10.x | bash -
RUN yum -y install nodejs

# ==================================== AWS Cli
RUN yum install -y python-pip && \
	pip install --upgrade pip && \
	pip install awscli --upgrade

# ==================================== Sonar Cli
RUN curl -o scanner.zip 'https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.0.0.1744-linux.zip'
RUN unzip scanner.zip
RUN mv sonar-scanner-4.0.0.1744-linux sonar-scanner
RUN chmod +x sonar-scanner/bin/sonar-scanner
RUN rm -rf scanner.zip
