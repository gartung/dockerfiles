FROM cern/slc6-base 
CMD "sh" "-c" "echo nameserver 8.8.8.8 >> /etc/resolv.conf"
ADD HEP_OSlibs.repo /etc/yum.repos.d/HEP_OSlibs.repo
RUN yum update -y && yum install -y HEP_OSlibs_SL6 wget rpm-build which git screen e2fsprogs python-pip jq
RUN pip install pygithub
RUN yum install -y strace vim svn screen openssh-server

RUN yum -y install openssh-server && \
    yum -y install pwgen && \
    rm -f /etc/ssh/ssh_host_ecdsa_key /etc/ssh/ssh_host_rsa_key && \
    ssh-keygen -q -N "" -t dsa -f /etc/ssh/ssh_host_ecdsa_key && \
    ssh-keygen -q -N "" -t rsa -f /etc/ssh/ssh_host_rsa_key && \
    sed -i "s/#UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config

RUN groupadd -g 1001 cms_admin
RUN useradd -u 1001 cms_admin -g cms_admin
RUN echo 'cms_admin:cms_admin' | chpasswd
RUN echo 'root:root_password' | chpasswd
RUN yum -y install gcc-gfortran
RUN yum -y install nano 

ADD cvmfs/cernvm.repo /etc/yum.repos.d/cernvm.repo
RUN yum install openssh-server nano cvmfs man freetype openssl098e libXpm libXext wget git  tcsh zsh tcl  perl-ExtUtils-Embed perl-libwww-perl  compat-libstdc++-33  libXmu  libXpm  zip e2fsprogs krb5-devel krb5-workstation  strace libXft -y

ADD cvmfs/default.local /etc/cvmfs/default.local
ADD cvmfs/run.sh /root/run.sh
RUN mkdir /cvmfs/cms.cern.ch ; #mkdir /cvmfs/cms-condb.cern.ch
RUN echo "cms.cern.ch /cvmfs/cms.cern.ch cvmfs defaults 0 0" >> /etc/fstab
Run mkdir /cvmfs/cms-ib.cern.ch ;
RUN echo "cms-ib.cern.ch /cvmfs/cms-ib.cern.ch cvmfs defaults 0 0" >> /etc/fstab
RUN yum -y install xauth
RUN yum -y install glx-utils

EXPOSE 22
CMD ["/root/run.sh"]
