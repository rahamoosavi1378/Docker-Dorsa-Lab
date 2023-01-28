FROM centos:7

# set proxy 
# =========

RUN yum update -y
RUN yum -y erase vim-minimal iputils libss
RUN yum -y install openssh openssh-server openssh-clients

RUN yum -y install net-tools wget curl nc whois nano epel-release

RUN yum -y install yum-utils
RUN yum-complete-transaction --cleanup-only

RUN yum -y install python3

RUN yum -y install git

RUN yum -y clean all

# set user and pass for ssh
RUN echo "PasswordAuthentication yes" >> /etc/ssh/sshd_config
RUN ssh-keygen -A
RUN echo "root:root" | chpasswd
# =========================

# ADD ./start.sh /start.sh
# RUN chmod +x /start.sh
# WORKDIR /var/www/html/
# RUN git clone https://github.com/meisamrce/DorsaLab.git 

CMD /usr/sbin/sshd -D