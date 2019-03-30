FROM centos:7.6.1810

# =================================== EPEL
RUN yum -y update; yum clean all && \
	yum -y install epel-release; yum clean all

# =================================== Node
RUN yum -y install curl && \
	curl -sL https://rpm.nodesource.com/setup_10.x | bash - && \
	yum -y install nodejs

RUN node --version && \
	npm --version

# ==================================== Java 8
RUN yum -y install java-1.8.0-openjdk-devel
RUN java -version

# =================================== Python
RUN yum -y install gcc openssl-devel bzip2-devel libffi-devel wget make

RUN cd /usr/src && \
	wget https://www.python.org/ftp/python/3.7.2/Python-3.7.2.tgz && \
	tar xzf Python-3.7.2.tgz && \
	cd Python-3.7.2 && \
	./configure --enable-optimizations && \
	make altinstall && \
	rm /usr/src/Python-3.7.2.tgz && \
	cp /usr/src/Python-3.7.2/python /usr/bin/python && \
	python /usr/local/lib/python3.7/site-packages/easy_install.py pip && \
	pip install --upgrade pip

RUN python --version && \
	pip --version

# ==================================== AWS Cli
RUN pip install awscli --upgrade
