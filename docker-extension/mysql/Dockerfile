FROM mysql:5.7

#这条语句可有可无
ENV MYSQL_DATABASE test

#设置免密登录
ENV MYSQL_ALLOW_EMPTY_PASSWORD yes

#将所需文件放到容器中
#添加my.cnf文件,设置mysql的字符编码,防止导入中文记录时出现乱码
COPY setup.sh /mysql/setup.sh
COPY schema.sql /mysql/schema.sql
COPY privileges.sql /mysql/privileges.sql
COPY my.cnf /etc/alternatives/my.cnf

#设置容器启动时执行的命令
CMD ["bash", "/mysql/setup.sh"]