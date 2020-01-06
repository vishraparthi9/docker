FROM centos:7
ENV container docker
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == \
systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;

RUN yum -y update && yum clean all && \
    yum install -y epel-release && yum install -y nginx && \
    rm -f /usr/share/nginx/html/en-US /usr/share/nginx/html/img /usr/share/nginx/html/index.html && \
    systemctl enable nginx.service
ADD index.html /usr/share/nginx/html/

RUN chown -R nginx:nginx /usr/share/nginx && chown -R nginx:nginx /var/log/nginx

EXPOSE 80

CMD ["/usr/sbin/nginx", "-g", "daemon off;"]
