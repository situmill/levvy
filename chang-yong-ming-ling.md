##### 1.搜索Linux安装的库：sudo apt-cache search XXX

##### 2.查看端口号：netstat -apn \| grep 8085

##### 3.查看运行的程序：ps aux\|grep redis

##### 4.停止nginx： ./nginx -s stop

##### 5.重启nginx:./nginx -s reload

##### 6.启动/停止Apache ：service apache2 start/stop

##### 7.重启数据库：service mysql restart

##### 8.清理dns 缓存:ipconfig /flushdns

##### 9.Linux里设置环境变量的方法：export PATH=$PATH:/root/web 

##### 10.显示当前PATH环境变量:echo $PATH 

##### 11.创建数据库：create database xxx

##### 12.数据库表索引的创建：

##### a.CREATE INDEX indexName ON table\_name \(column\_name\); （可重复索引）

##### b.CREATE UNIQUE INDEX index\_name ON table\_name \(column\_name\) （不可重复索引）

##### 或

##### a.ALTER TABLE tbl\_name ADD INDEX index\_name \(column\_list\); 

##### b.CREATE UNIQUE INDEX index\_name ON table\_name \(column\_name\)

##### 13.删索引：DROP INDEX indexName ON mytable;

##### 14。给字段设置默认值：ALTER TABLE test ALTER COLUMN case\_status SET DEFAULT 'A';

##### 15.数据库创建表：

#####  CREATE TABLE pet\_data\(

#####    pet\_data\_id bigint\(20\) NOT NULL AUTO\_INCREMENT,

#####    uuid VARCHAR\(64\) NOT NULL,

##### 	 name VARCHAR\(64\) NOT NULL UNIQUE,

#####    start\_time bigint\(20\) NOT NULL,

##### 	 end\_time bigint\(20\) NOT NULL,

#####    stay\_time bigint\(20\) NOT NULL,

##### 	 visits int  DEFAULT 1,

##### 	 time datetime  DEFAULT CURRENT\_TIMESTAMP,

##### 	 CONSTRAINT u\_time UNIQUE \(uuid,start\_time\),

##### 	 unique \(name\),

#####    PRIMARY KEY \( pet\_data\_id \)

#####    \)ENGINE=InnoDB DEFAULT CHARSET=utf8;

#####    

##### 16.修改字段名：ALTER TABLE video\_square CHANGE name name text NOT NULL;

##### 17.删除字段：alter table share drop maxuser;

##### 18.添加字段：alter table friend add username int NOT NULL;

##### 19.唯一字段：Alter table vcards add UNIQUE\(account\);

##### 20.改变字段类型:alter table  share modify  sharetoken VARCHAR\(64\) NOT NULL;

##### 21.转移其他表中的数据:insert into user\_playback\(id\) select users\_id from users;

##### 注：把users表中的id全部加到user\_playback中

##### 22.复制一个表（格式）:CREATE TABLE users\_message\_tokens\_map LIKE iviewsdb.users\_tokens\_map;

##### 23.复制表中的数据:INSERT users\_message\_tokens\_map SELECT \* FROM iviewsdb.users\_tokens\_map;

##### 24.Linux运行后台进程:nohup node app.js & 或  ./a.out &

##### 25.连接redis命令:redis-cli -h 101.132.249.240 -p 6379 -a 123456 ，\(shutdown\)退出

##### 26.连接redis集群：redis-cli -c -p 7000

##### 27.备份数据库表数据 mysqldump -u root -p iviewsdb devices\_events\_temp&gt; mySQL.sql;

##### 28.加载备份的数据:source mySQL.sql

##### 29.数据库查询:select count\(\*\),COUNT\(DISTINCT server\) as addr from server\_information WHERE time between 1505439478 and 1505439510 AND server="lancens";

##### 30.获取最近7天的数据:select date\(time\),count\(\*\) from devices\_events\_temp where DATE\_SUB\(CURDATE\(\), INTERVAL 7 DAY\) &lt;= date\(time\) group by date\(time\);

##### 31.获取最近的500条数据:select time from \(select \* from devices\_events order by time desc\) as time limit 500;

##### 32.获取大于500条的数据:SELECT uuid,COUNT\(\*\) AS nums FROM devices\_events\_temp GROUP BY uuid  having nums&gt;500;

##### 33.多个列的UNIQUE约束：ALTER TABLE Persons ADD CONSTRAINT uc\_PersonID UNIQUE \(Id\_P,LastName\);

##### 34.如需撤销UNIQUE约束：ALTER TABLE Persons DROP INDEX uc\_PersonID

##### 35.有则更新无则插入：replace into  test\(id,time\)  VALUES \(1232,NOW\(\)\);

##### 



