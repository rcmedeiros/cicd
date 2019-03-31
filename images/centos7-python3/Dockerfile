FROM centos:7.6.1810

# =================================== EPEL & Tools
RUN yum -y update; yum clean all && \
    yum -y install epel-release; yum clean all
RUN yum install -y openssl git

# =================================== Python
RUN yum -y install gcc openssl-devel bzip2-devel libffi-devel wget make

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
