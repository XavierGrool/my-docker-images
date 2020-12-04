FROM ubuntu:18.04

# change the apt source to aliyun
RUN rm /etc/apt/sources.list
ADD sources.list /etc/apt/sources.list

# install jdk-8
RUN set -eux; \
	apt-get update; \
	apt-get install -y --no-install-recommends openjdk-8-jdk-headless

# install python3 and create a soft link
RUN set -eux; \
	apt-get update; \
	apt-get install -y --no-install-recommends python3; \
	ln -s /usr/bin/python3 /usr/bin/python

# install pip3
RUN set -eux; \
	apt-get update; \
	apt-get install -y --no-install-recommends \
		python3-pip \
		python3-setuptools \
		python3-dev \
		python3-wheel

# change the pip source to tsinghua
RUN mkdir /root/.pip
ADD pip.conf /root/.pip/pip.conf

# install pyspark
RUN pip3 install pyspark

CMD ["bash"]