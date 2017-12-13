FROM centos:7

RUN yum update -y && yum install -y bind && yum clean all

ADD named.conf /etc/named.conf

EXPOSE 5053/tcp
EXPOSE 5053/udp

USER named

CMD /usr/sbin/named -c /etc/named.conf -g
