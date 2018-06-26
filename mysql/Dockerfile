FROM mysql:5.7

#RUN echo 'bind-address = 0.0.0.0' >>/etc/mysql/my.cnf 

#ENV HOME /root

#RUN /etc/my_init.d/00_regen_ssh_host_keys.sh

#CMD ["/sbin/my_init"]

# Some Environment Variables
#ENV    DEBIAN_FRONTEND noninteractive

#RUN sed -i "s/^exit 101$/exit 0/" /usr/sbin/policy-rc.d

# MySQL Installation
RUN apt-get update
RUN echo "mysql-server mysql-server/root_password password root" | debconf-set-selections
RUN echo "mysql-server mysql-server/root_password_again password root" | debconf-set-selections
RUN apt-get install -y mysql-server

ADD ./my.cnf    /etc/mysql/my.cnf

#RUN mkdir           /etc/service/mysql
#ADD build/mysql.sh  /etc/service/mysql/run
#RUN chmod +x        /etc/service/mysql/run

RUN mkdir -p        /var/lib/mysql/
RUN chmod -R 755    /var/lib/mysql/

#ADD etc/my_init.d/99_mysql_setup.sh /etc/my_init.d/99_mysql_setup.sh
#RUN chmod +x /etc/my_init.d/99_mysql_setup.sh

EXPOSE 3306
# END MySQL Installation

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

