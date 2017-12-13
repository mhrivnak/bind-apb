FROM centos:7

RUN yum update -y && yum install -y bind && yum clean all

ADD named.conf /etc/named.conf

EXPOSE 5053/tcp
EXPOSE 5053/udp

# see "Support Arbitrary User IDs"
# https://docs.openshift.org/latest/creating_images/guidelines.html
RUN chgrp -R 0 /var/named && chmod -R g=u /var/named

# user named
USER 25

CMD /usr/sbin/named -c /etc/named.conf -g
