FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
RUN yum install -y openssl openssh-client git tree jq zip unzip libxml2-utils wget curl

# ==================================== Java 8
RUN yum -y install java-1.8.0-openjdk-devel
ENV JAVA_HOME /etc/alternatives/java_sdk

# ==================================== Maven 3
RUN wget http://www-us.apache.org/dist/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz && \
	tar -xf apache-maven-3.6.1-bin.tar.gz && \
	mv apache-maven-3.6.1/ apache-maven/

ENV M2_HOME /apache-maven
ENV PATH=${M2_HOME}/bin:${PATH}

# ==================================== AWS Cli
RUN yum install -y python-pip && \
	pip install --upgrade pip && \
	pip install awscli --upgrade

# ==================================== Sonar Cli
RUN curl -o scanner.zip 'https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.0.0.1744.zip'
RUN unzip scanner.zip
RUN mv sonar-scanner-4.0.0.1744 sonar-scanner
RUN chmod +x sonar-scanner/bin/sonar-scanner
RUN rm -rf scanner.zip
