FROM centos:8

RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*

COPY libs/oracle-instantclient11.2-basic-11.2.0.4.0-1.x86_64.rpm /tmp/instantclient.rpm
RUN cd /tmp && yum install -y instantclient.rpm && yum install -y libnsl
RUN sh -c "echo /usr/lib/oracle/11.2/client64/lib > /etc/ld.so.conf.d/oracle-instant-client.conf" && ldconfig
RUN cd /usr/lib/oracle/11.2/client64/lib && ln -s libclntsh.so.11.2 libclntsh.so

RUN yum install -y wget git gcc 
RUN cd /tmp && wget https://go.dev/dl/go1.18.linux-amd64.tar.gz && tar -C /usr/local -xzf go1.18.linux-amd64.tar.gz
ENV PATH="/usr/local/go/bin:${PATH}"
