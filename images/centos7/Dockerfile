FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all
RUN yum install -y openssl openssh-client git tree jq zip unzip libxml2-utils wget curl

# =================================== Node
RUN yum -y install curl && \
	curl -sL https://rpm.nodesource.com/setup_10.x | bash - && \
	yum -y install nodejs

# ==================================== Java 8
RUN yum -y install java-1.8.0-openjdk-devel
ENV JAVA_HOME /etc/alternatives/java_sdk

# ==================================== Maven 3
RUN wget http://www-us.apache.org/dist/maven/maven-3/3.6.1/binaries/apache-maven-3.6.1-bin.tar.gz && \
	tar -xf apache-maven-3.6.1-bin.tar.gz && \
	mv apache-maven-3.6.1/ apache-maven/

ENV M2_HOME /apache-maven
ENV PATH=${M2_HOME}/bin:${PATH}

RUN mvn --version

# =================================== Python
RUN yum -y install gcc openssl-devel bzip2-devel libffi-devel wget make jq

RUN cd /usr/src && \
	wget https://www.python.org/ftp/python/3.7.3/Python-3.7.3.tgz && \
	tar xzf Python-3.7.3.tgz && \
	cd Python-3.7.3 && \
	./configure --enable-optimizations && \
	make altinstall && \
	rm /usr/src/Python-3.7.3.tgz && \
	cp /usr/src/Python-3.7.3/python /usr/bin/python && \
	python /usr/local/lib/python3.7/site-packages/easy_install.py pip && \
	pip install --upgrade pip

# ==================================== AWS Cli
RUN pip install awscli --upgrade

# ==================================== Sonar Cli
RUN curl -o scanner.zip 'https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.0.0.1744.zip'
RUN unzip scanner.zip
RUN mv sonar-scanner-4.0.0.1744 sonar-scanner
RUN chmod +x sonar-scanner/bin/sonar-scanner
RUN rm -rf scanner.zip
