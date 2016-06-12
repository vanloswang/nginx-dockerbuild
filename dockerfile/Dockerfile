FROM fedora-23:latest
MAINTAINER Vanlos Wang <vanloswang@126.com>

# Labels consumed by build service
LABEL Component="nginx" \
      Name="nginx" \
      Version="1.8.0" \
      Release="1"

# Labels could be consumed by Origin
LABEL io.k8s.description="nginx [engine x] is an HTTP and reverse proxy server, a mail proxy server, and a generic TCP/UDP proxy server, originally written by Igor Sysoev." \
      io.k8s.display-name="nginx 1.8.0" \
      io.openshift.expose-services="80:http" \
      io.openshift.tags="nginx"

RUN yum -y install --setopt=tsflags=nodocs nginx && \
    yum clean all && \
    mkdir -p /usr/share/nginx/html

RUN echo "This is a NGINX in Container example. Welcome!" > /usr/share/nginx/html/index.html && chmod 777 -R /var/log/nginx /var/lib/nginx/tmp 

EXPOSE 80

USER 5001

ENTRYPOINT ["container-entrypoint"]
CMD [ "nginx18" ]
