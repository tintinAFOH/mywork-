FROM ubuntu
LABEL maintainer="piattidjoka@gmail.com"
RUN mkdir -p /var/run/sshd

RUN apt update -y \
&& apt install -y openssh-server 


RUN  useradd -rm -d /home/naruto -s /bin/bash naruto \
&& echo naruto:liverpool_nufio | chpasswd

RUN mkdir /home/naruto/.ssh \
&& chmod 700 /home/naruto/.ssh

COPY id_rsa.pub /home/naruto/.ssh/authorized_keys

RUN chown naruto:naruto -R /home/naruto/.ssh \
&& chmod 600 /home/naruto/.ssh/authorized_keys
CMD [ "/usr/sbin/sshd","-D" ]
