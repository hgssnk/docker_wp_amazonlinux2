FROM amazonlinux:latest
ENV wp https://ja.wordpress.org/latest-ja.tar.gz

# apache
RUN yum update -y \
    && yum -y install httpd procps wget tar systemd-sysv git

# php関連
RUN amazon-linux-extras enable php7.3
RUN yum install php php-gd php-mysqlnd php-xmlrpc -y

# WordPress設置
#RUN wget -P /var/www/html $wp
#RUN cd /var/www/html && find ./ -type f -name "*.tar.gz" -exec tar zxf {} \;
#RUN mv /var/www/html/wordpress/* /var/www/html
#RUN chown -R apache:apache /var/www/html

# apache自動起動
RUN systemctl enable httpd.service

# ポート80開放
EXPOSE 80

# コンテナ起動時に各種プロセス起動
CMD ["/sbin/init"]
