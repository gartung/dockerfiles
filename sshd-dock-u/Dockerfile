# sshd
#
# VERSION               0.0.2

FROM ubuntu:14.04
CMD "sh" "-c" "echo nameserver 8.8.8.8 >> /etc/resolv.conf"
RUN apt-get update && apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN echo 'root:root_password' | chpasswd
RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

RUN groupadd -g 1001 cms_admin
RUN useradd -u 1001 cms_admin -g cms_admin
RUN echo 'cms_admin:cms_admin' | chpasswd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]

