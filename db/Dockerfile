FROM amazonlinux:latest

# mysql
RUN yum update -y \
    && yum -y install mariadb mariadb-server procps systemd-sysv

# 自動起動
RUN systemctl enable mariadb
RUN chown -R mysql:mysql /var/lib/mysql

# ポート80開放
EXPOSE 3306

# コンテナ起動時に各種プロセス起動
CMD ["/sbin/init"]
