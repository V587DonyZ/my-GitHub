# Mysql数据库

# 1. 初识数据库

```python
1. 解决数据读取慢的问题
2. 数据一致性
3. 数据的安全性
4. 解决了并发问题
```

```python
数据库管理系统DBMS
数据库管理员DBA
数据库database → db
表 table
```

```python
数据库分类:
    1.关系型数据库:数据之间关系紧密  mysql oracle sqlserver sqllite(轻量级小数据库) access
    2.非关系型数据库 :存储数据快  redis mongodb(轻量级)  memcache(内存级别,存储快,断电消失)

```

# 2. 安装数据库

Mysql 数据库管理系统

```python
卸载数据库:
    1. 停止mysql服务 cmd :net stop mysql
    2. mysql remove 删除服务
    3. 删除安装目录
    4. 删除环境变量
    5. 清除注册表/重启计算机
    
安装数据库 :
    1. 路径不能有中文
    2. 路径中不能有特殊字符
    3. 在创建my.ini (utf-8格式)文件 在安装目录中创建 :
        """
        配置mysql
        [mysql]
		# 设置mysql客户端默认字符集
		default-character-set=utf8
		[mysqld]
		#设置3306端口
		port = 3306
		# 设置mysql的安装目录
		basedir=D:\mysql\mysql-5.6.44-winx64
		# 设置mysql数据库的数据的存放目录
		datadir=D:\mysql\mysql-5.6.44-winx64\data
		# 允许最大连接数
		max_connections=200
		# 服务端使用的字符集默认为8比特编码的latin1字符集
		character-set-server=utf8
		# 创建新表时将使用的默认存储引擎
		default-storage-engine=INNODB
		"""
    4.配置环境变量 :
        添加环境变量 D:\Mysql\mysql-5.6.45-winx64\bin
    5. 管理员下cmd :mysqld install 安装
    6. 启动mysql服务 :cmd下: net start mysql  (启动的是mysql server端)
    7. 启动客户端 cmd : mysql
```

# 3. 初次使用数据库

```mysql
结构查询语句 ( Structure Query Language), SQL 数据库的核心语言,分四大类:
	1. DDL 数据定义语言 ,用来操作数据库对象:库 , 表 , 列等 ;指令有Create , ALTER , DROP
	2. DML 数据库操作语句,用来操作数据库数据 ; 指令有 Insert Update Delete select
	3. DCL 数据控制语句, 用来授予或访问数据库的某种特权,或操作事物特性; 指令有 Grant , RollBack , Commit
	
	4. DQL 数据查询语句, 用来查询数据 ; 指令 Select
```

```mysql
mysql -u root #进入
mysql -u root -p #输密码进入
exit # 退出
```

```mysql
对库操作 :
create database 数据库名; # 新建数据库
drop database 数据库名; # 删除数据库
show databases; # 查看所有数据库
use 数据库名; # 进入/切换数据库
```

```mysql
show tables; # 查看所有表格
create table 表名; # 创建表
select user(); # 查看当前登录用户
set password = password("密码"); # 给当前用户设置密码

create user '用户名'@'192.168.16.%'; # 创建用户,并且16网段下的所有主机都可以用这个用户名登录
create user '用户名'@'192.168.16.%' identified by '密码'; # 创建用户,设置密码

grant on 数据库名.表名 to '用户名'@'ip地址' # 创建 用户设置查看相应表的权限
grant on 数据库名.表名 to '用户名'@'ip地址%' identified by '密码' ; # 创建用户和密码并给相应表的权限

在这个数据库下的所有表中给这个用户名增删改查的权限(all):
	grant all on 数据库名.* to '用户名@ip地址' 
	
客户端登录srver:
	mysql -u用户名 -h server端IP地址 -p

root下查看所有用户：
	select user,host from mysql.user;
删除用户:
	delect from mysql.user where user like '用户名%';
```

```mysql
创建表:
create table 表名(字段 数据类型(长度),字段 数据类型(长度)...)
create table t1(id int,name char(12),password char(12));

删表:
drop table 表名;

改表名:
alter table 旧表名 rename 新表名;

查看表结构 :
desc 表名;



查看表所有数据:
select * from 表名;

修改表内数据 :
alter table 表名 change 旧字段名 新字段名 数据类型(长度)

操作表的数据:
增 :insert into 表名 values(1,'aa','22')

删除表内容:
delete from 表名 where id =1 ; 
修改表内容:
update 表名 set 属性名='修改值' where id = 1;


```



------



# 4 储存引擎

```mysql
数据的存储方式就是存储引擎engines

使用不同的存储引擎,数据是以不同的方式存储的
查看存储引擎:
show engines

InnoDB : 存两个文件
	1. 持久化存储
	2. 并发 修改 删除的操作的效率比较高
	3. mysql5.6以上,默认的存储方式
	4. row-level locking 行级锁
	5. table-;evel locking 表级锁
	6. foreign keys 外键(约束)
	7. 树tree - 加速查询 (树型结构+数据+表结构)
	8. transations 事务 保证数据的安全和完整
	
myisam : 三个文件
	1. 持久化存储
	2. 读 插入的操作效率高一些
	3. mysql5.5以下默认的存储方式
	4. table-;evel locking 表级锁
	5. 树tree - 加速查询(树型结构+数据+表结构)
memory : 磁盘中只存一个数据(表结构),其他存在内存中
	基于hash检索(内存中检索)
```

```python
# InnoDB
用于事务处理应用程序，支持外键和行级锁。如果应用对事物的完整性有比较高的要求，在并发条件下要求数据的一致性，数据操作除了插入和查询之外，还包括很多更新和删除操作，那么InnoDB存储引擎是比较合适的。InnoDB除了有效的降低由删除和更新导致的锁定，还可以确保事务的完整提交和回滚，对于类似计费系统或者财务系统等对数据准确要求性比较高的系统都是合适的选择。

# MyISAM
如果应用是以读操作和插入操作为主，只有很少的更新和删除操作，并且对事务的完整性、并发性要求不高，那么可以选择这个存储引擎。

# Memory
将所有的数据保存在内存中，在需要快速定位记录和其他类似数据的环境下，可以提供极快的访问。Memory的缺陷是对表的大小有限制，虽然数据库因为异常终止的话数据可以正常恢复，但是一旦数据库关闭，存储在内存中的数据都会丢失。
```



```mysql
# 修改储存引擎  默认innodb
create table 表名(表头...) engine=引擎;  (myisam innodb memory)
例子:
create table myisam_t (id int,name char(18)) engine=myisam;  # myisam innodb memory

查看创表语句
show create table 表名
```

# 5. 表的操作

## 1. 表的创建

```mysql
create table 表名(字段名 类型[ (宽度) 约束条件],字段名 类型[ (宽度) 约束条件]...)
# 注意:
1. 在同一张表中,字段名是不能相同的
2. 宽度和约束条件可选
3. 字段名和类型是必须的
```

## 2. 表的相关增删改查

```mysql
修改表名:
alter table 旧表名 rename 新表名
```



### **2.1 表的增删**

```mysql
增/创建表:
create table 表名 字段名 类型[ (宽度) 约束条件],字段名 类型[ (宽度) 约束条件]...);

删表:
drop table 表名
```

### **2.2 表结构的增删改查**

```mysql
增加字段: # 自动添加到最后
alter table 表名 add 字段名 类型;
选择位置增加字段 :
alter table 表名 add 字段名 类型 first # 设定为第一列
alter table 表名 add 字段名 类型 after 某字段名 # 设定位于某字段名之后



删除字段:
alter table 表名 drop 字段名
delete from 表名 where id = 1 ;# 删除 id=1(id为主键时) 这一行数据,不是删除字段名



修改字段的名称类型:
alter table 表名 modify 字段名 类型
alter table 表名 change 字段名 字段名 类型 # (特别)
修改字段的名称:
alter table 表名 change 旧字段名 新字段名 类型



查看表所有数据 :(表格形式)
select * from 表名 ; # *星 表示表中所有的字段名, 替换成字段名则查询某一字段,也可多个用逗号隔开

修改表数据
update class set id=1 where id =2;  # 将id=2修改为id=1

插入数据:
insert into 表名 values(数据1,数据2...)
```

## 3.  mysql支持的数据类型

### a.数值类型

| 类型         | 大小                                                  | 范围（有符号）                                               | 范围（无符号）unsigned约束                                   | 用途Application |
| :----------- | :---------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :-------------- |
| tinyint      | 1 字节                                                | (-128，127)                                                  | (0，255)                                                     | 小整数值        |
| smalyint     | 2 字节                                                | (-32 768，32 767)                                            | (0，65 535)                                                  | 大整数值        |
| mediumint    | 3 字节                                                | (-8 388 608，8 388 607)                                      | (0，16 777 215)                                              | 大整数值        |
| int或integer | 4 字节                                                | (-2 147 483 648，2 147 483 647)                              | (0，4 294 967 295)                                           | 大整数值        |
| bigint       | 8 字节                                                | (-9 233 372 036 854 775 808，9 223 372 036 854 775 807)      | (0，18 446 744 073 709 551 615)                              | 极大整数值      |
| float        | 4 字节float(255,30)                                   | (-3.402 823 466 E+38，-1.175 494 351 E-38)，0，(1.175 494 351 E-38，3.402 823 466 351 E+38) | 0，(1.175 494 351 E-38，3.402 823 466 E+38)                  | 单精度 浮点数值 |
| double       | 8 字节double(255,30)                                  | (-1.797 693 134 862 315 7 E+308，-2.225 073 858 507 201 4 E-308)，0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308) | 0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308) | 双精度 浮点数值 |
| decimal      | 对decimal(M,D) ，如果M>D，为M+2否则为D+2double(65,30) | 依赖于M和D的值                                               | 依赖于M和D的值                                               | 小数值          |

```mysql
### 整数
create table int_t (
      ti tinyint,            # ****
      i  int,       # 有符号可以是负数         # *****
      tiun tinyint unsigned,
      iun int unsigned # 无符号,不能是负数
);


### 小数
create table fd_t(
        f float,      # 精度问题 小数点后5位 # *****
        d double,     # 精度更高但也不准确
        f2 float(5,2),# 在精确位四舍五入
        d2 double(5,2)# 在精确位四舍五入
)

create table dec_t(
    dec1 decimal,
    dec2 decimal(30,20)
```



### b. 日期时间类型

| 类型      | 大小(字节) | 范围                                    | 格式                | 用途                     |
| :-------- | :--------: | :-------------------------------------- | :------------------ | ------------------------ |
| date      |     3      | 1000-01-01/9999-12-31                   | YYYY-MM-DD          | 年月日                   |
| time      |     3      | -838:59:59'/'838:59:59'                 | HH:MM:SS            | 时分秒                   |
| year      |     1      | 1901/2155                               | YYYY                | 年份值                   |
| datetime  |     8      | 1000-01-01 00:00:00/9999-12-31 23:59:59 | YYYY-MM-DD HH:MM:SS | 年月日时分秒             |
| timestamp |     4      | 1970-01-01 00:00:00/2038                | YYYYMMDD HHMMSS     | 混合日期和时间值，时间戳 |



```mysql
now()函数 → 当前时间

时间
    内置函数  now()
    datetime  打卡时间/日志/论坛博客类的评论\文章/*****
    date      员工生日/入职日期/离职日期/开班时间   *****
    time      上课时间/下课时间/规定上班时间    竞赛数据
    year
    timestamp 由于表示范围的问题,导致用的少了
    create table time_t2(
    	dt datetime # 格式 年月日时分秒
        dt datetime NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,   # 表示的范围更大,还能拥有timestamp的特点
        d  date, # 格式 年月日
        t  time,  # 格式 时分秒
        y  year, # 年
        ts timestamp    # 不能为空,默认值是当前时间,在修改的时候同时更新时间,最长时间到2038年# 年月日时分秒
    )

```



### c. 字符串类型:

| 类型       | 大小                | 用途                            |
| :--------- | ------------------- | ------------------------------- |
| char       | 0-255字节           | 定长字符串                      |
| varchar    | 0-65535 字节        | 变长字符串                      |
| tinyblob   | 0-255字节           | 不超过 255 个字符的二进制字符串 |
| tinytext   | 0-255字节           | 短文本字符串                    |
| blob       | 0-65 535字节        | 二进制形式的长文本数据          |
| text       | 0-65 535字节        | 长文本数据                      |
| mediumblob | 0-16 777 215字节    | 二进制形式的中等长度文本数据    |
| mediumtext | 0-16 777 215字节    | 中等长度文本数据                |
| longblob   | 0-4 294 967 295字节 | 二进制形式的极大文本数据        |
| longtext   | 0-4 294 967 295字节 | 极大文本数据                    |

```mysql
char 定长存储 : 一般存定长 如 :手机号,身份证号,用户名(弹性不大)
	0-255  存储速度快 占用空间较大
varchar 变长存储 : 存储评论
	0-65535 储存速度慢 ,占用空间小
	
# 时间和空间
    # 时间换空间
    # 空间换时间

```

### d. enum 和 set类型

```mysql
enum中文名称叫枚举类型，它的值范围需要在创建表时通过枚举方式显示。enum只允许从值集合中选取单个值，而不能一次取多个值。

```

```mysql
set和enum非常相似，也是一个字符串对象，里面可以包含0-64个成员。根据成员的不同，存储上也有所不同。set类型可以允许值集合中任意选择1或多个元素进行组合。对超出范围的内容将不允许注入，而对重复的值将进行自动去重。

```

| 类型 | 大小                                                         | 用途           |
| ---- | ------------------------------------------------------------ | -------------- |
| enum | 对1-255个成员的枚举需要1个字节存储;对于255-65535个成员，需要2个字节存储;最多允许65535个成员。 | 单选：选择性别 |
| set  | 1-8个成员的集合，占1个字节9-16个成员的集合，占2个字节17-24个成员的集合，占3个字节25-32个成员的集合，占4个字节33-64个成员的集合，占8个字节 | 多选：兴趣爱好 |

```mysql
单选 : enum() # 只能从给出的有限的条件中选择
create table enum_t(sex enum('男','女')) # 如果写入其他的结果是空

多选 : set() 从有限的条件选多个,去重
creat table set_t(hobby set('抽烟','喝酒','烫头'));
insert into set_t values('烫头,喝酒') # 自动去重,选其他则是空

```

# 6. 表的约束

## 1. not null 非空约束 和default默认值

```mysql
create table t1(
	id int not null, 非空约束(不能为空,空就报错)# 严格模式的设置,在my.ini添加一行语句
	name char(12),
	age tinyint unsigned not null default 18 # 不能为空,但是有默认值为18
	)

```

```mysql
设置严格模式：
    不支持对not null字段插入null值
    不支持对自增长字段插入”值
    不支持text字段有默认值

直接在mysql中生效(重启失效):
mysql>set sql_mode="STRICT_TRANS_TABLES,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION";

配置文件添加(永久失效)：
sql-mode="STRICT_TRANS_TABLES,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION"

not null不生效


停止：net stop mysql
（其中mysql为你安装的mysql服务名称）

启动：net start mysql

```



## 2. unique 唯一约束  -  不能重复

```mysql
create table t1(
	id int unique,
	username char(18) unique,
	age tinyint unsigned
	);
	再次写入相同的会报错

```

## 3. 非空+唯一

```mysql
create table t1(
	id int not null unique,
	username char(18) unique,
	age tinyint unsigned
	);
	# 如果一张表中没有设置primary key 主键,那么第一个设置非空+唯一的字段会被设置成主键
	# 一张表中只有一个主键
	# 主键的效果就是非空+唯一
	# 一般ID作为主键(开头的默认主键)
	# primary key 设置主键
	
	    create table t5(
        id int primary key,
        username  char(18) not null unique,
        age tinyint unsigned
    );

```



------



# 7.  约束和表关系

## A.  约束

```mysql
unsigned  # 建表时,必须放在首位 只能约束int-无符号
	
not null # 非空约束
	
default #  设置默认值 直接在其后面放默认值
	
unique # 唯一;联合唯一
	
auto_increment # 自增(针对int) 自带not null 需要设置unique
			# 被auto_increment修饰的列为标识列，可以自动增长。一张表中只能有一个标识列
			# auto_increment只能用来修饰数值类型的列，并且该类型的列列只能为key类型的列，key类型的列有：				primary key 、unique、key、foreign key
			# 当为数据库表中插入新纪录时，字段上的值会自动生成唯一的ID,并且再次插入新数据,这个新数据自增
			# 删除某一数据后,唯一的ID不会消失
	
primary key # 主键 相当于非空+唯一   一张表中只能有一个,且必须有
			设置主键:
			alter table 表名 add primary key(需要设置主键的字段名);
	
foreign key # 外键约束
		   # 约束字段至少 unique
		   # 联级删除 on delete cascade
		   # 联机更新 on update cascade
	级联更新和级联删除 :
	create table test1(
    	id int primary key auto_increment,
    	cid int,
		foreign key(cid) references test2(id) on delete cascade on update cascade
	);  # 将表test1中的cid字段与 表test2中的id 进行联机更新和联级删除
		# 由于是表test1中的某字段关联表test2中的某字段,所有,必须先有test2,也就是是必须先创建test2
		# 插入数据同样必须同行中先有test2的数据,才能插入咋同行中插入test1数据
		#修改数据只能修改test2中的数据,test1的数据会同步,
```



```mysql
show databases;  # 查看共有多少库
select database(); #  查看当前所在的库
```

```mysql
unique约束 可以插入多个null
对于mysql来说,数据与数据之间的相等就是重复
但是null不能用 = 判断 重复 二用 is / not is
```

```mysql
清空表 :
delete from 表名 # 如果有自增id,新增的数据,仍然是以删除以前的最后数据作为起始
truncate table 表名 # 数据量大,删除速度比上一条块,却直接从零开始,(初始化表)
```



```mysql
联合唯一:
create table t2(
    id int primary key,
    servername char(12) not null,
    ip char(15),
    port int,
    unique(ip,port) # 联合唯一
```

```mysql
auto_increment 自增:
	1.只能操作int
	2.自带非空属性
	3.只能对unique 字段设置 (唯一)
	4.不受删除影响 (添加的id会记录下来,再次添加会延续下一位,删除数据后,再次添加也会延续那条删除的数据)
create table t1(
	id int unique auto_increment
	name char(12) not null
)
```

```mysql
设置主键: 一张表只能有一个主键
primary key

联合主键:
creat table t1(
	family_name char(4),
    name char(4),
	primary key(family_name, name) # 联合主键    key PRI
)
```

外键级联 :

```mysql
外键约束 : 对应表中的字段至少是unique的,推荐使用主键作为关联字段
```

```mysql
级联更新和级联删除 :
create table test1(
    id int primary key auto_increment,
    cid int,
	foreign key(cid) references test2id) on delete cascade on update cascade
);   # 只允许被关联的字段数据删除和修,操作后,本字段会同步更新

	foreign key(cid) references test2(id) # 这个不允许删除和修改,否则报错

```

```mysql
# 数据的插入操作
将已有表格class的数据全部插入到新到的表格class1中
insert into class1 select * from class;

将已有数据表格class中的部分数据插入到class表格中
insert into class1(id,name) select id,cname from class;

正常插入数据:
insert into 表名 values(字段数据,字段数据,...);

```

```mysql
update class set id=1 where id =2;
将id=2修改为id=1

```



## B.  表与表之间的关系

1. 一对多 :

   ```
   多的一方表创建foreign key 关联一的字段
   
   ```

2. 多对多

3. 一对一

   ```mysql
   一对多  foreign key
   多对多  出现第三张表 :有两个foreign key
   一对一  foreign + unique
   
   ```

   

# 8.  数据的增删改



# 9.  单表查询

```mysql
调用函数 : now() user() database() concat() concat_ws()

```

## 1. select - 查询显示

```mysql
select 字段名 from 表名   # 查多个字段用逗号隔开
select * from 表名 # 查整个表
select user()  # 查询当前用户
select database() # 查询当前所在库
select now()  # 查询当前时间

select distinct  字段名 from 表名 ;  # 去重查
select distinct  字段名,字段名 from 表名 ;  # 多个字段去重查
select 字段名 新名字 from 表名 ;  # 重命名
select 字段名 新名字,字段名 新名字 from 表名 ;  # 重命名
select 字段名 as 新名字 from 表名 ;  # 重命名

select concat('要添加的字符串','要添加的字符串',...原字段名) from 表名
select concat('要添加的字符串','要添加的字符串',...原字段名)自定义显示表头 from 表名
select concat('要添加的字符串','要添加的字符串',...原字段名)as 自定义显示表头 from 表名

select concat_ws('要添加的字符串','要添加的字符串',...原字段名) from 表名
select concat_ws('要添加的字符串','要添加的字符串',...原字段名) 自定义字显示表头 from 表名
select concat_ws('要添加的字符串','要添加的字符串',...原字段名) as 自定义显示表头 from 表名

```

```mysql
运算:
select 字段名*12 from 表名 ;  # 可以四则运算(年薪等.)

```

**case语句**

```mysql
结构 :
select(
	case
	when 字段名条件 then
		修改后的数据
	when 字段名条件 then
		修改后的数据
	...
	else
		数据
	end # 结束语句
	)as new_name #自定义表头名
from 表名;


select(
    case
    when emp_name = 'alex' then  # 判断语句
        concat(emp_name,'BIGSB')
    when emp_name = 'jingliyang' then
        emp_name
    else
        concat(emp_name,'sb')
    end # 结束语句
    ) as new_name # 自定表头名
from employee;    

```

## **2. where**

**where 筛选行**

```mysql
select * from 表名 where 条件

范围查询
> < >= <= =     不等于: !=  /<> 

between a and b   # 包含a,b
select emp_name,age,salary from employee where post='teacher' and salary between 9000 and 10000;

in (1,2,3,4) # n选1
not in
select emp_name,age,salary from employee where post='teacher' and salary not in (10000,9000,30000);

```

```mysql
like 模糊查询
'a%' 以a开头
'%a' 以a结尾
'%a%' 包含a的
select emp_name,salary*12 from employee where post='teacher' and emp_name like 'jin%';


下划线 
'a_'一个下划线代表只一个任意字符
'_a'
select emp_name from employee where emp_name like '程__';

regexp  # mysql正则
'^a'  # 以a结尾
'\d+''

```

```mysql
is , is not # is null ; is not null
逻辑运算符：在多个条件直接可以使用逻辑运算符 and or not

```

## 3. **group by**   分组

```mysql
数据

insert into employee(emp_name,sex,age,hire_date,post,salary,office,depart_id) values
('egon','male',18,'20170301','老男孩驻沙河办事处外交大使',7300.33,401,1), #以下是教学部
('alex','male',78,'20150302','teacher',1000000.31,401,1),
('wupeiqi','male',81,'20130305','teacher',8300,401,1),
('yuanhao','male',73,'20140701','teacher',3500,401,1),
('liwenzhou','male',28,'20121101','teacher',2100,401,1),
('jingliyang','female',18,'20110211','teacher',9000,401,1),
('jinxin','male',18,'19000301','teacher',30000,401,1),
('成龙','male',48,'20101111','teacher',10000,401,1),

('歪歪','female',48,'20150311','sale',3000.13,402,2),#以下是销售部门
('丫丫','female',38,'20101101','sale',2000.35,402,2),
('丁丁','female',18,'20110312','sale',1000.37,402,2),
('星星','female',18,'20160513','sale',3000.29,402,2),
('格格','female',28,'20170127','sale',4000.33,402,2),

('张野','male',28,'20160311','operation',10000.13,403,3), #以下是运营部门
('程咬金','male',18,'19970312','operation',20000,403,3),
('程咬银','female',18,'20130311','operation',19000,403,3),
('程咬铜','male',18,'20150411','operation',18000,403,3),
('程咬铁','female',18,'20140512','operation',17000,403,3)
;

```

```mysql
单独使用group by关键字分组
select 字段名 from 表名 group by 字段名(前后一致); # 1.根据分组字段自动去重 2.其他重复项目不在结果中显示
select post from employee group by post;
注意：我们按照post字段分组，那么select查询的字段只能是post，想要获取组内的其他相关信息，需要借助函数

group by关键字和 group_concat() 函数一起使用 #  group_concat()只能作为最终结果显示
select post,group_concat(emp_name) from employee group by post;#按照岗位分组，并查看组内成员名
select post,group_concat(emp_name) as emp_members from employee group by post;

group by与聚合函数 count()一起使用
select post,count(id) as count from employee group by post;#按照岗位分组，并查看每个组有多少人

```

```mysql
count() # 计数
avg() # 平均数
max() # 最大值
min() # 最小值
sum() # 总和

```



------



# 10. 单表查询

```mysql
select # 想要的列 from 表
where # 先从这张表中查询的行
group by #分组
having # 对组过滤
order by # 排序
limit #取一个区间

执行顺序:
from → where → group by → having → order by → select → limit 
  1      2       3       4         5         6        7
```

## A . 分组

```mysql
分组 group by
1. 根据某个重复率比较高的字段进行的
2. 这个字段有多少种可能就分成多少组
3. 可以去重
4. 一旦分组了,就不能对具体的某一条数据进行操作了
select 字段名 from group by 字段名(前后一致)
```

## B. 聚合函数 - 不能用在where后面

```mysql
如果没有和分组一起使用,默认这整张表是一组
count()  # 计数 每个组对应几条数据
max()  # 这个组的某个字段数据的最大值
min() #最小值
avg() #平均值
sum() # 总和

select 字段名1,avg(需要求的字段) from 表名 group by 字段名1;
```

## C. 过滤条件

```mysql
having 过滤条件
对组进行筛选条件
先分组,再用having筛选数据
select post from employee group by post having count(id)>3;

select 筛选字段,字段 from 表 having 筛选字段条件
select  字段 from 表 group by 筛选字段 having 筛选字段条件
```

## D. order by

```mysql
order by 默认升序 asc  降序 desc

order by 字段1,字段2
order by 字段 asc,字段2 desc
order by 字段 desc,字段2 asc
order by 字段 desc,字段2 desc

select * from 表名 order by 需要排序的字段
select * from 表名 order by 需要排序的字段 asc

select * from 表名 order by 需要排序的字段1,需要排序的字段2
```

## E .limit 限制查询

```mysql
limit 限制
	1.显示分页 limit m,n 从m+1开始取n条 # 取的时候,读了全部数据,数据多的时候慢
	2.取前n名 (总是跟 order by 一起用)
	3.limit n offset m ;从m+1开始,取n条

select * from 表名 order by 字段名 limit 3; #从小到大排序取前三显示
select * from 表名 order by 字段名 limit 2,10; #从第3条开始取,去10条
```

```mysql
## 8.找出出版图书均价最高的价格   也可以有下面的书写方式
select max(db.avg_price) from (select avg(价格) as avg_price from book group by 作者) as db
```



# 11.  数据操作

## a 表操作

```mysql
创建 create table 表名(字段名 类型(宽度) 约束, 字段名 类型(宽度) 约束  ...);  # 创建一个表

删除 drop table 表名 # 删除一个表
	alter table 表名 drop 字段名 # 删除一个字段
	
查看 desc 表名 查表结构    show create table #查创表语句

修改 :
	alter table 旧表名 rename 新表名  # 修改表名

	alter table 表名 add 新字段 类型(宽度) 约束  # 添加新字段
	alter table 表名 add 新字段 类型(宽度) 约束 after 已有字段名  # 在已有字段后添加新字段
	alter table 表名 add 新字段 类型(宽度) 约束 first  # 在第一位字段添加字段

	修改字段的名称类型:
	alter table 表名 modify 字段名 类型 约束
	alter table 表名 modify 字段名 类型 约束 after 字段 # 修改位置
	alter table 表名 change 字段名 字段名 类型 约束# (特别) 
	修改字段的名称:
	alter table 表名 change 旧字段名 新字段名 类型 约束 
	alter table 表名 change 旧字段名 新字段名 类型 约束 after 字段 # 修改位置
```

## b. 数据操作

### 1. 增加

```mysql
增加 :
insert into 表名 value(数据) # 只能添加一条数据
insert into 表名 values(数据...)
insert into 表名(字段1,字段2) values(对应数据1,对应数据2)  # 给单独的字段添加数据(其他字段约束为null的时候)
insert into 表1(字段1,字段2) select (字段3,字段4) from 表2 # 给表1的字段1,字段2 添加表2的字段3,字段4的数据

```



### 2. 删除

```mysql
delete from 表名 where 条件
delete from 表名 where id=1

```



### 3. 修改

```mysql
update 表名 set 字段=值 where 条件
update 表名 set 字段1=值1,字段2=值2...where 条件
update 表名 set 字段1=值1,字段2=值2...where id=1

```

### 4. 查表数据 (单表查)

```mysql
select 字段名 from 表名   # 查多个字段用逗号隔开
select * from 表名 # 查整个表
select user()  # 查询当前用户
select database() # 查询当前所在库
select now()  # 查询当前时间

select distinct  字段名 from 表名 ;  # 去重查
select distinct  字段名,字段名 from 表名 ;  # 多个字段去重查
select 字段名 新名字 from 表名 ;  # 重命名
select 字段名 新名字,字段名 新名字 from 表名 ;  # 重命名
select 字段名 as 新名字 from 表名 ;  # 重命名


拼接字符:
select concat('要添加的字符串','要添加的字符串',...原字段名) from 表名
select concat('要添加的字符串','要添加的字符串',...原字段名)自定义显示表头 from 表名
select concat('要添加的字符串','要添加的字符串',...原字段名)as 自定义显示表头 from 表名

select concat_ws('要添加的字符串','要添加的字符串',...原字段名) from 表名
select concat_ws('要添加的字符串','要添加的字符串',...原字段名) 自定义字显示表头 from 表名
select concat_ws('要添加的字符串','要添加的字符串',...原字段名) as 自定义显示表头 from 表名

```



# 12. python操作数据库

```python
#sql注入
#查询
import pymysql
conn = pymysql.Connection(host='127.0.0.1', user='root', password="123",
                 database='day40')
cur = conn.cursor()  # 游标 数据库操作符
sql = 'select emp_name,salary from employee where age = %s'  # mysql语句
cur.execute(sql,(80,))  # 拼字符串

# 获取结果
ret1 = cur.fetchone()  # 查一条数据
ret2 = cur.fetchmany(2) # 查定条数据
ret3 = cur.fetchall()  # 查所有数据
print(ret1) # 以元组形式打印出来
print(ret2) # 取数据时会有记录,下次再取就是下一个(next)
print(ret3)
cur.close() # 关闭游标
conn.close()  # 关闭连接

insert语句 写入
import pymysql
conn = pymysql.Connection(host='127.0.0.1', user='root', password="123",
                 database='day40')
cur = conn.cursor()  # 游标 数据库操作符
username = '太亮'
sql = 'insert into employee(id,emp_name,sex,age,hire_date) values(%s,%s,"female",88,20170707)'
cur.execute(sql,(21,username,)) # 元组形式
conn.commit()  # 提交,不提交数据无法写进数据库
cur.close()
conn.close()

```

```python
文件操作数据库
conn = pymysql.Connection(host='127.0.0.1', user='root', password="123",
               database='day40')
cur = conn.cursor()  # 游标 数据库操作符
cur.excute(sql,(值1,))
查询
fetchone 
fethmany(10) 
fetchaLL
    插入\更新\删除
        conn.commit()
cur.close()
conn.close()

```

------



# 13. 多表查询 

## 连表查询

### A. 笛卡尔积

先计算两张表的笛卡尔积,再根据用户给出的条件进行筛选

### **B. 内连接 inner join**

```
内连接 - 只显示两张表中互相匹配上的项
```

```mysql
select * from 表1 inner join 表2 on 连接条件
select * from 表1 inner join 表2 on dep_id = department.id
select * from 表1 inner join 表2 on dep_id = department.id 条件
```

### **C. 外连接**

```mysql
左外连接 select * from 表1 left join 表2 on 连接条件 # 谁在左边全部显示谁
右外连接 select * from 表1 right join 表2 on 连接条件 # 谁在右边全部显示谁

全外连接:
select * from 表1 left join 表2 on 连接条件
union
select * from 表1 right join 表2 on 连接条件
```

## **子查询 - 嵌套查询** 

```mysql
select * from department where id in (select distinct dep_id from employee where age>25);
```

```mysql
子查询处理可以放在条件中,还可以放在连表中,还可以放在select字段(要求查询的结果必须是一个单行单列的值)中.
```

```mysql
推荐连表 : 连表的效率比子查询的效率要高
```

```mysql
select 语句到底做了什么?
    select name from emp;
    select name as n,(select age from employee where name = n) from emp;
```



```mysql
select * from 表 where 字段 > 一个值
如果我们查询出来的结果是一个值,那么就可以使用 >  <  =
select * from 表 where 字段 in (1个值,1个值)
如果我们查询出来的结果是一列中的多个值
        # dep_id
        # 201
        # 202
        # 204
如果我们查出来的是一张表,也不能作为条件,如果必须保留这两个字段,就不能用作条件,只能连表
    # id name
    # 1  alex
```

# 14. 导入init到mysql

```mysql
把写好的init文件导入到mysql流程:
1. 指定库:
	a.先创建一个库: create database 库名
	b.use 库名 ,切换到这个库
2. 导入数据:
	source init路径
	

```





------



# 15. 索引原理

平衡树 - balance tree    btree

```mysq
b+树 (平衡树):
	1.数据只储存在叶子节点
	2.在子节点之间加入了双向地址连接,更方便的在子节点之间进行数据的读取
	
根节点 root
分支节点 branch
叶子节点 leaf
```

## **a. innodb索引**

```mysql
# 聚集索引 : 
		直接把整行数据写在叶子节点上
		 只有一个聚集索引,以主键字段作为索引列
# 辅助索引 : 
		创建的索引列的数据储存在树形结构的叶子节点上
		存储的内容 : 索引列+id列
# 回表 : 
		只查询一个索引并不能解决查询中的问题,还需要到具体的表中去获取整行数据

```

## **b. myisam索引**

```mysql
# 辅助索引 :  myisam中只有一个辅助索引
		创建的索引列的数据储存在树形结构的叶子节点上
		存储的内容 : 索引列+id列
# 哈希索引
```

# 16. 索引的种类

```mysql
    1. priamry key 的创建自带索引效果       非空 + 唯一 + 聚集索引
    2. unique 唯一约束的创建也自带索引效果   唯一 + 辅助索引
    3. index  普通的索引                   辅助索引

```

# 17. 创建索引

```mysql
创建索引 :
create index  自定义索引的名字 on 表名(索引的字段)
删除索引 :
drop index 自定义索引的名字 on 表名
```

索引的优缺点

```mysql
优点 : 查找速度快
缺点 : 浪费空间,拖慢写数据的速度
	不要在程序中创建无用的索引
```



# 18. 索引的正确使用

```mysql
1. 查询的列不是创建索引的列(没命中)
2. 在条件中不能带有运算,函数(没命中)
3. 如果创建索引的列的内容重复率过高,也不能有效利用索引
	# 重复率不超过10%的列比较适合做索引
4. 如果数据对应的范围过大,也不能有效利用索引
	# between and > < >= <= != not in
5. like 如果把%放在最前面也不能命中索引
6. 多条件下的情况
	 	and 只要有一个条件列是索引列就可以命中索引
   		or  只有所有的条件列都是索引才能命中索引
7. 联合索引
	创建联合索引 :
		create index  自定义索引的名字 on 表名(索引的字段1,索引的字段2)
	在多个条件相连的情况下,使用联合索引的效率要高于使用单字段的索引
	1. 创建索引的顺序id,email 条件中从哪一个字段开始出现了范围,索引就失效了
	2. 联合索引在使用的时候遵循最左前缀原则 :
		查询的时候必须出现最左面的索引的字段才会命中索引
	3. 联合索引中只有使用and能生效,使用or失效
8.字段 能够尽量的固定长度 就用固定长度
```

mysql 神奇 explain

```mysql
explain select 查看sql语句的执行计划 是否命中了所用,命中的索引的类型
```

覆盖索引 using index

```mysql

```

索引合并

```mysql
创建的时候是分开创建的,用的时候临时和在一起了
using union 表示索引合并

```

慢查询优化

```mysql
知道mysql可以开启慢日志
慢日志是通过配置文件开启

```

```mysql
# 7表联查速度慢怎么办?
    1.表结构
        a.尽量用固定长度的数据类型代替可变长数据类型
        b.把固定长度的字段放在前面
    2.数据的角度上来说
        如果表中的数据越多 查询效率越慢
            a. 列多 : 垂直分表
            b. 行多 : 水平分表
    3.从sql的角度来说
        1. 尽量把条件写的细致点儿 where条件多做筛选
        2. 多表的时候尽量连表代替子查询
        3. 创建有效的索引,而规避无效的索引
    4.配置角度上来说
        开启慢日志查询 确认具体的有问题的sql
    5.数据库
        读写分离 : 解决数据库读的瓶颈

```



# 19. 数据库的导入/导出

```mysql
备份数据 : 
mysqldump -u root -p密码 库名 > 备份的文件路径
还原数据:
sourse 还原的文件路径

# 备份表 :homwork库中的所有表和数据
        # mysqldump -uroot -p123 homework > D:\s23\day42\a.sql
        # 备份单表
        # mysqldump -uroot -p123 homework course > D:\s23\day42\a.sql
# 备份库 :
        # mysqldump -uroot -p123 --databases homework > D:\s23\day42\db.sql

# 恢复数据:
#方法一：
[root@egon backup]# mysql -uroot -p123 < /backup/all.sql

#方法二：
mysql> use db1;
mysql> SET SQL_LOG_BIN=0;   #关闭二进制日志，只对当前session生效
mysql> source /root/db1.sql

```



# 20. 如何开启事物,给数据加锁

```mysql
begin;
select id from t1 where name = 'alex' for update;
update t1 set id = 2 where name = 'alex';
commit;

```

# 21. sql注入

```python
import pymysql

conn = pymysql.connect(host='127.0.0.1', user='root', password="123",
                 database='day43')
cur = conn.cursor()
user = "akhksh' or 1=1 ;-- "
password = '*******'
sql = "select * from userinfo where username = %s and password =%s;"
print(sql)
cur.execute(sql,(user,password))
ret = cur.fetchone()
print(ret)
cur.close()
conn.close()
```

