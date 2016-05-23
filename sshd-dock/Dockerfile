FROM cern/slc6-base
CMD "sh" "-c" "echo nameserver 8.8.8.8 >> /etc/resolv.conf"
ADD HEP_OSlibs.repo /etc/yum.repos.d/HEP_OSlibs.repo

RUN yum -y install openssh-server epel-release && \
    yum -y install pwgen xauth && \
    rm -f /etc/ssh/ssh_host_ecdsa_key /etc/ssh/ssh_host_rsa_key && \
    ssh-keygen -q -N "" -t dsa -f /etc/ssh/ssh_host_ecdsa_key && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_rsa_key && \
    sed -i "s/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config

RUN groupadd -g 1001 cms_admin
RUN useradd -u 1001 cms_admin -g cms_admin
RUN echo 'cms_admin:cms_admin' | chpasswd
RUN echo 'root:root_password' | chpasswd

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
