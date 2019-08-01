# Python的基础认知

## 1. 计算机基础知识

- cpu :      人类的大脑,思考 运算和处理问题       
- 内存 :       临时储存数据   断电即消失       存储速度快  4G 8G 16G 32G
- 硬盘 :       永久存储数据   存储图片,视频,音频    相对于内存存储慢    500G   1T  2T
- 操作系统 :       其实是一个软件,去控制每个硬件之间的数据交互

## 2. Python的应用和历史

1. python的创始人为吉多·范罗苏姆（Guido van Rossum）。1989年的圣诞节期间，吉多·范罗苏姆（中文名字：龟叔）为了在阿姆斯特丹打发时间，决心开发一个新的脚本解释程序，作为ABC语言的一种继承。（龟叔：2005年加入谷歌至2012年，2013年加入Dropbox直到现在，依然掌握着Python发展的核心方向，被称为仁慈的独裁者）。
2. 目前Python主要应用领域：
   - **云计算**: 云计算最火的语言， 典型应用OpenStack
   - **WEB开发**: 众多优秀的WEB框架，众多大型网站均为Python开发，Youtube, Dropbox, 豆瓣。。。， 典型WEB框架有Django
   - **科学运算、人工智能**: 典型库NumPy, SciPy, Matplotlib, Enthought librarys,pandas
   - **系统运维**: 运维人员必备语言
   - **爬虫**:通过代码来模拟人类访问网页,选择有用信息进行下载
   - **金融**：量化交易，金融分析，在金融工程领域，Python不但在用，且用的最多，而且重要性逐年提高。原因：作为动态语言的Python，语言结构清晰简单，库丰富，成熟稳定，科学计算和统计分析都很牛逼，生产效率远远高于c,c++,java,尤其擅长策略回测
   - **图形GUI**: PyQT, WxPython,TkInter
   - 游戏
3. Python在一些公司的应用：
   - 谷歌：Google App Engine 、code.google.com 、Google earth 、谷歌爬虫、Google广告等项目都在大量使用Python开发
   - CIA: 美国中情局网站就是用Python开发的
   - NASA: 美国航天局(NASA)大量使用Python进行数据分析和运算
   - YouTube:世界上最大的视频网站YouTube就是用Python开发的
   - Dropbox:美国最大的在线云存储网站，全部用Python实现，每天网站处理10亿个文件的上传和下载
   - Instagram:美国最大的图片分享社交网站，每天超过3千万张照片被分享，全部用python开发
   - Facebook:大量的基础库均通过Python实现的
   - Redhat: 世界上最流行的Linux发行版本中的yum包管理工具就是用python开发的
   - 豆瓣: 公司几乎所有的业务均是通过Python开发的
   - 知乎: 国内最大的问答社区，通过Python开发(国外Quora)
   - 春雨医生：国内知名的在线医疗网站是用Python开发的
   - 除上面之外，还有搜狐、金山、腾讯、盛大、网易、百度、阿里、淘宝 、土豆、新浪、果壳等公司都在使用Python完成各种各样的任务。
4. Python 版本 :
   - Python 2.+    ： C , Java ，C#      源码不统一，功能重复 维护难度大
   - Python 3.+    ：代码统一，代码（功能）重复    维护难度降低

## 3. Python是一门什么语言

1. 编译型  ： 从头到尾只编译一次      
   - 优点 ：运行速度快
   - 缺点 ： 开发速度慢
   - 代表语言 ：   C C++  Go
2. 解释型   ：一句一句编译   逐行编译   
   - 优点 ： 开发效率高
   - 缺点 ： 运行速度慢
   - 代表语言 ： Python   Ruby  PHP

## 4. Python的优缺点

1. 优点 ： 

   - Python的定位是“优雅”、“明确”、“简单”，所以Python程序看上去总是简单易懂，初学者学Python，不但入门容易，而且将来深入下去，可以编写那些非常非常复杂的程序。
   - 开发效率非常高，Python有非常强大的第三方库，基本上你想通过计算机实现任何功能，Python官方库里都有相应的模块进行支持，直接下载调用后，在基础库的基础上再进行开发，大大降低开发周期，避免重复造轮子。
   - 高级语言————当你用Python语言编写程序的时候，你无需考虑诸如如何管理你的程序使用的内存一类的底层细节
   - 可移植性————由于它的开源本质，Python已经被移植在许多平台上（经过改动使它能够工 作在不同平台上）。如果你小心地避免使用依赖于系统的特性，那么你的所有Python程序无需修改就几乎可以在市场上所有的系统平台上运行
   - 可扩展性————如果你需要你的一段关键代码运行得更快或者希望某些算法不公开，你可以把你的部分程序用C或C++编写，然后在你的Python程序中使用它们。
   - 可嵌入性————你可以把Python嵌入你的C/C++程序，从而向你的程序用户提供脚本功能。

2. 缺点 ： 

   - 速度慢，Python 的运行速度相比C语言确实慢很多，跟JAVA相比也要慢一些，因此这也是很多所谓的大牛不屑于使用Python的主要原因，但其实这里所指的运行速度慢在大多数情况下用户是无法直接感知到的，必须借助测试工具才能体现出来，比如你用C运一个程序花了0.01s,用Python是0.1s,这样C语言直接比Python快了10倍,算是非常夸张了，但是你是无法直接通过肉眼感知的，因为一个正常人所能感知的时间最小单位是0.15-0.4s左右，哈哈。其实在大多数情况下Python已经完全可以满足你对程序速度的要求，除非你要写对速度要求极高的搜索引擎等，这种情况下，当然还是建议你用C去实现的。
   - 代码不能加密，因为PYTHON是解释性语言，它的源码都是以名文形式存放的，不过我不认为这算是一个缺点，如果你的项目要求源代码必须是加密的，那你一开始就不应该用Python来去实现。
   - 线程不能利用多CPU问题，这是Python被人诟病最多的一个缺点，GIL即全局解释器锁（Global Interpreter Lock），是[计算机程序设计语言](http://zh.wikipedia.org/wiki/计算机程序设计语言)[解释器](http://zh.wikipedia.org/wiki/解释器)用于[同步](http://zh.wikipedia.org/wiki/同步)[线程](http://zh.wikipedia.org/wiki/线程)的工具，使得任何时刻仅有一个线程在执行，Python的线程是操作系统的原生线程。在Linux上为pthread，在Windows上为Win thread，完全由操作系统调度线程的执行。一个python解释器进程内有一条主线程，以及多条用户程序的执行线程。即使在多核CPU平台上，由于GIL的存在，所以禁止多线程的并行执行。关于这个问题的折衷解决方法，我们在以后线程和进程章节里再进行详细探讨。

   当我们编写Python代码时，我们得到的是一个包含Python代码的以`.py`为扩展名的文本文件。要运行代码，就需要Python解释器去执行`.py`文件。

   由于整个Python语言从规范到解释器都是开源的，所以理论上，只要水平够高，任何人都可以编写Python解释器来执行Python代码（当然难度很大）。事实上，确实存在多种Python解释器。

   

## 5. Python的种类

1. Cpyhon  : CPython。这个解释器是用C语言开发的，所以叫CPython。

2. Jython  :  Jython是运行在Java平台上的Python解释器，可以直接把Python代码编译成Java字节码执行。

3. IronPyhon   IronPython和Jython类似，只不过IronPython是运行在微软.Net平台上的Python解释器，可以直接把Python代码编译成.Net的字节码。

4. PyPy  : PyPy是另一个Python解释器，它的目标是执行速度。PyPy采用[JIT技术](http://en.wikipedia.org/wiki/Just-in-time_compilation)，对Python代码进行动态编译（注意不是解释），所以可以显著提高Python代码的执行速度。

   

# Python基础知识

## 1. Python的安装和环境配置



## 2. 第一个Python程序

​	print()   打印    打印到屏幕       print("hello world")

## 3. 变量

定义变量的规则 :

  1. **字母,数字,下划线组成**

  2. **不能数字开头**

  3. **不能用python中的关键字**

  4. 不建议使用中文或拼音

  5. 命名要有意义

  6. 区分大小写

  7. 推荐写法

     ​	驼峰体 : (首字母大写) : ZhangYiDong

     ​	下划线 :( 官方推荐 ) : zhang_yi_dong 

## 4.常量

为了迎合其他的编程语言,,Python语言中, 变量名中全部大写定为常量

## 5. 注释

作用 : 给一些繁琐的代码加一些描述,加强代码的可读性

两种注释方法 :  >>>注释后的代码不能运行

​			**单行注释** : #    只能注释一行,不能换行注释	

​			**多行注释** : '''  '''    支持多行注释	

## 6. 基础数据类型初识

1. 整型 : 数字     关键字 int

2. 字符串 :汉字,字母等    关键字 str    **Python中只要用引号引起来的就是字符串** 字符串可以用"+"拼接  

   - 字符串 + 都是字符串的时候才能相加
   - 字符串* 字符串只能和数字相乘

3. 布尔值 :  (首字母大写)

   - True : 真      1
   - False : 假     0

4. 列表   list[]

5. 元组   tuple()

6. 字典   dict{"key":"value"}

7. 集合    set{}

8. 用户输入input

   - input ("提示信息")  用户输入内容全部是字符串

   - ```python
     用户输入密码不可见 :
     import getpass
     user = input ("请输入用户名:")
     pwd = getpass.getpass("请输入密码:")
     print(user,pwd)
     ```

9. 流程控制语句 if

   - ```python
     if   条件:    #条件判断 > < ==  
      	print()   #条件成立后执行的事情
     else :
     	执行的活动事件    上条条件不成立后要执行的事件
     ```

   - ```python
     if elif  elif elif   按顺序执行,只要成立,就结束不再往下运行
     ```

   - ```python
     if  if  if  if 只要if成立就执行   一直成立一直执行
     ```

   - ```python
     if 的嵌套 ...............
     ```

## 7. 字符串的格式化输出

```python
# %s -- 占字符串的位置
# %d -- 占整型的位置
# %% -- 转义（把占位转换成普通的%号)
```

```python
msg = '''
------------------- info ----------------------
姓名: %s
年龄:  %s
性别 : %s
职业:  %s
爱好: %s
------------------- end ------------------------
'''
name = input("请输入你的名字:")
age = input("请输入你的年龄:")
sex = input("请输入你的性别:")
job = input("请输入你的工作:")
hobby = input("请输入你的爱好:")
print(msg%(name,age,sex,job,hobby))
```

```python
f"{}变量名" 在Python3.6版本中才能实现
msg = f'''
------------------- info ----------------------
name: {input("请输入您的名字:")}
age:  {input("请输入您的年龄:")}
sex : {input("请输入您的性别:")}
job:  {input("请输入您的职业:")}
hobby: {input("请输入您的爱好:")}
------------------- end ------------------------
'''
print(msg)
```

## 8. while循环

- ```python
  while True:   # while 是关键字  条件
  ```

- ```python
  while true :
  		print("内容")
  		break  #  终止当前循环
  		continue # 跳出本次循环,继续执行下一次循环 (理解为伪装成循环体代码最后一行,
  					不再执行下一行的print,直接跳转到开头再次循环)
  		print("内容")
  ```

- ```python
  while 条件 :
  	print("n内容")
  else :
  	print("内容")
  ```

  

## 9. 运算符

- ```python
  # 赋值运算
  	a = 1
  	a +=1      # a = a+1
  	a -= 1     # a = a-1
      a  * = 1   # a = a * 1
      a / = 1    # a = a / 1
      a ** = 1   # a = a**1
      a % =1     # a = a % 1
  ```

- ```python
  # 算数运算 :
  +-*/  # 加减乘除
  **   #幂
  //   #取整除    #   例: 9//4 输出结果为4
  % #取余数 (模)
  ```

- ```python
  # 逻辑运算 :
  # amd(与) :
  	#1 and 2         >> and两边都是真结果真 , 有一个假结果为假
      #1 and 2         >> and两边都是假的时候 , 结果取 and 后面的内容
      #0 and False  >> and 两边都是假的时候,结果取 and 前面的内容
  # or(或) :
  	#1 or 0         >> or  只要有一个是真的,结果就是真    全假结果才为假
      #1 or 4           >> or 两边都是真的时候,结果取 or 前面的内容  (和and相反)
      #False  or 0   >> or 两边都是假的时候,结果取 or 后面的内容 (和and相反)
  # not(非) :
  #计算优先顺序 :
  	()  >   not   >   and   >   or  
  ```

- ```python
  # 成员运算 :
  # in在	   not in 不在
  s = "123456"
  if "123"  in s :
  	print("内容")
      
  s = "123456"
  print("456" not in s )  
  ```

- ```python
  # 比较运算 :
  #   ==  等于
  #   !=  不等于
  #   >  大于
  #   <  小于
  #   >=  大于等于
  #   <=  小于等于
  ```

- ```python
  # 身份运算 :
  # is  是            
  # is not  不是 
  # is  判断是不是同一个东西    (从源头判断)
  # ==   判断表面上是不是同一个东西
  ```

## 10. 初识编码

- ASCII   英文1个字节  只支持英文

- GBK  -- 国标

  - 英文1个字节
  - 中文2个字节

- Unicode  万国码

  - 英文两个字节
  - 中文四个字节

- UTF-8  目前最流行的编码

  - 英文1个字节
  - 欧洲2个字节
  - 亚洲3个字节

- UTF-16 

  - 最少用2个字节

- 单位转换

  - ```python
    8bit=1byte
    1024byte=1KB
    1024KB=1MB
    1024MB=1GB
    1024GB=1TB
    1024TB=1PB
    1024TB=1EB
    1024EB=1ZB
    1024ZB=1YB
    1024YB=1NB
    1024NB=1DB
    ```

## 11. 整数 int

进制转换

- ```python
  num = 8
  # num.bit_length()  #  十进制转换二进制的占位位数
  print(num.bit_length())
  #结果是 3  
  ```

## 12. 布尔值

True - 真       False - 假         用于条件判断

- ```python
  print(bool(-10))     >>> 结果:True    # 0 是 False             非0即True
  print(bool(""))      >>> 结果 :False    # 空的字符串是 False    非空即True
  print(type(str(True)))   结果 : True    布尔值可以转换成字符串
  print(int(False))     >>> 结果 : 0      # True 转化成数字 1   False 转换成数字 0
  ```

## 13. 字符串

字符串 : 用于存储数据      >>>>>   Python中只要用引号引起来的就是字符串

### 1.索引 (下标)  [ ]    # 从0计数  

- ```python
  name = "alex"    # 从左向右
  name1 = name[2]
  print(name1)
  # 结果 : e
  ```

- ```python
  name = "alex"    # 从右向左
  name1 = name[-2]
  print(name1)
  # 结果 : x
  ```

### 2.切片

- ```python
  word = "中华人民共和国万岁!"   # 顾头不顾尾
  word1 = word[2:4]
  print(word1)
  # 结果 : 人民
  ```

- ```python
  word = "中华人民共和国万岁!"   
  word1 = word[0:3:2]		# [起始位置:终止位置:步长]
  print(word1)
  # 结果 : 中人
  ```

- ```python
  # print(name[0:100])  # 切片如果终止位置超出了不报错
  # print(name[100])    # 索引取值的时候超出了索引的范围会报错
  # print(name[::])
  # print(name[::-1])  #从左向右           +1 从右向左
  ```

- ```python
  # 总结：
  #     字符串，列表，元组   都是有索引（下标）
  #     索引是准确的定位某个元素
  #     从左向右 0,1,2,3
  #     从右向左 -1，-2，-3，-4
  #     支持索引的都支持切片   [索引]
  #     切片长度可以超出范围，索引长度不能超出范围  [起始位置：终止位置]
  #     步长： 决定要走的方向，决定走的步子多大  [起始位置：终止位置：步长]
  #     # 起始位置 + 步长
  ```

### 3.字符串常用的方法

**字符串类型.调用 才叫字符串的方法  例: s.upper()**  >>><u>**字符串不可变**</u>

- ```python
  #转换英文大小写 :    转换为大写: .upper()    小写 : .lower()
  word = "china"
  word1 = word.upper()
  print(word1)
  # 结果 : CHINA
  ```

- ```python
  #判断字符串以什么开头 :    .startswith()   .endswith()
  word = "你好世界!"
  print(word.startswith("你")
  # 结果 : True				#  判断结尾 : .endswith("内容")
  ```

- ```python
  # 统计  .count()
  word = " asdf123fdefawdf"
  print(word.count("d"))   # 查询 某个内容出现的次数
  # 结果 : 3
  ```

- ```python
  # 替换   .replace()
  word = "Chinb"
  word1 = word.replace("b","a") 	
  print(word1)
  # 结果 : China 
  ---------------------------------------------------------------------------
  word = "Chinbbb"
  word1 = word.replace("b","a",2) 	#.replace("旧","新",从左往右替换次数)
  print(word1)
  # 结果 : Chinaab 
  ```

- ```python
  #除去首位两边空格   .strip()   >>>脱
  word = "  中国  "
  word1 =word.strip()
  print(word1)
  # 结果 :中国
  ---------------------------------------------------------------------------
  word = "中国  "
  word1 =word.strip("中")   # 在头部没有空格的前提下可以写要去掉的内容
  print(word1)
  # 结果 :国  # 国后面的空格保留不会删掉
  ```

- ```python
  # 分割   .split()  用内容去分割内容 分割后返回的是一个列表
  element = "你好,中国"
  element1= element.split("中")
  print(element1)
  # 结果 : ['你好,', '国']
  ```

- ```python
  #第三种字符串格式化   .format()
  words = "今天天气{},风力{}级!"
  words1 = words.format("晴","四")
  print(words1)
  # 结果 :今天天气晴,风力四级!
  ```

- ```python
  is 系列 -- 判断
  ---------------------------------------------------------------------------
  a = "②"
  print(a.isdigit()) # 判断是不是数字  >>> 小bug  ②在这里是数字
  ---------------------------------------------------------------------------
  a = "666"
  print(a.isdecimal())  # 判断是不是十进制.进而来判断是不是数字    *************
  ---------------------------------------------------------------------------
  a = "China,你好!"
  print(a.isalpha())   # 判断是不是中文 字母  注意标点符号    ***************
  ---------------------------------------------------------------------------
  a = "China,你好!"
  print(a.isalnum())   # 判断是不是字母,中文和阿拉伯数字 ,注意标点符号 *********
  ---------------------------------------------------------------------------
  a = "A"
  print(a.isupper())   # 判断是不是大写
  ```

- ```python
  # 字符串的方法汇总总结
  #1.	.upper() 转换大写
  #2. .lower() 转换小写
  #3. .startswith("内容") 判断字符串以什么开头 → 返回的是判断 Ture or False
  #4. .endswith("内容") 判断字符串以什么结尾 → 返回的是判断 Ture or False
  #5. .count("内容") 统计某个元素出现的次数 → 返回的是数字
  #6. .replace("old","new",替换次数) 替换内容 替换次数不填默认全部替换
  #7. .strip()  除去首位两边空格 → 脱
      word = "中国  "
      word1 =word.strip("中")   # 在头部没有空格的前提下可以写要去掉的内容
      print(word1)
      #结果 :国  # 国后面的空格保留不会删掉
  #8. .split() 用内容去分割内容 分割后返回的是一个列表
  #9. .capitalize() 每个字符串首字母大写
  #10. title() 每个单词首字母大写
  #11. swapcase() 大小写转换(大写转为小写,小写转为大写)
  #12. find("内容") 找到返回的是索引 ,找不到返回-1
  #13. index("内容") 找不到会报错
  ```

- ```python
  is 系列 -- 判断
  ---------------------------------------------------------------------------
  a = "②"
  print(a.isdigit()) # 判断是不是数字  >>> 小bug  ②在这里是数字
  ---------------------------------------------------------------------------
  a = "666"
  print(a.isdecimal())  # 判断是不是十进制.进而来判断是不是数字    *************
  ---------------------------------------------------------------------------
  a = "China,你好!"
  print(a.isalpha())   # 判断是不是中文 字母  注意标点符号    ***************
  ---------------------------------------------------------------------------
  a = "China,你好!"
  print(a.isalnum())   # 判断是不是字母,中文和阿拉伯数字 ,注意标点符号 *********
  ---------------------------------------------------------------------------
  a = "A"
  print(a.isupper())   # 判断是不是大写
  ```

## 14. for循环

- ```python
  len() #  工厂函数  -- 除了int,bool ,其他的类型都可以用
  a = "中国,China,世界"
  print(len(a))   #  计算有多少字符,包括标点符号
  ```

- ```python
  for 循环	只执行一次循环  
  s = "123一二三"
  for a in s :	   #中的s是指可迭代对象
  	print(a)
  结果:
  	1
  	2
  	3
  	一
  	二
  	三
  -----------------------------------------------------------------------------------
  s = "123"
  for a in s :	 
  	#print(a)  # 从前到后依次打印
  	pass	
  	#... # 这是三个英文的点   pass和... 都是占位符  过
  print(a)
  #结果 :3  #分析 for循环体里有pass,最后从s中取出的是3,那么,a的值就是3
  ```

## 15. rang范围

- ```python
  s = range(1,10)  ******* 面试大坑题  range(1,10) 取不到10
  print(s)
  Python3.x 结果 :range(1, 10)  本身
  Python2.x 结果: [1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```

- ```python
  for i in range(1,10,2): # (起始位置，终止位置,步长)
  
  # range(10) 指定了终止位置，起始位置默认是0
  -----------------------------------------------------------------------------------
  for i in range(10,1,-1) : #倒着打印 10,9,8,7,...2  取不到1
  	print(i)
  -----------------------------------------------------------------------------------
  for i in range(1) :
  	print(i)
  #结果 : 0
  若rang(0),结果为空
  ```

## 16. list列表

### 认识list列表

- 初识     li = ["地方",12,"abc"]   里面有多个元素 , 每个元素后面用逗号隔开   **容器  存放任意类型**

  -  两种定义格式 :

    - li = [1,"中国","abc"]
    - li = list("abc")

  - ```python
    li = list("abc")  底层使用for循环  "abc"可迭代的字符串类型
    prin(li)
    结果 : ["a","b","c"]
    ```

  - 列表可以嵌 :

    lst = [1,2,["中国","世界],"你好"]

### 列表的作用

- 储存大量数据
- 有序 - 支持索引,切片,步长
- 可变 - 可在本身修改 

### 列表的增删改查

#### 增

li = [1,2,3,4,5,6]

- ```python
  li.append("内容")  # 追加 添加在末尾   
  li.insert(索引,"内容")  # 插入 索引+"内容  >>>效率低
  li.extend("内容") # 扩展 迭代添加
  li.count("内容") # 统计次数
  li.inex("内容") # 返回的是索引  找不到会报错  列表中没有find
  li.reverse() #翻转列表
  li.sort() #排序 默认升序
  li.sort(reverse=True) #降序排序
    列表合并 :
             l1=[1,2.3]     l2=["a","b","c"]
             l3 = l1 + l2
             print(l3)
             #结果 : [1,2.3,"a","b","c"]
  ```

#### 删

- ```python
  li.pop(索引)        # 默认删除的是最后一个     pop有返回值  可以打印 
  li.remove("内容")   # 只能删除第一个
  del li             # 删除容器
  del li[索引]       # 支持索引
  del li[0:3]        # 支持切片
  del li[1:3:2]      # 支持步长
  li.clear()         # 清空  删除容器内的所有内容
  # del  内存回收机制
  ```

#### 改

- ```python
  li[索引]="内容"        
  li[1:2]=[]    # [7,8,9]  #迭代进去,可多可少
  ```

- **面试题 :**

  ```python
  li = [1,2,3,4,"abc",5]
  li[0:2] = "ABC" #迭代添加
  print(li)
  #结果:['A', 'B', 'C', 3, 4, 'abc', 5]
  ```

  ```python
  a = 2  b = 1
  a,b = b,a
  print(a,b)
  ```

- 步长 ,取几个,就放回几个,不能多也不能少

  ```
  li = ["水杯",2,3,"abc",]
  li[0:3:2] = [1,2,3],[1234]
  print(li)
  ```

#### 查

- ```python
  li = [1,2,3,4,5,6]
  print(li[0])#索引查
  #结果 : 1
  print(li[1:3])
  #结果 :[2,3]
  ```

## 17. 元组

### 认识元组

元组和列表一样可以存放任意类型数据

- ```python
  元组关键字 tuple   
  书写格式  tu = ("哈哈",1)      #逗号隔开
  tu = ("哈哈")		# 小括号中只有元素,没有逗号,结果为元素本身
  print(tu)  结果 :哈哈
   ---------------------------------------------------------------------------------
  tu = (1,)    # 小括号中有一个元素后有逗号的就是元组
  tu = ()     # 空的小括号也是元组   print 结果是 : 0
  ```

- 元组是有序的:

  - 有索引,切片,步长
  - 元组不可变 (列表可变),不可变意味着不能增删改
    - 存一些不想让别人修改的数据,一般用于在配置文件中,防止误操作.

- ```python
  # 索引
      # print(tu[1])
      # 切片
      # print(type(tu[1:1000]))  # 切片返回的是切之前的数据类型
      # 步长
      # print(tu[::2])
  ```

- 元组可嵌套

## 18. dict字典

### 认识dict字典

- 字典 关键字 : dict   其他语言的字典叫键值对数据

  ​		 格式 : {"键":"值"}    {"key":"value"}  

  - 键  ：  必须是可哈希的（不可变的数据类型），并且是唯一的
  - 值 ：任意

- 字典是无序的  字典可以增删改查

### 字典的用处

- 储存大量数据，字典比列表还要大
- 字典查找值方便，快速
- 字典能够把数据进行关联
- 字典比较耗内存，最长使用的数据 ： 字符串，列表 ，字典
- 有明确的对应关系时，推荐使用字典   

### 字典的增删改查

#### 增

- ```python
  dic = {"a":"b","b":"c"}
  dic.setdefault("c","aaa")
  print(dic)
  # 结果 {'a': 'b', 'b': 'c', 'c': 'aaa'}
  
  dic.setdefault("a","aaa")
  print(dic)
  # 结果 {'a': 'b', 'b': 'c'}
  
  setdefault :
  # 先查看字典中是否有要添加的键值，有就不修改，没有就添加进去
  ```

- ```python
  dic["s"] = "ssss"   # dic[键] = 值
  print(dic)
  # 结果 ： {'a': 'b', 'b': 'c', 's': 'ssss'}
  # 同样这个方法也可以修改
  ```

- ```python
  # 定义字典方式 : 
  dic = {"k1":"v1","k2":"v2"}  or dic = dict(k1="v1",k2="v2")
  1. dic.popitem()  #随机删除  在pytnon 3.6版本以上默认删除最后一个键值对,3.6以下随机删除
  2. 批量创建字典  dic = dict.fromkeys(可迭代对象,每一个key的值)
     dic1 = dict.fromkeys("abcdef",1)
  ```

#### 删

- ```python
  dic = {"a":"b","b":"c"}
  print(dic.pop("a"))   #通过键删除  pop具有返回值,返回的是被删除的值
  print(dic)
  结果 ：{'b': 'c'}
  字典中没有remove方法
  ```

- ```python
  del dic # 删除整个字典
  del dic["b"] # 删除指定的键值对
  dic.clear # 清空
  ```

#### 改

- ```python
  dic = {"a":"b","C":"c"}
  dic["b"] = "这是值"   # 键在字典中存在就是修改,键在字典中不存在就是增加
  print(dic)
  结果 ： {'a': 'b', 'C': 'c', 'b': '这是值'}
  ```

- ```python
  dic2 = {1:2,"a":"a1"}
  dic2.update(dic)   # update括号里的字典级别高
  print(dic2)
  结果 ： {1: 2, 'a': 'b', 'C': 'c'}
  ```

#### 查

- ```python
  # 字典的查询只能通过键获取值,不能通过值获取键
  dic = {1:2,"a":"a1"}
  print(dic["c"])  # 如果有键在字典中存在就放回键对应的值,如果不存在就报错
  get  -- 获取
  print(dic.get("c","这是返回值")) #
  # 获取值的时候可以指定返回的内容,键不存的时候返回None不报错
  ```

- ```python
  # dic = {1:2,"a":"a1"}
  # for i in dic:   # for循环字典的时候打印的是字典的键
  #     print(i,dic[i])
  ```

#### 一些操作举例

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  # # 删除"2"  2种方式
  dic.pop("2")
  del dic["2"]
  
  # # 添加 "5":5 2种方式
  dic.setdefault("5",5)
  dic["5"] = 5
  
  # # 修改: "1":10086
  dic["1"] = 10086
  
  # # 查看"3"的值
  dic.get("3",'没有值')
  # dic["3"]  # 没有就会报错
  ```

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  li = []
  for key in dic:
      li.append(key)
  print(li)
  # 结果 : ['1', '2', '3', '4']
  ```

- ```python
  #高仿列表
  dic = {"1":9,"2":2,"3":3,"4":4}
  for i in dic.keys():#高仿列表
      print(i)  # 打印的是键
  # 结果 : 
      1
      2
      3
      4
  ```

- ```
  其他操作:
  获取所有的键 :   keys()   --- 高仿列表  没有索引
  获取所有的值 :   values()  --- 高仿列表  没有索引
  获取所有的键值 : items()   --- 以元组的形式存放  键是元组中的第一个元素, 值是第二个元素
  ```

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  print(type(dic.keys()))   # 可以for循环,但是不能索引
  dic_li = dic.keys()
  print(dic_li)  
  #结果 :
   <class 'dict_keys'>
  dict_keys(['1', '2', '3', '4']
  ```

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  print(dic.values())   # 打印的是键值
  # 结果 : dict_values([1, 2, 3, 4])
  ```

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  for i in dic.items():
       print(i)
  #结果 :
  ('1', 1)
  ('2', 2)
  ('3', 3)
  ('4', 4)
  ```

- ```python
  # 解构
  # a = 1
  # b = 2
  # print("is a",id(a))
  # print("is b",id(b))
  # a,b = b,a
  # print("is a",id(a))
  # print("is b",id(b))
  ```

- ```python
  dic = {"1":1,"2":2,"3":3,"4":4}
  for key,value in dic.items():
      print(key,value)
  # 结果 : 
      1 1
      2 2
      3 3
      4 4
  
  # keys,values,items,解构
  dic = {"1":1,"2":2,"3":3,"4":4}
  for i in dic:        # 效率高
      print(i,dic[i])
  # 结果同上   
  
  for k,v in dic.items():
      print(k,v)
  # 结果同上    
  ```

- **购物车**

  ```python
  dic = {"电脑":15000,"手机":8000,"耳机":4000,"老婆":1111}
  count = 1
  for i in dic:
      print(count,i)
      count += 1
  # 结果 :
      1 电脑
      2 手机
      3 耳机
      4 老婆   
  ```

- **枚举**

  ```python
  li = [1,2,3,4,54]
  for i,k in enumerate(li,0):  # enumerate 第二个参数默认不写就是0    -- 枚举
      print(i,k)	#第二个参数是指从数字几开始计数
  # 结果 :		  #打印的时候,第二个参数是第一个(先打第二个参数)
      0 1
      1 2
      2 3
      3 4
      4 54   
  ```

#### 字典的嵌套

```python
# dic = {
#     101:{1:["周杰伦","林俊杰"],2:{"汪峰":["国际章",{"前妻1":["熊大","熊二"]},
#                                   {"前妻2":["葫芦娃","木吒"]}]}},
#     102:{1:["李小龙","吴京","李连杰"],2:{"谢霆锋":["张柏芝","王菲"]},
#          3:["alex","wusir","大象","奇奇"]},
#     103:{1:["郭美美","干爹"],2:{"王宝强":{"马蓉":"宋哲"}}},
#     201:{1:["凹凸曼","皮卡丘"],2:{"朱怼怼":{"杨幂":"刘恺威"}}}
# }

# print(dic[101][2]["汪峰"][2]["前妻2"][0])
#['国际章', {'前妻1': ['熊大', '熊二']}, {'前妻2': ['葫芦娃', '木吒']}]
#{'前妻2': ['葫芦娃', '木吒']}
#['葫芦娃', '木吒']

# home1 = dic[102][3][2]
# {1: ['李小龙', '吴京', '李连杰'],
# 2: {'谢霆锋': ['张柏芝', '王菲']},
# 3: ['alex', 'wusir', '大象', '奇奇']}
# print(home1)

# print(dic[103][2]["王宝强"]["马蓉"])
```

## 19. set集合 -天然去重

### 认识集合

- set {1,2,3}     s = {1,2,3,"123",false,(1,2,3,4)}
- 集合就是一个没有值的字典,遵循唯一,无序,  元素要求可希哈(不可变)
  - 集合是无序的,
  - 集合是可变的

### 集合的增删改

#### 增

- ```python
  s.update("3456")    #迭代添加
  s.add(添加的内容)
  ```

#### 删

- ```python
  s.pop()   #随机删除
  s.remove(删除的内容)
  s.clear()   #清空
  del s
  ```

#### 改

- ````
  删了再添加
  ````

#### 去重

- ```python
  li = [1,2,3,4,2,1,3] #一行代码去重
  print(list(set(li)))
  ```

#### 其他操作

- ```python
  # 	差集   ( - 或者 difference )    
  set1 = {1,2,3,4,5}
  set2 = {4,5,6,7,8}
  print(set1 - set2)   # 结果: {1, 2, 3}
  print(set1.difference(set2))  # 结果: {1, 2, 3}
  ```

- ```python
  # 	并集   ( | 或者 union)
  set1 = {1,2,3,4,5}
  set2 = {4,5,6,7,8}
  print(set1 | set2)  # 结果:{1, 2, 3, 4, 5, 6, 7,8}
  print(set2.union(set1))  # 结果:{1, 2, 3, 4, 5, 6, 7,8}
  ```

- ```python
  # 交集  ( & 或者 intersection )
  set1 = {1,2,3,4,5}
  set2 = {4,5,6,7,8}
  print(set1 & set2)  # 结果 : {4, 5}
  print(set1.intersection(set2))  # 结果 : {4, 5}
  ```

- ```python
  #	对称差集  - 反交集   ( ^ 或者symmetric_difference)
  set1 = {1,2,3,4,5}
  set2 = {4,5,6,7,8}
  print(set1 ^ set2)  # 结果:  {1, 2, 3, 6, 7, 8}
  print(set1.symmetric_difference(set2))  # 结果: {1, 2, 3, 6, 7, 8}
  ```

- ```python
  #	超集和子集
  set1 = {1,2,3}
  set2 = {1,2,3,4,5,6}
  
  print(set1 < set2) # True
  print(set1.issubset(set2))  # True 这两个相同，都是说明set1是set2子集。
  
  print(set2 > set1) # True
  print(set2.issuperset(set1))  # True 这两个相同，都是说明set2是set1超集。
  ```

- ```python
  #	冻结集合 (可变转换成不可变)  -- 不常用
  f_s = frozenset({1,2,3,4,5})
  dic = {f_s:"1"}
  print(dic)
  ```

## 20. 深浅拷贝

**深浅拷贝用在不让修改原数据的数据的时候使用**

### 浅拷贝

- 对于浅copy来说,第一层创建的是新的内存地址,而从第二层开始指向的都是同一个内存地址,所以,对于第二层以及更深层的层数来说,保持一致性.

- ```python
  # l1 = [1,2,3,4,[4,5,6]]
  # l2 = l1[:]   # 浅拷贝
  # l2 = l1.copy() # 浅拷贝  -- 只拷贝第一层
  
  l1 = [1,2,3,['hello','world']]
  
  l2 = l1.copy()
  print(l1,id(l1))  # [1, 2, 3, ['hello', 'world']] 1920725366664
  print(l2,id(l2))  # [1, 2, 3, ['hello', 'world']] 1920726234696
  l1[1] = 222
  print(l1,id(l1))  #[1, 222, 3, ['hello', 'world']] 1920725366664
  print(l2,id(l2))  # [1, 2, 3, ['hello', 'world']] 1920726234696
  
  l1[3][0] = 'everybody'
  print(l1,id(l1[3]))  # [1, 222, 3, ['everybody', 'world']] 1920726234824
  print(l2,id(l2[3]))  # [1, 2, 3, ['everybody', 'world']] 1920726234824
  ```

### 深拷贝deepcopy

- 对于深copy来说,两个是完全独立的,改变任意一个任何元素(无论多少层),另一个也绝不会改变

- ```python
  import copy
  
  l1 = [1,2,3,['hello','world']]
  l2=copy.deepcopy(l1)
  print(l1,id(l1))  # [1, 2, 3, ['hello', 'world']] 2200548595592
  print(l2,id(l2))  # [1, 2, 3, ['hello', 'world']] 2200548596424
  l1[1] = 222
  print(l1,id(l1))  #[1, 222, 3, ['hello', 'world']] 2200548595592
  print(l2,id(l2))  # [1, 2, 3, ['hello', 'world']] 2200548596424
  
  l1[3][0] = 'everybody'
  print(l1,id(l1[3]))  # [1, 222, 3, ['everybody', 'world']] 2200548595400
  print(l2,id(l2[3]))  # [1, 2, 3, ['hello', 'world']] 2200548596360
  ```

## 21. 小数据池

- 小数据池是Python中的一种提高效率的方式,固定数据类型,,使用同一个内存地址

- 小数据池支持的数据类型 : str , int , bool

- ```python
  # == 比较的是值
  # is 比较的是内存地址
  ```

- ```
  1. 当我们在控制台(cmd)的时候,代码块与代码块之间的规则:
  	A.数字:-5~256之间额整数会被缓存
  	B.字符串:
  		1.小于等于1会默认缓存
  		2.长度大于1,如果字符串中只有数字,字母下划线会缓存
  		3.乘法得到的字符串:
  			如果乘法得到的最终的字符串不超过20,会缓存
  			手动指定缓存 : from sys import intern  intern(指定缓存的内容)
  	C.布尔值会被缓存
  2.py文件中,一个代码块内部,只会缓存int,str,bool,py中有自己的小数据池,范围比外面的代码块的数据池要大
  	a.数字.都会缓存.运算结果不缓存(-5~256的结果会缓存)
  	b.字符串.默认的字符串都会缓存,如果有乘法,遵循1.b.3的规则
  	c.布尔值,默认缓存
  ```

- ```
  # 代码块的规则:
      # 数字: 全部驻留
      # 字符串:
          #1.字符做乘法的时候总长度不能超过20
          #2.自定定义的都驻留
          #3.乘数为1的时候 就是赋值
          #4.python3.7 乘法的时候总长度不能超过4096
  
  # 总结:
      # 小数池 -- 支持: str,int,bool
      #小数据池数字: -5 ~ 256
      #小数据池字符串: 乘法时结果长度不能超过20
  ```

## 22. 数据类型转换

- ```
  1. str → int # 字符串转整型 字符串必须都是十进制的数
  	int(str)
  2. int → str # 整型转字符串
  	str(int)
  3. str → list # 字符串转换成列表
  	list(str) #字符串转列表  字符串会迭代
      str.split() # 字符串会成为一个元素,转换成列表,不会迭代
  4. list → str # 列表转换成字符串
  	''.join(list)  # 列表中不能有int整型数字
  5. list → tuple # 列表转换元组
  	tuple(list)
  6.tuple → list # 元组转换列表
  	list(tuple)
  7. set → list # 集合转换列表
  	list(set)
  8. list → set # 列表转换集合
  	set(list)
  # 总结1 :
  	1. 字符串→数字 :字符串中必须都是十进制的数字
      2. 数字→数字  : 直接转换
      3. 列表→字符串 : ''.join() # 可迭代对象,不能出现数字
      4. 字符串→列表 : .split()
      5. 除字典外,容器数据类型之间可以直接相互转换
  # 总结2 :
   1. 学到的数据类型 :
      str,int,bool,list,tuple,dict,set
   2. 有序的数据类型 :
      str,int,bool,list,tuple
   3. 无序 :
      dict,set
   4. 可变 :
      list,dict,set
   5. 不可变 :
      str,int,bool,tuple
   6.访问方式 :
      直接访问 : int,bool,set
      顺序访问 : str,list,tuple
      通过键访问 : dict
  ```

## 23. 坑

- **针对索引值是奇数的删除**

  - ```python
    li = [1,2,3,4]  # [1,3,4]
    # 索引值是奇数的删除
    for i in range(4):
        if i % 2 == 1:
            li.pop(i)   # 会报错 解释:列表可变,删除元素后,索引值会改变
    print(li)
    ```

  - ```python
    li = [1,2,3,4,5]   #[1,3,4,5]
    # 索引值是奇数的删除
    for i in range(4):
        if i % 2 == 1:
            li.pop(i)   # 结果不对
    print(li)
    ```

  - ```python
    #正确操作
    li = [1,2,3,4,5]
    for i in range(len(li)-1,-1,-1):
        if i % 2 == 1:
            li.pop(i)   # 倒序删除
    print(li)
    ```

  - ```python
    #正确操作
    #偷换感念 >>> 删除索引是奇数的
    li = [1,2,3,4,5]
    new_li = []
    for i in range(len(li)):
        if i % 2 == 1:
            new_li.append(li[i])
    for em in new_li:
        li.remove(em)
    print(li)
    ```

  - ```python
    li = [1,2,3,4,5]
    del li[1::2]
    print(li) # 结果 :[1, 3, 5]
    ```

- **使用for删除列表的时候从左向右删除,会报错.结果不对**

  - ```python
    dic = {"k1":"v1","k2":"v2"}
    for i in dic:
        dic["k3"] = "v3"
    print(dic) #结果报错
    #不能在遍历字典本身中改变大小,要批量删除字典的键值对
    dic = {"k1":"v1","k2":"v2","k3":"v3"}
    for i in dic:
        dic["k7"] = "1"
    print(dic) # 结果:报错
    ```

  - ```python
    # 删除字典  不能在遍历字典本身中改变大小,要批量删除字典的键值对
    dic = {"k1":"v1","k2":"v2","k3":"v3"}
    li = []
    for i in dic:
        if i == "k1" or i == "k3":
            li.append(i)
    for em in li:
        dic.pop(em)
    print(dic)
    ```

  - ```python
    li = [1,2,3,4]
    for i in li:
        li.append(i)
    print(li)
    #结果: 程序一直在运行,但是会显示空白,列表是可变的,会一直...
    ```

## 24. 编码解码

- ```python
  # ascii     不支持中文
                      字  节
  # gbk       国标   英文1 中文2
  # unicode   万国码 英文2 中文4
  # utf-8     英文1  欧洲2 亚洲3
  ```

- ```python
  # python3内存使用的就是unicode
  # python2内存使用的就是ascii
  ```

- ```python
  # 编码
  s = "你好"
  s1 =s.encode("gbk")
  print(s1)
  结果 :b'\xc4\xe3\xba\xc3'
  --------------------------------------------------------------------
  # 解码
  s2 = b'\xc4\xe3\xba\xc3'
  s3 = s2.decode("gbk")
  print(s3)
  结果 : 你好 
  ```

## 25. 文件操作

- **使⽤用python来读写⽂文件是非常简单的操作. 我们使⽤用open()函数来打开⼀一个⽂文件, 获取到⽂文
  件句句柄. 然后通过⽂文件句句柄就可以进⾏行行各种各样的操作了了. 根据打开⽅方式的不同能够执⾏行行的操作也会有相应的差异.打开⽂文件的⽅方式: r, w, a, r+, w+, a+, rb, wb, ab, r+b, w+b, a+b 默认使⽤用的是r(只读)模式**
- 模式
  - r 读 ,只能读		
  - w 写,只能写
  - a 追加写,只能写入

### 一般书写格式格式

- ```python
  f = open("文件",mode = "模式",encoding = "编码")    #  这里f是一个可迭代对象 
  ```

- ```python
  f = open("文件",mode = "r",encoding = "编码") 
  content = f.read()  # 读取全部内容 →缺点:读大文件时,内存容易溢出,    
  content = f.read(3) # 从前往后读取三个字符
  		f.readline()  #打印一行
  		print(content)
  		f.close()  # 关闭
  ```

- ```python
  #f是一个可迭代对象
  for line in f : # 内部调用的是readline()
  	print(line)  #一行一行打印
   f.close() #关闭  
  ```

### 写

- ```python
  f = open("文件",mode = "w",encoding = "编码")   #写模式,若没这个路径,则会自动在相应路径下创建文件
  f.write("要写进去的内容")  #写的时候,在本次打开的时候先清空,再写入    
  f.flush() #刷新
  f.close()
  #追加写 : a 
  f = open("文件",mode = "a",encoding = "编码") 
  ```

### 非文本操作b

- ```python
  b:bytes  这个时候处理的文件是字节
  rb
  wb
  ab
  f = open("文件",mode = "rb") #没有编码
  ```

- ```python
  #网络请求
  import requests
  ret = requests.get("http://www.521609.com/uploads/allimg/151124/1-1511241G251317.png")
  f = open("2.jpg",mode="wb")
  f.write(ret.content)
  f.close()
  ```

- ```python
  #文件拷贝
  f1 = open("路径",mode="rb")
  f2 = open("保存的地址及文件名".mode = "wb")
  for line in f1 :
      f2.write(line)
  f1.close()
  f2.flush()
  f2.close()
  ```

### r+ ,w+ , a+ 

- **r+ 正确用法: 先读后写**  # 深坑,在r+的模式下.只要是执行了读,再写就在末尾写**

  - ```python
    f = open("地址",mode="r+",encoding="utf-8")
    f.wirte("写入的内容")  #如果上来直接写,则写在文件开头,并且覆盖原文
    ```

  - ```python
    f = open("地址",mode="r+",encoding="utf-8")
    s = f.read(1)  # 读取一个字符
    print(s)
    f.wirte("写入的内容")  #  如果已经执行了读操作,后面的写都是在文件末尾,和光标没有关系
    ```

- **w+ 写读 正确使用 :先写后读(执行写的时候先清空)**

  - ```python
    f = open("地址",mode="w+",encoding="utf-8")
    f.seek(0) # 光标移动到开头
    ```

- **a+ 追加读写模式**

  - ```python
    f = open("地址",mode="a+",encoding="utf-8")
    ```

### 断点续传

- r+b

  w+b

  a+b (常用)

### 光标

- ```python
  #tell查找光标  单位字节
  #seek(1) 移动光标 单位字节
  #read(1)  单位字符
  #seek(0,2) 光标移动到末尾    seek(偏移量,位置)    位置 :0开头  1当前位置  2,末尾  默认o
  ```

### truncate() 截断文件

- ```python
  f = open("地址",mode="r+",encoding="utf-8")
  f.seek(9)
  f.truncate(9)#如果没有参数,按照光标截断,如果有参数,截断到参数位置
  ```

### 文件修改

- ```python
  import os # 引入os模块
  with open("路径",mode="r",encoding="utf-8") as f1,\
      open("路径副本",mode="r",encoding="utf-8") as f2 :
      for line in f1:
          ...
  os.remove("路径")
  os.rename("路径副本","路径")
  ```


## 26. 三种格式化输出

1. %s , %d .....

   - ```python
     print("我的名字叫%s,我的爱好是%s"%("张三","听音乐"))
     结果:我的名字叫张三,我的爱好是听音乐
     ```

   ### 格式符

   - ```
     格式符为真实值预留位置，并控制显示的格式。格式符可以包含有一个类型码，用以控制显示的类型，如下:
     
     %s    字符串 (采用str()的显示)
     
     %r    字符串 (采用repr()的显示)
     
     %c    单个字符
     
     %b    二进制整数
     
     %d    十进制整数
     
     %i    十进制整数
     
     %o    八进制整数
     
     %x    十六进制整数
     
     %e    指数 (基底写为e)
     
     %E    指数 (基底写为E)
     
     %f    浮点数
     
     %F    浮点数，与上相同
     
     %g    指数(e)或浮点数 (根据显示长度)
     
     %G    指数(E)或浮点数 (根据显示长度)
     ```

2. f

   ```
   f"{}变量名" 在Python3.6斑斑中才能实现
   msg = f'''
   ------------------- info ----------------------
   name: {input("请输入您的名字:")}
   age:  {input("请输入您的年龄:")}
   sex : {input("请输入您的性别:")}
   job:  {input("请输入您的职业:")}
   hobby: {input("请输入您的爱好:")}
   ------------------- end ------------------------
   '''
   print(msg)
   ```

3.format 的三种格式化输出

```python
形式一 :  >>> 必要要一一对应
print("我的名字是{},我住在{},我的爱好是{}".format("张三","河北","唱歌"))
```

```python
形式二 :
print("我的名字是{0},我住在{1},我的爱好是{2}".format("张三","河北","唱歌"))
```

```python
形式三 :
print("我的名字是{name},我住在{site},我的爱好是{hobby}".format(name="张三",hobby="唱歌",site="河北"))
```

# 函数和模块

## 1. 函数 - 面向过程编程

### 初识函数

- 函数 ：函数是以功能为导向，一个函数封装一个功能，登录，注册，评论，文件操作等

- 优点：减少代码重复，提高代码的可描述性 

- ```python
  #获取任意一个字符串的元素的个数
  s1 = 'fdskjlgfdgfdjkslgdfjkjafdsajk'
  count = 0
  for i in s1:
      count += 1
  print(count)
  
  
  #获取列表的元素的个数
  l1 = [1, 2, 3]
  count = 0
  for i in l1:
      count += 1
  print(count)
  
  # 利用函数
  l1 = [1, 2, 3]
  def new_len():
      count = 0
      for i in l1:
          count += 1
      	print(count)
  new_len()
  ```

### 函数的结构

- `def  func() :`

  🔼	  🔼   

  关键字 函数名  `() 和:`结构需要

  - 函数名 : 与变量名命名规范一致,一定具有可描述性

  - ```python
    l1 = [1, 2, 3]
    def new_len():
        count = 0
        for i in l1:
            count += 1
        	print(count)
    new_len()
    ```

### 函数的调用 ***

函数名()  → 函数的执行者/函数的调用者, 出现几次,这个函数就执行几次

```python
l1 = [1, 2, 3]
def new_len():
    count = 0
    for i in l1:
        count += 1
    print(count)

函数的执行写多少次，执行多少次。
new_len() # 函数名() 函数的执行者。调用者。
new_len()  # 函数名() 函数的执行者。
new_len()  # 函数名() 函数的执行者。
new_len()  # 函数名() 函数的执行者。
new_len()  # 函数名() 函数的执行者。

l1 = [1, 2, 3]
def new_len():
    count = 0
    for i in l1:
        count += 1
    print(count)

for i in range(10):
    print(111)
    
for i in range(3):
    new_len()
```

### 函数的返回值

- 函数的返回值  - 返回给函数的执行者

- ```python
  #一个函数就是封装一个功能，这个功能一般都会有一个最终结果的，比如你写一个登录函数，最终登录成功与否是不是需要返回你一个结果？还有咱们是不是都用过len这个函数，他是获取一个对象的元素的总个数，最终肯定会返回一个元素个数这样的结果：
  s1 = 'abfdas'
  print(len(s1))  # 6
  ```

- **函数中的return作用 :**

- ```python
  1.结束函数,后面的代码统统不执行,只能在函数中用
  2.给函数的执行者返回具体的值
  ```

- ```python
  l1 = [1, 2, 3]
  def new_len():
      print(111)
      print(222)
      if 1 == 1:
          return
      print(333)
      print(444)
  new_len()
  #结果
  111
  222 
  ```

- **函数中如果没有return,或者程序中只有一个return,函数的执行者得到的是None**

- ```python
  l1 = [1, 2, 3]
  def new_len():
      count = 0
      for i in l1:
          count += 1
      return
  print(new_len())
  # 结果 :	None
  ```

- **函数中return后面是单个值,则返回这个值(值类型不改变)**

- ```python
  def func():
      print(111)
      # return 100
      # return [1, 2, 3]
      return {'name': '哈哈'}
  ret = func()
  print(ret, type(ret))
  # 结果 :
  111
  {'name': '哈哈'} <class 'dict'>
  ```

- **函数中return后面是多个值,函数的执行者得到的是一个元组**

- ```python
  def func():
      print(111)
      return 1, '走你', [22, 33]
  ret = func()
  print(ret, type(ret))  # (1, '走你', [22, 33])
  
  
  def func():
      print(111)
      # return 1+1+2
      return 2 > 1 # 返回结果
  ret = func()
  print(ret)
  # 结果
  111
  True
  
  ```

### 函数的传参

- 之前的函数都是写死的,现在引出函数的传参,使代码更简便

- 函数的传参 - - 函数的拓展性

- ```python
  def new_len(a):  # 定义函数时：参数：形参。
      count = 0
      for i in a:
          count += 1
      return count
  l1 = [1, 2, 3]
  print(new_len(l1)) # 函数的调用者：参数 实参。
  
  ```

  #### 实参角度 :

  ##### 1. 位置参数

  ```python
  # 1. 位置参数。： 从左至右，按照顺序，一一对应
  def meet(sex,age,job,):
      print('左划一下')
      print('右划一下')
      print(f'寻找性别{sex},年龄{age}岁,{job}')
  
  meet('女','18~25','讲师')
  
  #写一个函数，接收两个数字的参数，将较大的数字返回。
  def comp(a,b):
      if a > b:
          return a
      else:
          return b
  ret = comp(1,2000)
  print(ret)
  
  ```

  **三元运算符：简单的if else。**

  ```python
  a1 = 1
  b2 = 2
  ret = a1 if a1 > b2 else b2
  print(ret)
  
  def comp(a,b):
      # ret = a if a > b else b
      # return ret
      return a if a > b else b
  ret = comp(1,2000)
  print(ret)
  
  ```

  ##### 2. 关键字参数

  ​	**参数要一一对应**

  ```python
  def meet(sex,age,job,hight,weight,):
      print('左划一下')
      print('右划一下')
      print(f'寻找性别{sex},年龄{age}岁,身高{hight},体重{weight},工作{job}')
  
  meet(sex='女',job='学生',weight=120,hight=170,age='18~25')
  
  ```

  ##### 3.混合参数

  ​	**关键字参数一定要在位置参数后面,遵循一一对应**

  ```python
  def meet(sex,age,job,hight,weight,):
      print('左划一下')
      print('右划一下')
      print(f'寻找性别{sex},年龄{age}岁,身高{hight},体重{weight},工作{job}')
  
  meet('男',22,'ITC语言',weight=120,hight=175,)
  
  ```

  #### 形参角度 :

  - **1.位置参数 : 与实参角度位置参数一样**

  - ```python
    def meet(sex,age,job):
        print('左划一下')
        print('右划一下')
        print(f'寻找性别{sex},年龄{age}岁,{job}')
    
    meet('女','18~25','幼师')
    
    ```

  - **2.默认参数 : 一定要写在位置参数后面 , 不传参即沿用默认参数**

  - ```python
    # open('文件的改',encoding='utf-8')
    def meet(age,job,sex='女'):
        print('左划一下')
        print('右划一下')
        print(f'寻找性别{sex},年龄{age}岁,{job}')
    
    # meet('18~25','幼师')
    # 更改默认参数
    # meet('18~25','幼师',sex='laddy_boy')
    meet('18~25','幼师','laddy_boy')
    
    ```

  #### 万能参数

  ​	形参角度 : 第三种传参方式 → 万能参数py

  ```python
  def eat(food1,food2,food3):
      print(f'我请你吃：{food1},{food2},{food3}')
  eat('蒸羊羔','蒸熊掌','蒸鹿尾')
  #当给函数传入的参数数目不定时，之前的传参方式解决不了问题。
  
  ```

  ##### 万能参数 - 动态参数 :

  - ***args**

  ```python
  def eat(*args):  # 将实参角度：定义一个函数时，* 所有的位置参数聚合到一个元组中。
      print(args)
      print(f'我请你吃：{args}')
  eat('蒸羊羔','蒸熊掌','蒸鹿尾','烧花鸭','烧企鹅')
  # 结果
  ('蒸羊羔', '蒸熊掌', '蒸鹿尾', '烧花鸭', '烧企鹅')
  我请你吃：('蒸羊羔', '蒸熊掌', '蒸鹿尾', '烧花鸭', '烧企鹅')
  
  ```

  ```python
  # 函数接收不定个数的数字实参，将最终的和返回出去。
  def sum1(*args):
      # print(args)  (100, 2, 67, 3)
      result = 0
      for i in args:
          result += i
      return result
  print(sum1(100,2,67,3))
  # 结果 :172
  
  ```

  - ** **kwargs**

  ```python
  def func(**kwargs):  # 函数的定义时：**将实参角度所有的关键字参数聚合成了一个字典，给了kwargs.
      print(kwargs)
  func(name='alex',age=84,hobby='唱跳rap篮球')
  # 结果 :{'name': 'alex', 'age': 84, 'hobby': '唱跳rap篮球'}
  
  ```

  - **万能参数**

  ```python
  # *args,**kwargs 万能参数
  def func(*args,**kwargs):
      print(args,kwargs)
  func(1,2,4,'fjdksal',age=84,hobby='唱跳rap篮球')
  # 结果 :(1, 2, 4, 'fjdksal') {'age': 84, 'hobby': '唱跳rap篮球'}
  
  ```

  - ***的魔性用法(函数中)**

  ```python
  def func(*args,**kwargs):
      print(args)  
      print(kwargs)
  l1 = [1, 2, 3]
  l2 = ['太阳', 'moon', '云朵']
  func(l1,l2)
  # 结果:
  ([1, 2, 3], ['太阳', 'moon', '云朵'])
  {}
  
  func(*l1,*l2)  # 当函数的执行时：*iterable 代表打散。
  # 结果 :
  (1, 2, 3, '太阳', 'moon', '云朵')
  {}
  
  func(*[1, 2, 3],*(11,22),*'fdsakl')  # 当函数的执行时：*iterable 代表打散。
  # 结果:
  (1, 2, 3, 11, 22, 'f', 'd', 's', 'a', 'k', 'l')
  {}
  
  ```

  ```python
  # 当函数的执行时：**dict 代表打散。
  def func(*args,**kwargs):
      print(args)
      print(kwargs)
  func(**{'name':"alex"},**{'age': 73,'hobby': '吹'})
  # 结果 :
  ()
  {'name': 'alex', 'age': 73, 'hobby': '吹'}
  
  ```

  - **函数外: 处理剩余元素** - 以列表形式返回

  - ```python
    a,b,*c = [1,2,3,4,5]
    print(a,b,c) #  1 2 [3, 4, 5]
    
    a,*c,b, = [1,2,3,4,5]
    print(a,b,c) # 1 5 [2, 3, 4]
    
    a,*c = range(5)
    print(a,c) #  0 [1, 2, 3, 4]
    
    a,*c,b = (1,2,3,4,5,6)
    print(a,c,b) # 1 [2, 3, 4, 5] 6
    
    ```

  - ***args的位置**

    - *args不能放在位置参数前面，a,b取不到值

      ```python
      def func(*args,a,b,sex='man',):
          print(a)
          print(b)
          print(sex)
          print(args)
          # print(kwargs)
      func(1,2,4,5,6) # 报错
      
      ```

    - *args如果想要接收到值之前，肯定要改变sex默认参数。

      ```python
      def func(a,b,sex='man',*args):
          print(a)
          print(b)
          print(sex)
          print(args)
      func(1,2,4,5,6)
      # 结果:
      1
      2
      4
      (5, 6)
      
      
      def func(a,b,*args,sex='man'):
          print(a)
          print(b)
          print(sex)
          print(args)
      func(1,2,4,5,6)
      # 结果 :
      1
      2
      man
      (4, 5, 6)
      func(1,2,4,5,6,sex='women')
      # 结果 :
      1
      2
      women
      (4, 5, 6)
      
      ```

      ##### **kwargs

      **含参函数的形参位置 :**

      位置参数  → *args → 默认参数 → 仅限关键字参数  → **kwargs

      ```python
      def func(a,b,*args,sex='man',**kwargs,):
          print(a)
          print(b)
          print(sex)
          print(args)
          print(kwargs)
      func(1,2,4,5,6,name='星星',age=18)
      # 结果 :
      1
      2
      man
      (4, 5, 6)
      {'name': '星星', 'age': 18}
      
      ```

      **形参角度第四种传参方式：仅限关键字参数**  

      ```python
      # 位置参数,*args,默认参数，仅限关键字参数,**kwargs
      def func(a,b,*args,sex='man',c,**kwargs,):
          print(a)
          print(b)
          print(sex)
          print(c)
          print(args)
          print(kwargs)
      func(1,2,4,5,6,67,c=666,name='阿坤',age=18,)
      # 结果:
      1
      2
      man
      666
      (4, 5, 6, 67)
      {'name': '阿坤', 'age': 18}
      
      ```

      ##### 简单了解时间模块

      ```python
      import time #导入时间模块
      print(time.time()) # time.time 为时间戳
      print(111)
      time.sleep(1) # 让程序静止1秒
      age = 18
      print(age)从空间角度研究函数
      
      ```

### 从空间角度研究函数

#### 1. 全局名称空间

​	py文件中，存放变量与值的关系的一个空间叫做全局名称空间

#### 2. 局部名称空间 (临时名称空间)

​	当执行函数时，内存中会临时开辟一个空间，临时存放函数中的变量与值的关系，叫临时名称空间，也叫局部名称空间

#### 3. 内置名称空间

​	内置名称空间存放的就是一些内置函数等拿来即用的特殊的变量：input，print，list等等

#### 4. 加载顺序

​	内置命名空间(程序运行伊始加载)->全局命名空间(程序运行中：从上到下加载)->局部命名空间(程序运行中：调用时才加载。

#### 5. 取值顺序

```python
#变量 (函数名也叫变量)

input = 666
print(input)
# 从全局寻找input ————> 全局名称空间 ——————> 内置

input = '太白'
def func():
    #input = 666
    print(input)
func()
#从局部寻找input ——————> 局部名称空间 ————> 全局名称空间 ——————> 内置
# 取值顺序：单向不可逆

def func():
    name = 'moon'
func()
print(name) #全局找name --> 内置(不会在局部找)


name = '阿坤'
def func():
    #name = 'moon'
    def inner():
        print(name) # 先在局部找,如果局部没有,去全局找,然后内置
    inner()
func()

```

### 内置函数的研究   globals locals

```python
name = 'moon'
l1 = [1, 2, 3]

def func():
    age = '18'
func()
print(globals()) # 全局作用域所有的内容
print(locals())  # 当前位置

```

**三个小练习**

```python
# 例1：

# def func1():
#     print('in func1')
#     print(3)
# def func2():
#     print('in func2')
#     print(4)
#
# func1()
# print(1)
# func2()
# print(2)
'''
in func1
3
1
in func2'
4
2
---------------------------------------------
# 例2：
def func1():
    print('in func1')
    print(3)
def func2():
    print('in func2')
    func1()
    print(4)
print(1)
func2()
print(2)

'''
1
in func2
in func1
3
4
2
-----------------------------------------------
# # 例3：
#
def fun2():
    print(2)
    def func3():
        print(6)
    print(4)
    func3()
    print(8)

print(3)
fun2()
print(5)
#//3 2 4 6 8 5


```

### 关键字

```python
count = 0
def func():
    count += 1
func()
# 报错 ：UnboundLocalError: local variable 'count' referenced before assignment
# 解释器认为：如果你在局部作用域对一个变量进行修改了，解释器认为你在局部作用域已经定义好这个变量了。但现在你并没有定义这个变量,所有报错了

```

#### 1. **在局部作用域声明一个全局变量 : global   -  (剪切)**

```python
def func():
    global name
    name = 1
    print(globals())
    # print(locals())
    name += 1
    print(globals())
func()
# print(name)
print(globals())

```

#### 2. global  - 可以修改全局变量

```python
count = 0
def func():
    global count
    count += 1
print(count)
func()
print(count)

```

#### 3.  在局部作用域声明一个局部变量 - nonlocal  - (复制)**    - - → **不能操作全局变量**

```python
# nonlocal可以对父级作用域的变量进行修改，并且在当前作用域创建（复制）一份此变量。
def func():
    count = 0
    def inner():
        nonlocal count
        count += 1
        print(count)
        print(locals())
    inner()
    print(locals())
func()
#UnboundLocalError: local variable 'count' referenced before assignment
#解释器认为：如果你在局部作用域对一个变量进行修改了，
#你在局部作用域已经定义好这个变量了。

```

#### 4. 默认参数的坑

```python
def func(a,b=False):
    print(a)
    print(b)
func(1,True)
#当你的默认参数如果是可变的数据类型，你要小心了。
#⏬
def func(a,l=[]):
    l.append(a)
    return l
print(func(1))  # [1,]
print(func(2))  # [1,2]
print(func(3))  # [1,2,3]

```

### 函数名的应用

#### 1. 函数名指向的是函数的内存地址,加上()就执行这个函数 : → func()

```python
函数名是一个特殊的变量。
def func():
    print(666)
print(func)  # func = <function func at 0x00000000003F1EA0>

```

#### 2. 函数名可以是一个变量。

```python
def func():
    print(666)
f1 = func
f2 = f1
f2()
f1()

```

#### 3. 函数名可以作为容器类类型的元素。

```python
def func1():
    print('in func1')
def func2():
    print('in func2')
def func3():
    print('in func3')
l = [func1, func2, func3]
print(l)
for i in l:
    i()
# 结果:
[<function func1 at 0x10849fea0>, <function func2 at 0x10875f488>, <function func3 at 0x10875f268>]
in func1
in func2
in func3

```

#### 4. 函数名可以作为函数的实参。

```python
a = 1
def func(argv):
    print(argv)
func(a)


def func1():
    print('in func1')
def func2(argv):
    argv()
    print('in func2')
func2(func1)

```

#### 5. 函数名可以作为函数的返回值。

```python
b = 666
def func1():
    print('in func1')
def func2(argv):
    print('in func2')
    return argv
ret = func2(b)
print(ret)


def func1():
    print('in func1')
def func2(argv):
    # argv = func1 : function 43543
    print('in func2')
    return argv
ret = func2(func1)  # func1 : function 43543
ret()



def wrapper():
    def inner():
        print(666)
    return inner
# ret = wrapper()
# ret()
wrapper()()

```

## 2. 格式化输出f

```python
#f不区分大小写
num = input('>>>')
s = F'python{num}'
print(s)


#可以加入表达式
s1 = 'moon'
s2 = f'我的名字{s1.upper()}'
print(s2)


l1 = ['阿坤', 18, 176]
s1 = f'我的名字{l1[0]}，我的年龄{l1[1]}，我的身高{l1[2]}'
print(s1)


#可以结合函数
def func(a,b):
    return a + b
s1 = f'最终的结果{func(1,3)}'
print(s1)


#不能放一些特殊的字符 ! , : { } ;
print(f"替换结果{{{73}}}")
print(f'{12,}')

```

## 3. 可迭代对象

```python
# 字面意思分析 : 可以循环取值的数据集
# list,dict(keys(),values(),items()),tuple,str,set,range, 文件句柄
# 专业角度:内部含有'__iter__'方法的对象,就是可迭代对象.
# 内置函数 :dir()   print(dir(str))
# 判断一个对象是不是可迭代对象 : print('__iter__' in dir(str))
# 优点:
			1.直观	2.操作方法较多
# 缺点:
			1.占内存	2.不能迭代取值(索引,字典的key)

```

### 1. 判断迭代对象

```python
# str  list
# 内置函数：dir()→ 用来查方法
print(dir(str)) # 返回的表中有'__iter__' 就是可迭代对象

print('__iter__' in dir(str)) # True

```

### 2. 迭代器

```python
# 字面意思 :可以迭代取值的工具
# 专业角度 : 内部含有'__iter__'并且'__next__'方法的对象,就是迭代器
# 优点 :
			1. 非常节省内存.	2.惰性机制
# 缺点 :
			1.不直观	2.操作不灵活	3.效率相对低
# 特性
l1 = [22, 33, 44, 55, 66, 77]
obj = iter(l1)
for i in range(3):
    print(next(obj))
for i in range(2):
    print(next(obj))

 
# 可迭代对象与迭代器的对比:
#		可迭代对象：可迭代对象是一个操作比较灵活，直观，效率相对高，但是比较占用内存的数据集。
#		迭代器：迭代器是一个非常节省内存，满足惰性机制，但是效率相对低，操作不灵活的数据集。用空间换时间
#   字典是用时间换空间

```

**利用while循环，模拟for循环内部循环可迭代对象的机制。**

```python
#    先要将可迭代对象转化成迭代器。
#    利用next对迭代器进行取值。
#    利用异常处理try一下防止报错。
s = 'gkffdsa;lfkdsk;lafkds;laldgjfd'
obj = iter(s)
while 1:
     try:
         print(next(obj))
     except StopIteration:
         break

```

```python
with open('调试',encoding='utf-8',mode='w') as f1:
    print(f1)
print(zip('fdsa','fdsagdfsg'))  # <zip object at 0x00000000029B1D88>
# 将zip函数中的两个可迭代对象参数按对应索引值进行匹配组合，得到zip对象。（拉链式函数）

```

### 3. 可迭代对象转化成迭代器 iter()

```python
l1 = [1, 2, 3, 4, 5]
# 内置函数iter()
obj = iter(l1)  # l1.__iter__()
print(obj)  # <list_iterator object at 0x0000000001DEA2E8>

```

### 4. 迭代器可以迭代取值。利用next()进行取值

```python
l1 = [1, 2, 3, 4, 5]
# 内置函数iter()
obj = iter(l1)
print(obj)  #<list_iterator object at 0x1055828d0>
print(next(obj)) # 1
print(next(obj)) # 2
print(next(obj)) # 3
print(next(obj)) # 4
...
#迭代器一条路走到底，不走回头（记录位置）。
# next超过元素会报错

```

```python
for i in range(3):
    print(next(obj))
    
for i in range(2):
    print(next(obj))

```

## 4. 生成器

### 1. 生成器函数 yield

```python
def func():
    print(111)
    return 2
ret = func()
print(ret)
# 结果 :
111
2
# 执行此函数，遇到return结束函数。
# 将数字2返回给ret。

```

```python
def func():
  print(111)
  yield 222
  yield 333
func()
# 结果 : 无


def func():
  print(111)
  yield 222
  yield 333
  yield 2,3,4
ret = func()
print(next(ret)
print(next(ret)   
print(next(ret)
print(next(ret)   
# 结果:
111
222
333
(2,3,4)
5.0
++++++++++++++++++++++++++++++++     
++++++++++++++++++++++++++++++++
# 01
a = 5
def func():
	global a
	a = 1
	yield 1
func()
print(a)
# 结果 :5
============================
# 02
a = 5
def func():
	global a
	a = 1
	yield 1
func()
print(next(func()))
print(a)
# 结果 :
1
1
============================
# 03
def func():
	yield 1
	print('哈哈')
func()
# 结果 :空

# 总结 : 在带有yield的函数中,若没有执行next(),则yield前后都不会执行

```

**与迭代器一样,当程序运行完最后一个yield,再次运行next(),程序会报错**

**说明一个yield对应一个next,next超过yield数量,就会报错**

```python
# 只要函数中出现了yield那么他就不是函数，它是生成器函数。
# 一个next对应一个yield.
print(next(ret))
print(next(ret))
print(next(ret))
print(next(ret))

# return yield
# return 结束函数，给函数的执行者返回值(多个值通过元组的形式返回)。
# yield  不结束函数，对应着给next返回值(多个值通过元组的形式返回)。

```

**yield与return的区别:**

- return一般在函数中设置一个,,他的作用是终止函数,并且给函数的执行者返回值
- yield在生成器函数中可设置多个,且并不会终止函数,next会获取对应yield生成的元素

```python
# 举例说明：
def eat_baozi():
    list1 = []
    for i in range(1,2001):
        list1.append(f'{i}号包子')
    return list1
print(eat_baozi())

def eat_baozi_gen():
    for i in range(1,2001):
        # print(11)
        yield f'{i}号包子'
ret = eat_baozi_gen()  #这是一个生成器
print(ret)
# 结果 :<generator object eat_baozi_gen at 0x0000020584B84CA8>
print(next(ret))  # 生成器,可以用next()函数一个一个打印出来
print(next(ret))
# 结果
1号包子
2号包子


#下一次打印的包子序号会接着上一次打印,也就是说,生成器会停留在最后一次打印(取出)元素的位置上
ret = eat_baozi_gen()
for i in range(200):
    print(next(ret))
for i in range(200):
    print(next(ret))

```

```python
def func():
    l1 = [1, 2, 3]
    yield l1
ret = func()
print(next(ret))
print(next(ret))
print(next(ret))
因为函数中yield只有一个,而next()有多个,所有会报错

```

**yield from** :

**可以直接把迭代对象中的每一个数据作为生成器的结果进行返回**

```python
def func():
    l1 = ['one', 'two', 'three']
    yield from l1
    yield 1
    yield 2
    yield 3
ret = func()
print(next(ret))
print(next(ret))
print(next(ret))
print(next(ret))
print(next(ret))
"""
结果:
one
two
three
1
2
"""
# yield : 对应next  给next返回值
# yield from 将一个可迭代对象的每一个元素返回给next
# yield from 节省代码，提升效率（代替了for循环）

```

### 2. 推导式 

#### 1. 列表推导式

```python
l1 = [1,2,3......100]
l1 = []
for i in range(1,101):
    l1.append(i)
print(l1)

# 列表推导式
l1 = [i for i in range(1, 101)]
print(l1)

```

**列表推导式的两种构建方式**

```python
# 1.循环模式： [变量(加工后的变量) for 变量 in iterable]
# 2.筛选模式： [变量(加工后的变量) for 变量 in iterable if 条件]

```

- 1. 循环模式 :

     ```python
     # 将10以内所有整数的平方写入列表。
     print([i**2 for i in range(1, 11)])
     
     # 100以内所有的偶数写入列表.
     print([i for i in range(2, 101, 2)])
     
     # 从python1期到python100期写入列表list
     print([f'python{i}期' for i in range(1, 101)])
     
     ```

- 2. 筛选模式 :

     ```python
     #一百以内大于49的数的列表
     print([i for i in range(1, 101) if i > 49])
     
     # 三十以内可以被三整除的数。(列表)
     print([i for i in range(1, 31) if i % 3 == 0])
     
     # 过滤掉长度小于3的字符串列表，并将剩下的转换成大写字母
     l1 = ['barry', 'fdsaf', 'alex', 'sb', 'ab']
     print([i.upper() for i in l1 if len(i) > 3])
     
     # 找到嵌套列表中名字含有两个‘e’的所有名字（有难度）
     names = [['Tom', 'Billy', 'Jefferson', 'Andrew', 'Wesley', 'Steven', 'Joe'],
              ['Alice', 'Jill', 'Ana', 'Wendy', 'Jennifer', 'Sherry', 'Eva']]
     l1 = []
     for i in names:
         for j in i:
             if j.count('e') == 2:
                 l1.append(j)
     print(l1)
     
     print([j for i in names for j in i if j.count('e') > 1])
     
     ```

- 列表推导式的优缺点：

```python
# 优点：
    # 1， 简单，快捷，装b。
# 缺点：
    # 2. 可读性不高，不好排错。

# 慎用，不要入迷。

```

#### 2. 生成器表达式

```python
# 生成器表达式：
# 与列表推导式几乎一模一样。
# 循环模式，筛选模式。

obj = (i for i in range(1, 11))
print(obj)
print(next(obj))
print(next(obj))
print(next(obj))

```

```python
# 如何触发生成器（迭代器）取值？
1. next(obj)
2. for 循环
# for i in obj:
#     print(i)
3. 数据转化
# print(list(obj))

# 生成器表达式：生成器 节省内存。

```

```python
# 字典推导式，集合推导式：  两种模式： 循环模式，筛选模式

l1 = ['小潘', '怼怼哥','西门大官人', '小泽ml亚']
# {0： '小潘', 1： '怼怼哥', 2: '西门大官人'}
dic = {}
for index in range(len(l1)):
    dic[index] = l1[index]
 print(dic)
# {0： '小潘', 1： '怼怼哥', 2: '西门大官人'}

print({i:l1[i] for i in range(len(l1))})
# {0： '小潘', 1： '怼怼哥', 2: '西门大官人'}


# 1~100
print({i for i in range(1, 101)})

```

## 5. 匿名函数

匿名函数只能构建简单的函数,一句话函数   一般与lambda配合使用

```python
def func(x,y):
    return x + y
# print(func(1, 2))

# 匿名函数构建
func2 = lambda x,y: x + y
print(func2(1, 2))

# 匿名函数最常用的就是与内置函数结合使用。

# 写匿名函数：接收一个可切片的数据，返回索引为 0与2的对应的元素（元组形式）。
func = lambda x: (x[0],x[2])
print(func('太白金星'))

# 写匿名函数：接收两个int参数，将较大的数据返回。
func1 = lambda x, y: x if x > y else y
print(func1(100,2))

func2 = lambda : 3
print(func2()) # 3

```

```python
函数:
# str() dir() range() len() print() max() min() open()
# input() type() int() enumerate() list() id() set() dict()
# iter() next() tuple() bool() globals() locals() frozenset()

```

## 6. 内置函数

```python
# eval exce     慎用

eval:
s1 = "{1: 'alex'}"  →  print（eval(s1)） 输出结果 :{1: 'alex'}
s2 = '1 + 3'    →eval(s2) 输出结果 :4 
eval 剥去字符串的外衣，返回里面的本质
# 前提条件 是字符串(str)
	若字符串里面的是数字,且里面有运算,则会直接输出结果
    
    
# exec 执行字符串类型的代码,(执行str里面的可执行代码)

s3 = '''
    for i in range(3):
         print(i)
     '''
exec(s3)
# 结果 : 执行s3里面的for循环,打印:0 1 2

```

```python
# hash() 获取一个可哈希对象(int ,str ,bool,tuple..)的值
print(hash(123214134))
print(hash('fkljdsaklgjdfs'))
print(hash('gjdfs'))
\
# help() 查看函数或模块用途的详细说明
print(help(str.count))
\
# callable  ** 用于查看一个人对象是否可调用,若返回True,程序可能会报错,但是返回False.肯定会失败
name = 'alex'
def func():
    pass
print(callable(name))  # False
print(callable(func))  # True
\
# int  ** 用于将一个字符串或数字转化为整型
print(int(3.14))
print(int('123'))
\
print(float(100)) # 将整数和字符串转换成浮点数
\
print(complex(1,2)) #函数用于创建一个值为 real + imag * j 的复数或者转化一个字符串或数为复数。如果第一个参数为字符串，则不需要指定第二个参数。。
\
print(bin(100))  # 将十进制转化成二进制。 **
\
print(oct(10)) # 将十进制转化成八进制字符串并返回。
\
print(hex(17)) # 将十进制转化成十六进制字符串并返回。 **

# 将其他进制转换成10进制首先知道是什么进制）：
print(int('1010',2))
print(int('12',8))
print(int('a',16))

\
print(divmod(10, 3)) # 结果:(3, 1)  **
# 计算除数与被除数的结果，返回一个包含商和余数的元组(a // b, a % b)分页用到
\
print(round(3.1485926,2)) #结果 :print(round(3.1485926,2))
# 保留小数的有效位置 默认保留整数,保留遵循四舍五入原则
\
print(pow(3, 3))  # 求x的y次幂.(三个参数为x**y的结果对z取余)
print(pow(3, 3, 2))
\
print(ord('a')) # 输入字符寻找其在unicode的位置。
print(ord('中'))
\
print(chr(98))  # **  # 输入位置数字找出其对应的字符
print(chr(20104))  # 予
\
print(repr('太白'))  #  结果 :'太白'   repr 原形毕露  **
\
l1 = [1, 'fgdsa', [], {1: 2}]
l2 = [0, '', [], {}]
print(all(l1)) # 判断可迭代对象元素全部都为True，返回True
print(any(l2))  # 判断可迭代对象元素只要有一个True返回True

```

```python
sep # 设定分割符。
end # 默认是换行可以打印到一行
print(1, 2, 3, sep='|')
print(1, 2, end=' ')
\
print(3, 4)
f = open('log','w',encoding='utf-8')
 # f.write('写入文件')
print('写入文件', file=f)
\
list
# l1 = list('fdsafd')
# print(l1)
\
dict
# 创建字典的几种方式
dic = {1: 2}
dic = dict(one=1, two=2, three=3)
dic = dict.fromkeys(可迭代对象,每一个key的值) # 值都是同一个值
print({i: 1 for i in range(3)}) # 值都是1
\
# 字典推导式
print({i: 1 for i in range(3)})
\
# abs()  获取绝对值
print(abs(-10))
\
# sum() 数字相加求和
# sum(iterable,)
print(sum([1,2,3,4]))
print(sum([1, 2, 3, 4], 100)) # 结果 : 110


#####  非常非常非常重要的  #####

# min 可以加功能
print(min([22, 11, 45, 2]))  # 结果 : 2

#找年龄最小的元组
l1 = [(73, 'alex'), (35, '武大'), (18, '太白')]
print(min(l1)) #返回的是这个组成列表的元组  (18, '太白')

l1 = [('alex', 73, 170), ('太白', 18, 185), ('武大', 35, 159),]
# # 通过设置key去使用min
# # key = 函数名
# # def func(x):  # x = ('alex', 73)
# #     return x[1]

# # 返回值是什么就按照什么比较最小的。

# # min 会自动的将可迭代对象的每一个元素作为实参传给x，
'''
第一次，x = ('alex', 73)   73
第二次，x = ('武大', 35)   35
第三次，x = ('太白', 18)   18
'''

# 将遍历的那个元素即是 ('太白', 18) 返回
# print(min(l1,key=func))
# print(min(l1,key=lambda x: x[1]))


# def func(x):
#     return x[1]
# print(min(l1,key=func))
# print(min(l1,key=lambda x: x[1]))
# print(min(l1,key=lambda x: x[2])[0])
\
\
\
# 练习：
dic = {'a':3,'b':2,'c':1}
# 将dic值最小的键返回。
print(min(dic,key= lambda x:dic[x]))
\
# 将dic值最小的值返回。
print(dic[min(dic,key= lambda x:dic[x])])
\
dic = {'A':['李业', 67],'b': ['怼哥', 95],'c': ['冯垚', 85]}
# 将成绩最低的从属于的那个列表返回。
print(dic[min(dic,key=lambda x:dic[x][1])])
# 将成绩最低的分数返回。
print(dic[min(dic,key=lambda x:dic[x][1])][1])


# max() 与min 用法相同。


# reversed()  对一个可迭代对象进行翻转，返回一个迭代器
s1 = 'alex'
print(reversed(s1)) #// <reversed object at 0x0000023442C3B278>
for i in reversed(s1):
	print(i)
# 结果 :
x
e
l
a

#bytes()
s1 = '太白'
# 方法一：
print(s1.encode('utf-8')) #  b'\xe5\xa4\xaa\xe7\x99\xbd'
# 方法二：
print(bytes(s1,encoding='utf-8')) #  b'\xe5\xa4\xaa\xe7\x99\xbd'


# 解码：
b1 = b'\xe5\xa4\xaa\xe7\x99\xbd'
# 方法一：
print(b1.decode('utf-8'))
# 方法二：
 print(str(b1, encoding='utf-8'))

```

```python
# 继续min()

dic = {'c': 1, 'b': 2, 'a': 3}
# 最小的值对应的键返回
print(min(dic))
print(min(dic,key=lambda x:dic[x]))
# min 会自动将dic的每个key依次传给x,返回值设定什么，就按照什么比较大小。
# 最后将x返回。
# 最小的值对应的值返回
print(dic[min(dic, key=lambda x:dic[x])])

list = [
    {'name': 'alex', 'age': 73},
    {'name': 'wusir', 'age': 35},
    {'name': '太白', 'age': 25},
 ]
# 将年龄最小的 字典返回。
print(min(list,key=lambda x: x['age']))
# 将年龄最小的名字返回。
print(min(list,key=lambda x:x['age'])['name'])
# 将年龄最小的年龄返回。
print(min(list,key=lambda x: x['age'])['age'])

# zip 拉链方法 返回一个迭代器
#函数用于将可迭代的对象作为参数,将对象中对应的元素打包成一个个元组,
#然后返回由这些元祖组成的内容,如果各个迭代器的元素个数不一致,则按照长度最短的返回，
l1 = [1, 2, 3, 4]
tu = ('a', 'b', 'c')
s = 'python23'
# # print(zip(l1,tu,s))
print(list(zip(l1,tu,s)))
#结果 :[(1, 'a', 'p'), (2, 'b', 'y'), (3, 'c', 't')]

# sorted 排序
l1 = [2, 6, 4, 1, 3]
# 列表原有的方法
l1.sort()
print(l1)
# 形成新列表
print(sorted(l1))
print(l1)

list1 = [
    {'name': 'alex', 'age': 73},
    {'name': 'wusir', 'age': 35},
    {'name': '太白', 'age': 25},
]
# 加key
print(sorted(list1))
print(sorted(list1, key=lambda x:x['age']))
print(sorted(list1, key=lambda x:x['age'],reverse=True))
#
l1 = [('张一东', 80), ('张耳洞', 75), ('怼怼哥', 7), ('李业', 59)]
print(sorted(l1,key=lambda x:x[1]))
print(sorted(l1,key=lambda x:x[1],reverse=True))

# filter  返回一个生成器
# 生成器表达式的筛选模式
l1 = [56, 67, 12, 34, 78, 90,]
print([i for i in l1 if i > 60])
# 返回值为True的留下来
print(filter(lambda x: x>60,l1)) # <filter object at 0x000002E5453CB278>
print(list(filter(lambda x: x>60,l1)))# [67, 78, 90]
#
lst = [{'id':1,'name':'alex','age':50},
       {'id':1,'name':'wusir','age':17},
        {'id':1,'name':'taibai','age':16},]
print(list(filter(lambda x:x['age']<30,lst)))

# map 返回一个迭代器，相当于生成器表达式：循环模式
l1 = [56, 67, 12, 34, 78, 90,]
print([i**2 for i in l1])
print(map(lambda x:x**2,l1))
print(list(map(lambda x:x**2,l1)))

# reduce python3x 从内置函数剔除了。
作用是先把列表中的前俩个元素取出计算出一个值然后临时保存着,
接下来用这个临时保存的值和列表中第三个元素进行计算,求出一个新的值将最开始
临时保存的值覆盖掉,然后在用这个新的临时值和列表中第四个元素计算.依次类推
from functools import reduce # 引入模内置块
'''
第一次：x,y 1,2 求和 3 记录到内存
第二次：x,y 3,3 求和 6 记录到内存
第三次：x,y 6，4 .........

'''
# print(reduce(lambda x,y: x+y,[1,2,3,4,5]))
# print(reduce(lambda x,y: 2*x+y, [1,2,3]))
# print(reduce(lambda x,y: x+y, ['alex','s','b']))  # 可以用字符串拼接



```

## 7. 闭包

```
什么是闭包:
	闭包是存在嵌套函数当中的,内层函数对外层函数的非全局变量的引用,这样就会产生闭包,引用的变量也就是自由变量,不会随着函数的结束而消失,会一直保存在内存中,最终的目的就是保证了数据的安全

```

```
闭包的形成条件:
    1.闭包存在于嵌套函数中
    2.内存函数对外层非全局变量引用(改变)
    (参考函数名逐层返回直至返回到最外层)

```

```
闭包:
	闭包函数的空间不会随着函数的结束而消失
	被引用的变量也不会消失
	被引用的变量叫自由变量

```

```python
# 第一版： 没有保证数据的安全
l1 = []  #全局变量
def make_average(price):
    l1.append(price)
    total = sum(l1)
     return total/len(l1)
print(make_average(100000))
print(make_average(110000))
print(make_average(120000))

# 有很多代码....

# l1.append(666) 不小心输入个append就会是数据不准确
# print(make_average(90000))



# 第二版：
# 每次执行l1是空的。
def make_average(price):
    l1 = []
    l1.append(price)
    total = sum(l1)
    return total/len(l1)
print(make_average(100000))
print(make_average(110000))
print(make_average(120000))

# 为了保证数据的安全，闭包
def make_average():
    l1 = []
    def average(price):
        l1.append(price)
        total = sum(l1)
        return total/len(l1)
    return average
avg = make_average()
# print(avg)
print(avg(100000))
print(avg(110000))
print(avg(120000))
# print(globals())

def make_average():
     count = 1
    def average():
        nonlocal count
        count += 1
        return count
    return average
avg = make_average()
print(avg)
print(avg())
print(avg())
print(avg())
print(avg())





# 例一：
def wrapper():
    a = 1
    def inner():
        print(a)
    return inner
ret = wrapper()

# 例二：
a = 2
def wrapper():
    def inner():
        print(a)
    return inner
ret = wrapper()

# 例三：
def wrapper(a,b):
    def inner():
        print(a)
        print(b)
    return inner
a = 2
b = 3
ret = wrapper(a, b)

# 判断一个函数是不是闭包 == 闭包函数有没有自由变量
print(ret.__code__.co_freevars)


# 了解
print(ret.__code__.co_varnames)  # 函数中的局部变量

# 闭包的应用：
# 1，保证数据的安全。
# 2，装饰器的本质。

```

## 8. 装饰器

### 1. 开放封闭原则

​	软件在制作时,不可能把所有功能都设计好,等上线后,后续按需求增加功能,定期迭代更新,对于软件之前写的源代码一般不会修改(函数里面的代码以及函数的调用方式)

`开放原则 :`在源码不改变的情况下,增加一些额外的功能

`封闭原则 :`不改变源码

`python中的装饰器 :`完美的诠释了开放封闭原则

`装饰器 :`装饰器就是一个函数,它要装饰一个函数,在不改变原函数的源代码以及调用方式的前提下,给其增加一些			额外的功能

### 2. 初识装饰器

```python
# 1 李业，在一家xx科技有限公司工作，主管安排了一个任务，
# 写一个代码测试怼怼哥写的函数的执行效率。
import time
def index():
	time.sleep(2)
	print('欢迎访问博客园首页')
start_time = time.time()
index()
end_time = time.time()
print(f'此函数的执行效率{end_time-start_time}')

```

```python
# 2. 主管让你测试小邓，李大象,重复代码太多。
def func1():
	time.sleep(2)
	print('欢迎访问日记首页')

def func2():
	time.sleep(1)
	print('欢迎访问评论首页')
  
start_time = time.time()
func1()
end_time = time.time()
print(f'此函数的执行效率{end_time-start_time}')

start_time = time.time()
func2()
end_time = time.time()
print(f'此函数的执行效率{end_time-start_time}')

```

```python
# 3.  整合到函数中
def func1():
    time.sleep(2)
    print('欢迎访问日记首页')

def func2():
		time.sleep(1)
		print('欢迎访问评论首页')

def test_time(x):
    start_time = time.time()
    x()
    end_time = time.time()
print(f'此函数的执行效率{end_time-start_time}')

test_time(func1)
test_time(func2)

```

```python
# 4. 怼怼哥这个函数在实际项目中被500执行，主管要求：在被执行此函数时，
# 同时要测试一下被执行函数的效率。

def index():
    time.sleep(2)
    print('欢迎访问博客园首页')
index()

def test_time(x):
    start_time = time.time()
    x()
    end_time = time.time()
    print(f'此函数的执行效率{end_time-start_time}')
test_time(index)

```

```python
# 版本4的问题： 开放原则满足了，封闭原则：不改变原函数的源码，以及调用方式。
# 违反了封闭原则：改变了函数的调用方式。
# 版本5： 不能改变原函数的调用方式（闭包）：

def index():
		time.sleep(2)
		print('欢迎访问博客园首页')
		index()
		
def func1():
    time.sleep(2)
    print('欢迎访问日记首页')
def test_time(x):  # x = index
		def inner():
		start_time = time.time()
		x()
		end_time = time.time()
		print(f'此函数的执行效率{end_time-start_time}')
		return inner

index = test_time(index)
index()

```

```python
# 语法糖 @加上装饰器函数的名

def test_time(x):  # x = index
		def inner():
		start_time = time.time()
		x()
		end_time = time.time()
		print(f'此函数的执行效率{end_time-start_time}')
		return inner
  
@test_time  # index = test_time(index)
def index():
		time.sleep(2)
		print('欢迎访问博客园首页')
index()

@test_time
def func1():
		time.sleep(2)
		print('欢迎访问日记首页')
    
@test_time
def func2():
		time.sleep(1)
		print('欢迎访问评论首页')
 

func2 = test_time(func2)
func3 = test_time(func3)

# func2()

'''100行代码'''

# index()


'''10行代码'''

# index()

'''50行代码'''

# index()

```

```python
# 版本6：被装饰函数有返回值

def test_time(x):  # x = index
		def inner():
		start_time = time.time()
		ret = x()
		end_time = time.time()
		print(f'此函数的执行效率{end_time-start_time}')
		return ret
return inner

@test_time  # index = test_time(index)
def index():
		time.sleep(0.5)
		print('欢迎访问博客园首页')
		return True
print(index())  # inner()

# 你应该是让True返回给index()这样才完美了，但是现在index是inner，所以你要是完全不改变原函数的使用，
# 你print(index()) ---> True

```

```python
# 版本7： 被装饰函数带参数，无论加不加装饰器，你的实参'太白金星'应该传给形参n,。
# 但版本6不能实现传参，index('太白金星') ==  inner('太白金星')

def test_time(x):  # x = index
    def inner(*args,**kwargs):
        # 函数的定义：* ** 聚合。
        start_time = time.time()
        ret = x(*args,**kwargs)
        # 函数的执行：* ** 打散。
        end_time = time.time()
        print(f'此函数的执行效率{end_time-start_time}')
        return ret
    return inner
@test_time  # index = test_time(index)
def index(n):
	time.sleep(0.5)
	print(f'欢迎{n}访问博客园首页')
	return True

@test_time  # index = test_time(index)
def func2(a,b):
		time.sleep(0.5)
		print(f'最终结果：{a+b}')
		return a + b
print(index('苹果'))  # inner('苹果')
print(func2(1,3)) # == inner(1,3)


def warpper(f):
		def inner(*args,**kwargs):
		'''被装饰函数之前的操作'''
		# print(666)
		ret = f(*args,**kwargs)
		'''被装饰函数之后的操作'''
		# print('执行完毕了')
		return ret
return inner

@warpper
def func():
		print(111)

func()
func()
func()


# 装饰器的应用：在不改变原函数的源码以及调用方式前提下，为其增加额外的功能。
# 登陆认证，打印日志等。

```

**装饰器的标准写法**

```python
##装饰器标准写法
def test_(func):
    def inner(*args,**kwargs):
        '执行被装饰函数之前的操作'
        ret = func(*args,**kwargs)
        """执行被装饰函数之后的操作"""
        return ret
    return inner

```

```python
#登录构架
flag = False
def auth(f):
    def inner(*args,**kwargs):
        if flag:
            '''被装饰函数之前的操作'''
            # 登陆认证：
            # 输入用户名，输入密码
            ret = f(*args,**kwargs)
            '''被装饰函数之后的操作'''
            return ret
        else:
            pass
    return inner


@auth
def article():
    print('欢迎访问文章页面')

@auth
def diary():
    print('欢迎访问日记页面')
    
@auth
def comment():
    print('欢迎访问评论页面')

article()
diary()
comment()

```

### 3. 带参数的装饰器

```python
def wrapper(f):
	def inner(*args,**kwargs):
		if f._name_ =='qq':
			ret = f(*args,*kwargs)
			return ret
		else:
			pass
	return inner


def wrapper(f):
    def inner(*args, **kwargs):
        ret = f(*args, **kwargs)
        return ret
    return inner


def wrapper_out(n,*args,sex='男',):
    def wrapper(f):  # f
        def inner(*args,**kwargs):
            ret = f(*args,**kwargs)  # func1()
            return ret
        return inner
    return wrapper

func = wrapper_out(1)  # wrapper函数名
ly = func(func1)  # wrapper(func1) = inner
ly()  # inner()



def wrapper_out(n):
    def wrapper(f):
        def inner(*args,**kwargs):
            # if n == 'qq':
            #     username = input('请输入用户名：').strip()
            #     password = input('请输入密码：').strip()
            #     with open('qq',encoding='utf-8') as f1:
            #         for line in f1:
            #             user,pwd = line.strip().split('|')
            #             if username == user and password == pwd:
            #                 print('登陆成功')
            #                 ret = f(*args,**kwargs)
            #                 return ret
            #         return False
            # elif n == 'tiktok':
            #     username = input('请输入用户名：').strip()
            #     password = input('请输入密码：').strip()
            #     with open('tiktok', encoding='utf-8') as f1:
            #         for line in f1:
            #             user, pwd = line.strip().split('|')
            #             if username == user and password == pwd:
            #                 print('登陆成功')
            #                 ret = f(*args, **kwargs)
            #                 return ret
            #         return False
            username = input('请输入用户名：').strip()
            password = input('请输入密码：').strip()
            with open(n,encoding='utf-8') as f1:
                for line in f1:
                    user,pwd = line.strip().split('|')
                    if username == user and password == pwd:
                        print('登陆成功')
                        ret = f(*args,**kwargs)
                        return ret
                return False
        return inner
    return wrapper



@wrapper_out('qq')
def qq():
	print('成功访问qq')
qq()
# # 看到带参数的装饰器分两步执行：
# @wrapper_out('腾讯')
#     1. 执行wrapper_out('腾讯') 这个函数，把相应的参数'腾讯' 传给 n,并且得到返回值 wrapper函数名。
#     2. 将@与wrapper结合，得到我们之前熟悉的标准版的装饰器按照装饰器的执行流程执行。
@wrapper_out('qq')
def qq():
	print('成功访问qq')

@wrapper_out('tiktok')
def tiktok():
	print('成功访问抖音')

qq()
tiktok()
# 开发思路：增强耦合性

```

### 4. 多个装饰器装饰一个函数

```python
针对@ -→ 
装饰函数之前依次从上到下执结果输出, 
执行函数
装饰函数之后依次从后往前结果输出

```

```python
def wrapper1(func1):  #　func1 = f原函数
    def inner1():
        print('wrapper1 ,before func')  # 2
        func1()
        print('wrapper1 ,after func')  # 4
    return inner


def wrapper2(func2):  # func2 == inner1
    def inner2():
        print('wrapper2 ,before func')  # 1
        func2()  # inner1
        print('wrapper2 ,after func')  # 5
    return inner2


@wrapper2  # f = wrapper2(f) 里面的f == inner1  外面的f == inner2
@wrapper1  # f = wrapper1(f) 里面的f == func1  外面的 f == inner1
def f():
    print('in f')  # 3
f()  # inner2()

```

### 5. 递归函数

```python
#  初识递归。
def func():
    print('in func')
def func1():
    func()
func1()


#比如：
def func():
    print(666)
    func()
func()


def func(n):
    print(n)
    n += 1
    func(n)
func(1)


# 官网规定：默认递归的最大深度1000次。
# 如果你递归超过100次还没有解决这个问题，那么执意使用递归，效率很低。
import sys
print(sys.setrecursionlimit(1000000))
def func(n):
    print(n)
    n += 1
    func(n)
func(1)


1  太白   18
2  景女神  18 + 2
3  宝元    18 + 2 + 2
4  alex    18 + 2+ 2+2  age(4) = age(3) + 2

def age(n):
    if n == 1:
        return 18
    else:
        return age(n-1) + 2
print(age(4))



def age(4):
    if n == 1:
        return 18
    else:
        return age(3) + 2
age(4) = age(3)  + 2



def age(3):
    if n == 1:
        return 18
    else:
        return age(2) + 2
age(4) = age(2) + 2  + 2



def age(2):
    if n == 1:
        return 18
    else:
        return age(1) + 2
age(4) = age(1) + 2 + 2  + 2    



def age(1):
    if n == 1:
        return 18
    else:
        return age(1) + 2
age(4) = 18 + 2 + 2  + 2    

'''



l1 = [1, 3, 5, ['太白','元宝', 34, [33, 55, [11,33]]], [77, 88],66]
1
3
5
'太白'
'元宝'
34
66

l1 = [1,3,5,['太白','元宝',34],55]
l2 = [1, 3, 5, ['太白','元宝', 34, [33, 55, [11,33]]], [77, 88],66]
for i in l1:
	if type(i) == list:
		for j in i:
			print(j)
	else:
		 print(i)



def func(alist):
    for i in alist:
        if type(i) == list:
            func(i)  # func(['太白','元宝',34])
        else:
            print(i)
func(l1)
func(l2)

```

## 9. 模块

### 1. 模块的定义与分类

什么是模块 : 一个py文件就是一个模块

模拟博客园系统作业，100000行代码. 不可能全部存在一个文件.

1. 不易维护.
2. 效率低.

分文件: 10个文件.每个文件有50个函数,有一写相同功能或者相似功能的函数.代码冗余,重复性.我们应该将这10个函数提取出来,放在一个文件中,随用随拿.

1. 节省代码.
2. 容易维护,组织结构更清晰.

一个模块就是一个py文件,这个模块存储很多相似的功能,相似的函数的集合体.

模块的分类:

- 内置模块,标准库.python解释器自带的,time,os,sys,等等.200多种.
- 第三方库(模块),各种大神写的一些模块,通过pip install....安装.6000种.
- 自己写的模块.自定义模块.

### 2. import

```python
# import tbjx
# # 当我引用tbjx模块的时候,实际上将tbjx.py执行一遍,加载到内存.
# import tbjx
# import tbjx
# import tbjx

# 只是第一次引用时,将此模块加载到内存.

```

- 执行文件:02 模块import
- 被引用文件(模块): tbjx.py

**第一次导入模块发生的三件事**

```python
import tbjx
n = 1
# 引用模块发生三件事.
'''
    1. 将tbjx.py文件加载到内存.
    2. 在内存中创建一个以tbjx命名的名称空间.
    3. 通过tbjx名称空间的名字.的方式引用此模块的名字(变量,函数名,类名等等).
'''

# print(tbjx.name)
# tbjx.read1()
# tbjx.read2()

```

### 3. 被导入模块有独立的名称空间

```python
# 坑:通过tbjx.的方式引用此模块的名字时,一定一定是从此模块中寻找.
# 通过import 引用模块 他有自己的独立名称空间,与当前执行文件没有关系.
name = '李业'
print(tbjx.name)

def read1():
    print('in 02 模块import')

tbjx.read1()

```

### 4. 为模块起别名

```python
# 起别名:将一个比较长的模块名化简成简单的.
# import contextlib as cb
# 1 书写方便.
# import tbjx as tb
# print(tb.name)
# tb.read1()
# 2 简化代码.

```

### 5. 导入多个模块

```python
# import time,os,sys  # 不推荐.
import time
import os
import sys

# 易于阅读 易于编辑 易于搜索 易于维护。

```

### 6. from... import...

```python
# from tbjx import name
# from tbjx import read1
# print(globals())
# 相当于从tbjx模块的全局空间中将name,read1变量与值的对应关系
# 复制到当前执行文件的全局名称空间中.
# print(name)
# read1()

# 优点:使用起来方便了.
# 缺点:容易与当前执行文件产生覆盖效果.

```

### 7. from... import...的使用

```python
# 示例1:
# from tbjx import name
# from tbjx import read1
# name = '李业'
# print(name)

# 示例2:
# name = '怼怼哥'
# from tbjx import name
# from tbjx import read1
# def read1():
#     print('在执行文件中')
# # print(name)
# read1()

# 特殊情况:极值情况,工作中不会出现.(了解)
# 因为如果你要是引用一些模块的变量,那么执行文件中就不应该出现同名变量.
# 示例3:
# from tbjx import name
# from tbjx import change
#
# change()
# print(name)

# 示例4:
# from tbjx import change
#
# change()
# from tbjx import name
# print(name)

# 也可以起别名
# from tbjx import name as n
#
# print(n)

```

**一行导入多个**

```python
# 导入多个名字
# from tbjx import name
# from tbjx import read1

# from ... import *  尽量别单独用
# from tbjx import *
# print(name)
# read1()
# read2()
# 1,全部将tbjx的所有名字复制过来,无用功.
# 2,容易覆盖.

```

### 8. from... import *

```python
from   模块名  import  引用的函数或其他
 
from ...import * 与__all__配合使用(写在模块开头写上:_all_ = ['引用变量名1','引用变量名2'])
 
# from tbjx import *
#
# # read1()
# # read2()
# change()

```

### 9. py文件的两种功能

1. py文件的第一个功能:执行文件(承载代码) 脚本.

   直接打印`__name__`返回`__main__`

   调试模块:

   `if _name_=='_main_':`

   ​	`被调试的函数`

   **这样,被调试的函数只会在本py文件中执行,当被当做模块调用的时候不会执行**

2. py文件的第二个功能: 模块(被执行文件).

   直接打印`__name__`返回`tbjx` 模块名

作用:用来控制.py文件在不同的应用场景下执行不同的逻辑（或者是在模块文件中测试代码）

```
# import tbjx
# import time
# print(time.time())
# # import tbjx
# # tbjx.read1()
# import tbjx1
# tbjx1.read1()

```

### 10. 模块的搜索路径

```python
# 寻找模块的路径: 内存 ----> 内置模块  ---> sys.path中找
# 只要这三个地方:内存 内置模块 sys.path可以找到这个引用的模块的路径,这个模块就可以直接引用到.
# import sys
# # print(sys.path)
# # import tbjx
# print(sys.modules)

# 如何引用到tbjx1.py
import sys
# print(sys.path) -- 是一个列表
sys.path.append(r'D:\s23\day15')
# import tbjx
import tbjx1
tbjx1.read1()

```

## 10. 序列化模块

**序列化模块 :**将一个数据结构 ( list,dict… ) 转换成一个特殊的序列( 特殊的字符串 )的过程

```python
# l1 = [1, 2, 3]
# ret = str(l1)
# print(ret,type(ret))
# print(eval(ret))  # 不让用

# 文件存取时,遇到的矛盾.
# dic ={'username': '太白', 'password': 123}

# dic = {1: {'username': '太白', 'password': 123,'status': False},
#        2:{'username': 'alex', 'password': 123,'status': False}

# 这个字典能放在全局么? (不可以,当数据多的时候,加载消耗时间)
# with open('register.json',encoding='utf-8',mode='w') as f1:
#     f1.write(str(dic))
# with open('register',encoding='utf-8') as f1:
#     ret = f1.read()
#     print(ret,type(ret))
#
# # 数据结构 --- > str() 存储在文件, 读取出来时,反转不回去.
# # 网络传输.
# l1 = [i for i in range(100000)]
# # 凡是数据通过网络传出去最终的格式必须bytes
# s1 = str(l1)
# b1 = s1.encode('utf-8')
# print(b1)  # b1可以发送出去
#
# s2 = b1.decode('utf-8')
# print(s2,type(s2))
# s2 转化不成列表了.

# 我们现在要解决的问题: 如果有一种特殊的字符串,这个字符串可以与任何的数据结构互相转换.

```

#### 1. 序列化模块

```python
# 序列化模块: 将一种数据结构转化成特殊的序列(特殊的字符串,bytes)并且还可以反转回去.

    # json模块: 是所有语言公认的一种序列.最最常用的
    #所以支持的python数据结构有限: int str bool dict list(tuple),None,float

    # None  ---> Null ----> NUll
    # dict  --->
    # pickle模块: 只能python语言中使用的,序列化模块:
    # 支持python所有的数据类型以及对象.
    # shevle模块(不讲): 课下了解(只能是文件存取).

```

#### 2. json序列化

**json序列换化--是所有语言公认的一种序列.最最常用的**

两对 四个 方法:

dumps,loads 主要用于网络传输,可以用于文件的读取

```python
import json
# dumps,loads 主要用于网络传输,可以用于文件的存取.
dic = {'username': '太白', 'password': 123,'status': False}
ret = json.dumps(dic) # 转换成特殊的字符串供网络传输
print(ret,type(ret))
\\{"username": "\u592a\u767d", "password": 123, "status": false} <class 'str'>

ret_dict = json.load # 转换成源数据类型
print(ret_dict)
\\{'username': '太白', 'password': 123, 'status': False}

# 特殊的参数
dic = {'username': '太白', 'password': 123,'status': False}
ret = json.dumps(dic,ensure_ascii=False,sort_keys=True) #ensuir_ascii 解决中文 sork_key 排序
print(ret,type(ret))
\\{"password": 123, "status": false, "username": "太白"} <class 'str'>

# 文件的读取
import json
dic = {'username': '太白', 'password': 123,'status': False}
s_dict = json.dumps(dic)
with open('jsonlx.json',encoding='utf-8',mode='w') as f1:
     f1.write(s_dict)

with open('jsonlx.json',encoding='utf-8') as f2:
     content = f2.read()
     print(json.loads(content))

```

**多个数据如何储存到一个文件中**

```python
#错误演示:
import json
dic1 = {'username': '太白', 'password': 123,'status': False}
dic2 = {'username': 'alex', 'password': 123,'status': False}
dic3 = {'username': 'ly', 'password': 123,'status': False}
with open('jsonmore.json',encoding='utf-8',mode='a') as f1:
    # f1.write(json.dumps(dic1))
    # f1.write(json.dumps(dic2))
    # f1.write(json.dumps(dic3))
    f1.write(f'{json.dumps(dic1)}{json.dumps(dic2)}{json.dumps(dic3)}')

with open('jsonmore.json',encoding='utf-8') as f2:
    ret = json.loads(f2.read())
    print(ret)

          
# 正确做法:
import json
dic1 = {'username': '太白', 'password': 123,'status': False}
dic2 = {'username': 'alex', 'password': 123,'status': False}
dic3 = {'username': 'ly', 'password': 123,'status': False}
with open('jsonmore.json',encoding='utf-8',mode='a') as f1:
    f1.write(f'{json.dumps(dic1)}\n{json.dumps(dic2)}\n{json.dumps(dic3)}')

with open('jsonmore.json',encoding='utf-8') as f1:
    for line in f1:
        ret = json.loads(line)
        print(ret,type(ret))

```

#### 3. pickle序列化

pickle序列化, 只支持python

dumps,loads 只能是网络传输

```python
#dumps,loads  只能是网络传输

import picklimport picklxe
l1 = ['wusir', '太白', '小黑', 666]
ret = pickle.dumps(l1)
print(ret)

l2 = pickle.loads(ret)
print(l2,type(l2))

```

dump load 数据结构存取文件.

```python
import pickle
l1 = ['wusir', '太白', '小黑', 666]
with open('pickle练习.pickle',mode='wb') as f1:
    pickle.dump(l1,f1)

with open('pickle练习.pickle', mode='rb') as f1:
    ret = pickle.load(f1)
    print(ret,type(ret))

# 多个数据写入文件
l1 = ['wusir', '太白', '小黑1', 666]
l2 = ['wusir', '太白', '小黑2', 666]
l3 = ['wusir', '太白', '小黑3', 666]
with open('pickle练习1.pickle',mode='wb') as f1:
     pickle.dump(l1,f1)
     pickle.dump(l2,f1)
     pickle.dump(l3,f1)

with open('pickle练习1.pickle', mode='rb') as f1:
    ret1 = pickle.load(f1)
    ret2 = pickle.load(f1)
    ret3 = pickle.load(f1)
    print(ret1,ret2,ret3)

```

## 11.os模块

```python
import os

print(os.getcwd()) 获取当前文件的绝对路径
os.chdir('路径')  修改当前的工作路径  shell下cd  **
os.chdir 返回文件⤴️目录 os.chdir('.')当前  os.chdir('..')上一级(父级)

#与文件夹相关
os.makedirs('文件夹3/文件夹2/文件夹1') # 生成递归文件夹 ***
os.removedirs('文件夹3/文件夹2/文件夹1')
# 若目录为空，则删除，并递归到上一级目录，如若也为空，则删除，依此类推 ***

os.mkdir('文件夹')  # 生成单级目录；相当于shell中mkdir dirname ***
os.rmdir('文件夹') # 删除单级空目录，若目录不为空则无法删除，报错；相当于shell中rmdir dirname ***
print(os.listdir('文件夹'))#列出指定目录下的所有文件和目录，包括隐藏文件，并以列表方式打印 **

# 和文件相关
os.remove()  删除一个文件  ***
os.rename("oldname","newname")  重命名文件/目录  ***
print(os.stat('练习.py')) 获取文件/目录信息 **

"""
stat 结构:
st_mode: inode 保护模式
st_ino: inode 节点号。
st_dev: inode 驻留的设备。
st_nlink: inode 的链接数。
st_uid: 所有者的用户ID。
st_gid: 所有者的组ID。
st_size: 普通文件以字节为单位的大小；包含等待某些特殊文件的数据。
st_atime: 上次访问的时间。
st_mtime: 最后一次修改的时间。
st_ctime: 由操作系统报告的"ctime"。在某些系统上（如Unix）是最新的元数据更改的时间，在其它系统上（如Windows）是创建时间（详细信息参见平台的文档）。
"""

# 和操作系统差异相关
os.sep    输出操作系统特定的路径分隔符，win下为"\\",Linux下为"/" *
os.linesep    输出当前平台使用的行终止符，win下为"\t\n",Linux下为"\n" *
os.pathsep    输出用于分割文件路径的字符串 win下为;,Linux下为: *
os.name    输出字符串指示当前使用平台。win->'nt'; Linux->'posix' *
#和执行系统命令相关
os.system("bash command")  运行shell命令，直接显示  **
os.popen("bash command).read()  运行shell命令，获取执行结果  **
os.environ  获取系统环境变量  **

#path系列，和路径相关
print(os.path.abspath('练习.py')) #返回path规范化的绝对路径  ***
os.path.split(path) #将path分割成目录和文件名二元组返回 ***
os.path.dirname(path) #返回path的目录。其实就是os.path.split(path)的第一个元素  **
os.path.basename(path) 
#返回path最后的文件名。如何path以／或\结尾，那么就会返回空值，即os.path.split(path)的第二个元素。 **
         
os.path.exists(path)  # 如果path存在，返回True；如果path不存在，返回False  ***
os.path.isabs(path)  # 如果path是绝对路径，返回True  **
os.path.isfile(path)  # 如果path是一个存在的文件，返回True。否则返回False  ***
os.path.isdir(path) # 如果path是一个存在的目录，则返回True。否则返回False  ***
os.path.join(path1[, path2[, ...]])  #将多个路径组合后返回，第一个绝对路径之前的参数将被忽略 ***
  $路径的拼接:
# path = r'D:\s23\day17\db\lydata'
# path = par_dir + '\db' +'\lydata'
# path = os.path.join(par_dir,'db','lydata')
os.path.getatime(path) # 返回path所指向的文件或者目录的最后访问时间  **
os.path.getmtime(path)  # 返回path所指向的文件或者目录的最后修改时间  **
os.path.getsize(path) # 返回path的大小 ***

```

## 12. sys模块

```python
sys.argv           命令行参数List，第一个元素是程序本身路径
sys.exit(n)        退出程序，正常退出时exit(0),错误退出sys.exit(1)
sys.version        获取Python解释程序的版本信息
sys.path           返回模块的搜索路径，初始化时使用PYTHONPATH环境变量的值  ***
sys.platform       返回操作系统平台名称

```

## 13. hashlib模块

叫法 : 摘要算法 , 加密算法 , 哈希算法 , 散列算法

作用 : 加密和校验

工作原理 : 通过函数，把任意长度的数据按一定规则转换为一个固定长度的数据串通常用16进制的字符串表示）。

hashlib的特征及使用要点 :

- bytes类型数据 ---> 通过hashlib算法 ---> 固定长度的字符串
- 不同的bytes类型数据转化成的结果一定不同。
- 相同的bytes类型数据转化成的结果一定相同。
- 此转化过程不可逆。

### 1. md5 - 密码加密

```python
import hashlib  # 引入模块
ret = hashlib.md5() # 创建一个用来装数据的容器
ret.update('123'.encode('utf-8')) # 把需要加密的数据放到容器
s = ret.hexdigest() # 封装容器
print(s)

#撞库 : 一些简单的密码如1111, 1234 6666 8888 等,
ret = hashlib.md5()
ret.update('123456*@qwe'.encode('utf-8'))
s = ret.hexdigest()
print(s,type(s))

# 加固定盐
ret = hashlib.md5('xxx教育'.encode('utf-8'))
ret.update('123456'.encode('utf-8'))
s = ret.hexdigest()
print(s,type(s))

# 加动态的盐
username = input('输入用户名:').strip()
password = input('输入密码').strip()
ret = hashlib.md5(username[::2].encode('utf-8'))
ret.update(password.encode('utf-8'))
s = ret.hexdigest()
print(s)

# sha系列: 安全系数高,耗时高.
# 加盐,加动态盐
ret = hashlib.sha512()
ret.update('123456fdklsajflsdfjsdlkafjafkl'.encode('utf-8'))
s = ret.hexdigest()
print(s,type(s))

```

### 2. 文件的一致性校验

```python
# low版
import hashlib
ret = hashlib.md5()
with open('MD5文件校验',mode='rb') as f1:
    content = f1.read() # 占内存,若校验的文件过大,系统内存会溢出
    ret.update(content)
print(ret.hexdigest())

# 分步update
s1 = '老男孩教育 最好的python 讲师 是 太白'
# # 1
ret = hashlib.md5()
ret.update(s1.encode('utf-8'))
print(ret.hexdigest()) #90c56d265a363292ec70c7074798c913
# # 2
ret = hashlib.md5()
ret.update('老男孩教育'.encode('utf-8'))
ret.update(' 最好的python'.encode('utf-8'))
ret.update(' 讲师 是'.encode('utf-8'))
ret.update(' 太白'.encode('utf-8'))
print(ret.hexdigest())  # 90c56d265a363292ec70c7074798c913



# 高大上版
import hashlib
def md5_file(path):
    ret = hashlib.md5()
    with open(path,mode='rb') as f1:
        while 1:
            content = f1.read(1024) # 每次读取1024个字符,节省内存
            if content:
                ret.update(content)
            else:
                return ret.hexdigest()

print(md5_file(r'D:\s23\day17\python-3.7.4rc1-embed-win32.zip'))

```

## 14.规范化开发

**目录结构**

🔽📂项目  - 项目的总文件夹 

​		🔽📂bin 

​				📃starts.py  - 程序的启动 (为了防止误输入和其他等 在starts.py中加入`if _name_ == '_main_': ` 后面										加上调用程序开始执行的函数)

​									`import sys`

​									`	import os`

​									`BASE_PATH = os.path.dirname(os.path.dirname(__file__))`

​									`sys.path.append(BASE_PATH)`

​									`from … import 模块`

​		🔽📂conf   ( config )

​				📃settings.py  - 存放一些配置文件 ( 静态变量 - 轻易不改变的变量 )

​		🔽📂core - 

​				📃src.py  - 放主逻辑

​		🔽📂db - 

​				📃register.py  - 数据库文件,注册表,用户信息,访问记录等

​		🔽📂lib - 

​				📃common.py  - 公共组件部分,装饰器等

​		🔽📂log

​				📃access.py

​		📃README  - 描述项目的信息

## 15. time模块

### 1. 格式化时间

```python
imoprt time #导入时间模块
time.time() # 时间戳
# 时间字符串
time.strftime("%Y-%m-%d %X") # 需要打印  Y 大写表示年份写全,如2019  小写则为19
\\2019-06-28 15:43:32

time.strftime("%Y-%m-%d %H-%M-%S") # 需要打印
\\2019-06-28 15-44-14

print(time.strftime("%Y{}%m{}%d{} %H:%M:%S").format('年','月','日'))
\\2019年06月28日 15:45:43

```

### 2. 时间戳与结构化时间的相互转换

```python
时间戳 ---→ 结构化时间
import time
t1= time.strftime('%Y/%m/%d %H:%M:%S') # 格式化时间 \\t1= 2019/06/28 15:52:08
t2= time.strptime(t1,'%Y/%m/%d %H:%M:%S') # 结构化时间
print:
time.struct_time(tm_year=2019, tm_mon=6, tm_mday=28, tm_hour=15, tm_min=56, tm_sec=59, tm_wday=4, tm_yday=179, tm_isdst=-1)

结构化时间 -- → 时间戳
t3 =time.mktime(t2) # \\1561708758.0  只保留一位小数

结构化时间 --→ 格式化时间
t4 = time.strftime('%Y/%m/%d %H:%M:%S',t2) #\\2019/06/28 16:03:20

```

## 16. datetime模块

```python
import datetime
now_time = datetime.datetime.now()  # 现在的时间
# 只能调整的字段：weeks days hours minutes seconds
print(datetime.datetime.now() + datetime.timedelta(weeks=3)) # 三周后
print(datetime.datetime.now() + datetime.timedelta(weeks=-3)) # 三周前
print(datetime.datetime.now() + datetime.timedelta(days=-3)) # 三天前
print(datetime.datetime.now() + datetime.timedelta(days=3)) # 三天后
print(datetime.datetime.now() + datetime.timedelta(hours=5)) # 5小时后
print(datetime.datetime.now() + datetime.timedelta(hours=-5)) # 5小时前
print(datetime.datetime.now() + datetime.timedelta(minutes=-15)) # 15分钟前
print(datetime.datetime.now() + datetime.timedelta(minutes=15)) # 15分钟后
print(datetime.datetime.now() + datetime.timedelta(seconds=-70)) # 70秒前
print(datetime.datetime.now() + datetime.timedelta(seconds=70)) # 70秒后

current_time = datetime.datetime.now()
# 可直接调整到指定的 年 月 日 时 分 秒 等

print(current_time.replace(year=1977))  # 直接调整到1977年
print(current_time.replace(month=1))  # 直接调整到1月份
print(current_time.replace(year=1989,month=4,day=25))  # 1989-04-25 18:49:05.898601

# 将时间戳转化成时间
print(datetime.date.fromtimestamp(1232132131))  # 2009-01-17

```

## 17. random 模块

### 1. random的使用

```python
>>> import random
#随机小数
>>> random.random()      # 大于0且小于1之间的小数
0.7664338663654585
>>> random.uniform(1,3) #大于1小于3的小数
1.6270147180533838
#恒富：发红包

#随机整数
>>> random.randint(1,5)  # 大于等于1且小于等于5之间的整数
>>> random.randrange(1,10,2) # 大于等于1且小于10之间的奇数


#随机选择一个返回
>>> random.choice([1,'23',[4,5]])  # #1或者23或者[4,5]
#随机选择多个返回，返回的个数为函数的第二个参数
>>> random.sample([1,'23',[4,5]],2) # #列表元素任意2个组合
[[4, 5], '23']


#打乱列表顺序
>>> item=[1,3,5,7,9]
>>> random.shuffle(item) # 打乱次序
>>> item
[5, 1, 3, 7, 9]
>>> random.shuffle(item)
>>> item
[5, 9, 7, 1, 3]

```

### 2. 生成随机验证码

```python
import random

def v_code():

    code = ''
    for i in range(5):
        num=random.randint(0,9)
        alf=chr(random.randint(65,90))
        add=random.choice([num,alf])
        code="".join([code,str(add)])

    return code

print(v_code())
生成随机验证码

```



## 18. 包的使用

**time模块 一个py文件,200个函数,功能特别多,分文件,分三个文件,time文件夹: time1 time2 time3py文件,这个time文件夹就叫做包.**

### 1. import

```python
# 第一类: 执行文件 通过 import 导入包以及包内的功能
# 创建一个aaa的包,自行创建一个__init__py文件
# 回忆 :创建一个tbjx模块发生的三件事:
'''
    1. 将该tbjx文件加载到内存.
    2. 创建一个以tbjx命名的名称空间.
    3. 通过tbjx. 的方式引用tbjx模块的所有的名字.
'''

# 创建一个包,也会发生三件事:
'''
    1. 将该aaa包内 __init__py文件加载到内存.
    2. 创建一个以aaa命名的名称空间.
    3. 通过aaa. 的方式引用__init__的所有的名字.
'''
import aaa
# print(aaa.x)
# aaa.f1()

# print(aaa.m1)
# print(aaa.m1.a)

# 我想要引用 aaa包的m1文件的a变量
# 错误示例1:
import aaa
# 1. aaa的 __init__ 里面 写import m1
# 2. print(aaa.m1.a)
# print(aaa.m1.a)

# 报错原因: No module named 'm1'
# 分析报错原因: 模块找不到 内存,内置,sys.path三个地方找不到.
# m1 不在内存,不在内置,sys.path 会主动加载执行文件(包的使用.py)的当前目录.

# 解决方式:
import aaa
# 1. 在执行文件写入 import aaa
# 2. aaa的 __init__ 里面 写 from aaa import m1
# 3. 然后在执行文件  aaa.m1.a
# print(aaa.m1.a)

# aaa.m1.func1()


import aaa
# 如何在当前文件中,引用 aaa包的bbb包.
# 1. 在执行文件写入 import aaa
# 2. aaa的 __init__ 里面 写 from aaa import bbb
# 3. 然后在执行文件  aaa.bbb
# print(aaa.bbb)


# 如何在当前文件中,引用 aaa包的bbb包 的 变量 name.
# 1. 在执行文件写入 import aaa
# 2. aaa的 __init__ 里面 写 from aaa import bbb
# 3. 然后在执行文件  aaa.bbb
# print(aaa.bbb)


import aaa
# print(aaa.bbb.name)

# 如何在当前文件中,引用 aaa包的bbb包 的 mb文件的函数func.

# 1. 在执行文件写入 import aaa
# 2. 在aaa包的__Init__ 写上 from aaa import bbb  (这样写 bbb包的__init__里面所有的名字都能引用)
# print(aaa.bbb.name)
# 3. 在bbb包的__Init__ 写上 from aaa.bbb import mb
# aaa.bbb.mb.func3()

# 首先 无论从哪里引用模块,import 或者 from  ... import ...
# 最开始的模块或者包名一定是内存,内置,sys.path中能找到的.(可参考bbb包中的 __init__)

# 直接import 为了让我们会使用 包里面的 __init__






# 第二类: 执行文件 通过 from ... import... 导入包以及包内的功能
```



### 2. from … import ...

```python
# from ... import ...
# 通过这种方式不用设置__init__文件
# from aaa import m1
# m1.func()

# from aaa.bbb.m2 import func1
# func1()
# from aaa.bbb import m2
# m2.func1()

# from a.b.c import d.e.f
# c的. 的前面一定是包
# import 的后面一定是名字,并且不能 再有点

# from aaa.bbb.m2.func1 import a  # 错误的
# from aaa.bbb import m2
# m2.func1()

import json

```



### 3. 相对导入和绝对导入

```python
# import nb
# nb.f1()
# nb.f2()

# 由于nb模块增加了很多很多功能,所以我们nb这个文件就要划整一个包,
# 无论对nb模块有任何操作,对于使用者来说不应该改变,极少的改变对其的调用.
#
# import sys
# sys.path.append(r'D:\s23\day19\相对导入绝对导入\dir')
#
# import nb
#
# nb.f1()
# nb.f2()
# nb.f3()
# nb.f4()
# nb.f5()
# nb.f6()

# 我将原包名改成了大写的NB
import sys
sys.path.append(r'D:\s23\day19\相对导入绝对导入\dir')
import NB as nb

nb.f1()
nb.f2()
nb.f3()
nb.f4()
nb.f5()
nb.f6()
nb.f7()
```



## 19. ogging日志

**工作日志分四个大类:**

1. 系统日志:记录服务器的一些重要信息:监控系统,cpu温度,网卡流量,重要的硬件的一些指标,运维人员经常使用的,运维人员,记录操作的一些指令.
2. 网站日志: 访问异常,卡顿,网站一些板块,受欢迎程度,访问量,点击率.等等,蜘蛛爬取次数等等.
3. 辅助开发日志: 开发人员在开发项目中,利用日志进行排错,排除一些避免不了的错误(记录),辅助开发.
4. 记录用户信息日志: 用户的消费习惯,新闻偏好,等等.(数据库解决)

**日志一般是开发者使用**

**日志的三个版本 :**

1. Low版(简易版)

   ```python
   # import logging
   # logging.basicConfig(
   #     level=logging.DEBUG,
   # )
   # # logging.debug('debug message')
   # # logging.info('info message')
   # # logging.warning('warning message')
   # # logging.error('error message')
   # # logging.critical('critical message')
   
   # 应用:
   # def func():
   #     print('in func')
   #     logging.debug('正常执行')
   # func()
   
   # try:
   #     i = input('请输入选项:')
   #     int(i)
   # except Exception as e:
   #     logging.error(e)
   # print(11)
   
   # low版的日志:缺点: 文件与屏幕输入只能选择一个.
   import logging
   logging.basicConfig(
       # level=logging.DEBUG,
       level=30,
       format='%(asctime)s %(filename)s[line:%(lineno)d] %(levelname)s %(message)s',
       filename=r'test.log',
   )
   # logging.debug('调试模式')  # 10
   # logging.info('正常模式')  # 20
   logging.warning('警告信息')  # 30
   # logging.error('错误信息')  # 40
   # logging.critical('严重错误信息')  # 50
   
   ```

   

2. 标配版(标准版)

   ```python
   # import logging
   #
   # # 创建一个logging对象
   # logger = logging.getLogger()
   #
   # # 创建一个文件对象
   # fh = logging.FileHandler('标配版.log', encoding='utf-8')
   #
   # # 创建一个屏幕对象
   # sh = logging.StreamHandler()
   #
   # # 配置显示格式
   # formatter1 = logging.Formatter('%(asctime)s %(filename)s[line:%(lineno)d] %(levelname)s %(message)s')
   # formatter2 = logging.Formatter('%(asctime)s %(message)s')
   # fh.setFormatter(formatter1)
   # sh.setFormatter(formatter2)
   #
   # logger.addHandler(fh)
   # logger.addHandler(sh)
   #
   # # 总开关
   # logger.setLevel(10)
   #
   # fh.setLevel(10)
   # sh.setLevel(40)
   #
   # logging.debug('调试模式')  # 10
   # logging.info('正常模式')  # 20
   # logging.warning('警告信息')  # 30
   # logging.error('错误信息')  # 40
   # logging.critical('严重错误信息')  # 50
   ```

   

3. 旗舰版(项目中使用的,Django项目) ***

   1. 自定制(通过字典的方式)日志
   2. 轮转日志的功能.

   ```python
   """
   logging配置
   """
   
   
   import logging.config
   
   # 定义三种日志输出格式 开始
   
   standard_format = '[%(asctime)s][%(threadName)s:%(thread)d][task_id:%(name)s][%(filename)s:%(lineno)d]' \
                     '[%(levelname)s][%(message)s]' #其中name为getlogger指定的名字
   
   simple_format = '[%(levelname)s][%(asctime)s][%(filename)s:%(lineno)d]%(message)s'
   
   id_simple_format = '[%(levelname)s][%(asctime)s] %(message)s'
   
   # 定义日志输出格式 结束
   logfile_name = 'login.log'  # log文件名
   logfile_path_staff = r'D:\s23\day19\日志模块\旗舰版日志文件夹\staff.log'
   logfile_path_boss = r'D:\s23\day19\日志模块\旗舰版日志文件夹\boss.log'
   
   # log配置字典
   # LOGGING_DIC第一层的所有的键不能改变
   
   LOGGING_DIC = {
       'version': 1,  # 版本号
       'disable_existing_loggers': False,  #　固定写法
       'formatters': {
           'standard': {
               'format': standard_format
           },
           'simple': {
               'format': simple_format
           },
           'id_simple':{
               'format': id_simple_format
           }
       },
       'filters': {},
       'handlers': {
           #打印到终端的日志
           'sh': {
               'level': 'DEBUG',
               'class': 'logging.StreamHandler',  # 打印到屏幕
               'formatter': 'id_simple'
           },
           #打印到文件的日志,收集info及以上的日志
           'fh': {
               'level': 'DEBUG',
               'class': 'logging.handlers.RotatingFileHandler',  # 保存到文件
               'formatter': 'standard',
               'filename': logfile_path_staff,  # 日志文件
               'maxBytes': 5000,  # 日志大小 5M
               'backupCount': 5,
               'encoding': 'utf-8',  # 日志文件的编码，再也不用担心中文log乱码了
           },
           'boss':
               {
                   'level': 'DEBUG',
                   'class': 'logging.handlers.RotatingFileHandler',  # 保存到文件
                   'formatter': 'id_simple',
                   'filename': logfile_path_boss,  # 日志文件
                   'maxBytes': 5000,  # 日志大小 5M
                   'backupCount': 5,
                   'encoding': 'utf-8',  # 日志文件的编码，再也不用担心中文log乱码了
               },
       },
       'loggers': {
           #logging.getLogger(__name__)拿到的logger配置
           '': {
               'handlers': ['sh', 'fh', 'boss'],  # 这里把上面定义的两个handler都加上，即log数据既写入文件又打印到屏幕
               'level': 'DEBUG',
               'propagate': True,  # 向上（更高level的logger）传递
           },
       },
   }
   
   
   def md_logger():
       logging.config.dictConfig(LOGGING_DIC)  # 导入上面定义的logging配置
       logger = logging.getLogger()  # 生成一个log实例
       return logger
       # logger.debug('It works!')  # 记录该文件的运行状态
   
   dic = {
       'username': '小黑'
   }
   
   
   def login():
       # print('登陆成功')
       md_logger().info(f"{dic['username']}登陆成功")
   #
   # def aricle():
   #     print('欢迎访问文章页面')
   
   
   login()
   # aricle()
   ```

   源码

   ```python
   """
   logging配置
   """
   
   import os
   import logging.config
   
   # 定义三种日志输出格式 开始
   
   standard_format = '[%(asctime)s][%(threadName)s:%(thread)d][task_id:%(name)s][%(filename)s:%(lineno)d]' \
                     '[%(levelname)s][%(message)s]' #其中name为getlogger指定的名字
   
   simple_format = '[%(levelname)s][%(asctime)s][%(filename)s:%(lineno)d]%(message)s'
   
   id_simple_format = '[%(levelname)s][%(asctime)s] %(message)s'
   
   # 定义日志输出格式 结束
   
   logfile_dir = os.path.dirname(os.path.abspath(__file__))  # log文件的目录
   
   logfile_name = 'all2.log'  # log文件名
   
   # 如果不存在定义的日志目录就创建一个
   if not os.path.isdir(logfile_dir):
       os.mkdir(logfile_dir)
   
   # log文件的全路径
   logfile_path = os.path.join(logfile_dir, logfile_name)
   
   # log配置字典
   LOGGING_DIC = {
       'version': 1,
       'disable_existing_loggers': False,
       'formatters': {
           'standard': {
               'format': standard_format
           },
           'simple': {
               'format': simple_format
           },
       },
       'filters': {},
       'handlers': {
           #打印到终端的日志
           'console': {
               'level': 'DEBUG',
               'class': 'logging.StreamHandler',  # 打印到屏幕
               'formatter': 'simple'
           },
           #打印到文件的日志,收集info及以上的日志
           'default': {
               'level': 'DEBUG',
               'class': 'logging.handlers.RotatingFileHandler',  # 保存到文件
               'formatter': 'standard',
               'filename': logfile_path,  # 日志文件
               'maxBytes': 1024*1024*5,  # 日志大小 5M
               'backupCount': 5,
               'encoding': 'utf-8',  # 日志文件的编码，再也不用担心中文log乱码了
           },
       },
       'loggers': {
           #logging.getLogger(__name__)拿到的logger配置
           '': {
               'handlers': ['default', 'console'],  # 这里把上面定义的两个handler都加上，即log数据既写入文件又打印到屏幕
               'level': 'DEBUG',
               'propagate': True,  # 向上（更高level的logger）传递
           },
       },
   }
   
   
   def load_my_logging_cfg():
       logging.config.dictConfig(LOGGING_DIC)  # 导入上面定义的logging配置
       logger = logging.getLogger(__name__)  # 生成一个log实例
       logger.info('It works!')  # 记录该文件的运行状态
   
   if __name__ == '__main__':
       load_my_logging_cfg()
   
   logger配置文件
   ```

   

## 20. collections模块

在内置数据类型（dict、list、set、tuple）的基础上，collections模块还提供了几个额外的数据类型：Counter、deque、defaultdict、namedtuple和OrderedDict等。

1.namedtuple: 生成可以使用名字来访问元素内容的tuple

2.deque: 双端队列，可以快速的从另外一侧追加和推出对象

3.Counter: 计数器，主要用来计数

4.OrderedDict: 有序字典

5.defaultdict: 带有默认值的字典

### 1. namedtuple (坐标的点)

```python
from collections import namedtuple
Point = namedtuple('Point',['x', 'y'])
print(type(Point)) # <class 'type'>

p = Point(1, 2)
print(type(p))# <class '__main__.Point'>
print(p)  # Point(x=1, y=2)

print(p[0]) # 1
print(p[1]) # 2

print(p.x) # 1
print(p.y) # 2
```

### 2. deque

使用list存储数据时，按索引访问元素很快，但是插入和删除元素就很慢了，因为list是线性存储，数据量大的时候，插入和删除效率很低。

deque是为了高效实现插入和删除操作的双向列表，适合用于队列和栈：

```python
#deque: 类似于列表的一种容器型数据,插入元素删除元素效率高.
from collections import deque
q = deque(['a', 1, 'c', 'd']) 
print(q) # deque(['a', 1, 'c', 'd'])

q.append('e') 
print(q) # deque(['a', 1, 'c', 'd', 'e'])

q.appendleft('ly') # deque(['ly', 'a', 1, 'c', 'd', 'e'])

q.pop() # deque(['ly', 'a', 1, 'c', 'd'])
q.popleft() # deque(['a', 1, 'c', 'd'])
# deque 除了可以在两端增删外,其他的用法和list一样
```

### 3. QrderedDict

使用dict时，Key是无序的。在对dict做迭代时，我们无法确定Key的顺序。

如果要保持Key的顺序，可以用`OrderedDict`：

```python
from collections import OrderedDict

od = OrderedDict([('a', 1), ('b', 2), ('c', 3)])
print(od) # OrderedDict([('a', 1), ('b', 2), ('c', 3)])
print(od['a']) # 1
```

### 4. defaultdict 默认字典

```
有如下值集合 [``11``,``22``,``33``,``44``,``55``,``66``,``77``,``88``,``99``,``90.``..]，将所有大于 ``66` `的值保存至字典的第一个key中，将小于 ``66` `的值保存至第二个key的值中。
即： {``'k1'``: 大于``66` `, ``'k2'``: 小于``66``}
```

```python
#原字典方法
l1 = [11, 22, 33, 44, 55, 77, 88, 99]
dic = {}
for i in l1:
    if i < 66:
        if 'key1' not in dic:
            dic['key1'] = []
        dic['key1'].append(i)
    else:
        if 'key2' not in dic:
            dic['key2'] = []
        dic['key2'].append(i)
print(dic)
```

```python
# defaultdict字典解决方法
from collections import defaultdict
l1 = [11, 22, 33, 44, 55, 77, 88, 99]
dic = defaultdict(list)
for i in l1:
    if i < 66:
        dic['key1'].append(i)
    else:
        dic['key2'].append(i)
print(dic)
```

```python
from collections import defaultdict
dic = defaultdict(list)  # 需要一个可回调的
dic['1'] = 222
dic['2']
dic['3']
print(dic)
# defaultdict(<class 'list'>, {'1': 222, '2': [], '3': []})

from collections import defaultdict
dic = defaultdict(str)  
dic['1'] = 222
dic['2']
dic['3']
print(dic)
# defaultdict(<class 'str'>, {'1': 222, '2': '', '3': ''})

dic = dict.fromkeys('123',[])
print(dic)
# {'1': [], '2': [], '3': []}
```

### 5. Counter 计数器

```python
from collections import Counter
c = Counter('flkjdasffdfakjsfdsaklfdsalf')  # 计数器
print(c)
print(c['f'])
# 结果：Counter({'f': 7, 'd': 4, 'a': 4, 's': 4, 'l': 3, 'k': 3, 'j': 2})
		7
```

## 21. re模块

### 1. 什么是正则

**正则就是用一些具有特殊含义的符号组合到一起（称为正则表达式）来描述字符或者字符串的方法。或者说：正则就是用来描述一类事物的规则。（在Python中）它内嵌在Python中，并通过 re 模块实现。正则表达式模式被编译成一系列的字节码，然后由用 C 编写的匹配引擎执行。**

| `元字符` | `匹配内容`                                                   |
| -------- | ------------------------------------------------------------ |
| \w       | 匹配字母（包含中文）或数字或下划线                           |
| \W       | 匹配非字母（包含中文）或数字或下划线                         |
| \s       | 匹配任意的空白符                                             |
| \S       | 匹配任意非空白符                                             |
| \d       | 匹配数字                                                     |
| \D       | p匹配非数字                                                  |
| \A       | 从字符串开头匹配                                             |
| \z       | 匹配字符串的结束，如果是换行，只匹配到换行前的结果           |
| \n       | 匹配一个换行符                                               |
| \t       | 匹配一个制表符                                               |
| ^        | 匹配字符串的开始                                             |
| $        | 匹配字符串的结尾                                             |
| .        | 匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。 |
| [...]    | 匹配字符组中的字符                                           |
| [^...]   | 匹配除了字符组中的字符的所有字符                             |
| *        | 匹配0个或者多个左边的字符。                                  |
| +        | 匹配一个或者多个左边的字符。                                 |
| ？       | 匹配0个或者1个左边的字符，非贪婪方式。                       |
| {n}      | 精准匹配n个前面的表达式。                                    |
| {n,m}    | 匹配n到m次由前面的正则表达式定义的片段，贪婪方式             |
| a\|b     | 匹配a或者b。                                                 |
| ()       | 匹配括号内的表达式，也表示一个组                             |

### 1. findall（）

```python
import re

# re.findall()
# 正则表达式: 从一大堆字符串中,找出你想要的字符串.
# 在于对你想要得这个字符串进行一个精确地描述.

# s1 = 'fdsa太白金星'
# print(s1.find('白'))


# 单个字符匹配
# \W与\w
# \w 数字字母下划线中文
# \W 非数字字母下划线中文
# print(re.findall('\w', '太白jx 12*() _'))
# print(re.findall('\W', '太白jx 12*() _'))

# \s  匹配的 空格 \t \n
# \S  匹配的 非空格 \t \n
# print(re.findall('\s','太白barry*(_ \t \n'))
# print(re.findall('\S','太白barry*(_ \t \n'))


# \d 匹配所有的数字
# \D 非匹配所有的数字
# print(re.findall('\d\d','1234567890 alex *（_'))
# print(re.findall('\D','1234567890 alex *（_'))


# \A ^从开头开始匹配
# print(re.findall('\Ahello','hello hello 太白 hell'))
# print(re.findall('^hello','hello hello 太白 hell'))



# \Z,从结尾开始匹配
# \z,有一点问题
# $从结尾开始匹配
# print(re.findall('fjkdsla太白金星\Z','fjkdsla太白金星'))
# print(re.findall('金星$','fjkdsla太白金星'))


# \n \t
# print(re.findall('\n','fdsak\n fkjdlas\n \t'))
# print(re.findall('\t','fdsak\n fkjdlas\n \t'))



# 元字符匹配
# . ? * + {m,n} .* .*?
#  . 匹配任意一个字符
# 如果匹配成功光标则移到匹配成功的最后的字符
# 如果匹配未成功光标则向下移动一位再次匹配
# print(re.findall('a.b','aaabbb'))


# ? 匹配0个或者1个由左边字符定义的片段。
# print(re.findall('a?b', 'ab aab'))
# print(re.findall('a?b', 'sb ab aabb'))


#* 匹配0个或者多个左边字符表达式。 满足贪婪匹配
# print(re.findall('a*b','aaab ab b'))
# # print(re.findall('a*b','aasab ab b'))


# + 匹配1个或者多个左边字符表达式。 满足贪婪匹配
# print(re.findall('a+b','aaab ab b'))

# {m,n}  匹配m个至n(n能取到)个左边字符表达式。 满足贪婪匹配
# print(re.findall('a{1,5}b', 'ab aab aaab aaaab aaaaaab aaaaabb'))



# .* 贪婪匹配 从头到尾.
# print(re.findall('a.*b','aab abbliye aaab abbb aa#b'))
# print(re.findall('a.*b','asb abbliyeaaab \nabbb aa#y',re.DOTALL))  # a...................b



# .*? 此时的?不是对左边的字符进行0次或者1次的匹配,
# 而只是针对.*这种贪婪匹配的模式进行一种限定:告知他要遵从非贪婪匹配 推荐使用!
# 0个或者多个
# print(re.findall('a.*?b','ab a#bbbbbb aaab'))
# print(re.findall('a.*b','a#bbbbbb'))
# print(re.findall('a.*?b','a#bbbbbb'))

#[]
# print(re.findall('a[abc]b', 'aab abb acb adb afb a_b'))
# print(re.findall('a[abc][bd]b', 'aabb aaabc abd acdbb'))


# print(re.findall('a[0-9]b', 'a1b a3b aeb a*b arb a_b'))
# print(re.findall('a[a-z]b', 'a1b a3b aeb a*b arb a_b'))
# print(re.findall('a[A-Z]b', 'aAb a3b aEb a*b aRb a_b'))
# print(re.findall('a[a-zA-Z]b', 'aab a3b aAb a*b aTb a_b'))

# 当你想匹配 - 时,要把它放在[]里面的最前面或者最后面
# print(re.findall('a[-*$]b', 'a-b a$b a)b a*b '))

# ^ 在中括号里面最前面代表取反
# print(re.findall('a[0-9]b', 'a1b a$b a5b a*b '))
# print(re.findall('a[*^)]b', 'a^b a$b a5b a*b '))


# 'alex_sb wusir_sb ritian_sb 太白_nb yuanbao_sb'
s = 'alex_sb wusir_sb ritian_sb 太白_nb yuanbao_sb dsb_sb'
# print(re.findall('\w+_sb',s))
# # 'alex_sb wusir_sb ritian_sb 太白_nb yuanbao_sb'

# ()
# print(re.findall('(\w+)_sb',s))



# |
# print(re.findall('alex|太白|wusir', 'alex太白wusiraleeeex太太白odlb'))


# # () 分组里面加了?: 将全部的内容给我返回回来,而不是将组内的内容返回
# print(re.findall('companies|company',
#                  'Too many companies have gone bankrupt, and the next one is my company'))  # ['ies', 'y']



# printy companies have gone bankrupt, and the next one is my company'))(re.findall('compan(?:ies|y)',

# #                  'Too man

```

### 2. search match

```python
# search match
import re
# 找到第一个符合条件的字符串就返回,返回一个对象,通过对象.group()

# ret = re.search('sb|alex', 'alex sb sb barry 日天')
# ret = re.search('alex', 'fdsjkfd fjdsklalex gfdlgjfdlgjfggfjlgjfkdl')
# # # print(ret)
# # # print(ret.group())

#
# # 从字符串开头匹配,如果以符合条件的字符串开头则返回,否则返回None
# ret = re.match('alex', 'alexfdskfd fjdsklalex gfdlgjfdlgjfggfjlgjfkdl')
# print(ret)
# print(ret.group())


# split
# s1 = 'alex;wusir,太白 吴超~宝元'
# import re
# print(re.split('[;, ~]',s1))

import re
# print(re.sub('barry', '太白', 'barry是最好的讲师，barry就是一个普通老师，请不要将barry当男神对待。'))



# obj = re.compile('\d{2}')
# # print(obj.search('fdsa12fds435454').group())
# print(obj.findall('fjdskalf2134fkjsd3245fdjsl545'))



# finditer
ret = re.finditer('\d','54fjdkls4535lsdfj6776')
# print(ret)
# print(next(ret))
# print(next(ret).group())
# print(next(ret).group())

# for i in ret:
#     print(i.group())
# print(list(ret))
s1 = '''

时间就是f4321995-04-27,2005-04-27
1999-04-27 老男孩教育创始人
老男孩老师 alex 1980-04-27:1980-04-27
2018-12-08

'''

# print(re.findall('\d{4}-\d{2}-\d{2}',s1))

# 匹配一个qq账号 10000开始 第一个元素规定就是非零数字,后面的是随意的数字长度大于5位.

s2 = '56546326546757'

print(re.findall('[1-9][0-9]{4,}',s2))

```



# 面向对象

## 1. 面向过程编程vs函数式编程vs面向对象编程

```python
s1 = 'fdskljfsda'
count = 1
for i in s1:
	count += 1
	
l1 = [1,2,3,4,5]
count = 1
for i in l1:
	count += 1
	

def my_len(a):
    count = 0
    for i in a:
        count += 1
    return count
lst = [1]
print(my_len(lst))
提高代码的可读性,减少了代码的重复性....
上面统称为面向过程式编程.


面向过程式编程:
好处: 出色的完成你之前布置的所有的需求.
坏处: 但凡更改或者增加一条需求,可能整个项目都随之改变.
```



## 2. 面向对象的结构

```python
class Bankcard:
    def save(self):
        pass
    def transfer(self):
        pass
    def check_bill(self):
        pass


class Shop:
    def shopping(self):
        pass
    def shopping2(self):
        pass

# 1.类 -  相似功能的集合体
# 	   - 类是一个公共模板,对象是从这个公共的模板产出的.
# 2.类 -  站在上帝的角度思考问题
# 3.类 -  具有相似功能和特性的一类事物
# 对象 -  类的具体体现

class Student:
    daily = '学习'
    examination = '考试'
    def work(self):
        print('每天要上课')
    def homework(self):
        print('家庭作业')
# 类名要具有描述性,类名首字母要大写,类名不宜用"_"   \ 如上面的 Student 
```



## 3. 从类名的角度使用类

```python
class Student:
    """
    此类是构建学生类
    """
    daily = '学习'
    examination = '考试'

    def work(self):
        print('每天要上课')

    def homework(self):
        print('家庭作业')

# 类名的角度调用类中的属性.
#1. 查看类中的所有的内容.  类名.__dict__只用于获取类中的全部.
print(Student.__dict__)
"""
{'__module__': '__main__', '__doc__': '\n    此类是构建学生类\n    ', 'daily': '学习', 'examination': '考试', 'work': <function Student.work at 0x000001E80FBCDA60>, 'homework': <function Student.homework at 0x000001E80FBCDAE8>, '__dict__': <attribute '__dict__' of 'Student' objects>, '__weakref__': <attribute '__weakref__' of 'Student' objects>}
"""
print(Student.__dict__['daily']) # 学习


2. 万能的点
print(Student.daily)  # 查   - 结果: 学习

Student.cloth = '校服'  # 增
print(Student.__dict__)

Student.examination = '不考试!'  # 改
print(Student.examination)

del Student.daily  # 删
print(Student.__dict__)

# 一般类中的属性都是通过类名.的方式去操控的.


类名的角度调用类中的方法.(一般类中的方法(除去类方法,静态方法外)不通过类名调用)
Student.work(5565)  # 工作中不用类名调用
```

## 4.  从对象的角度分析  "类"

```python
class Student:
    """
    这是构建学生类
    """
    daily = '学习'
    exam = '考试'
    def __init__(self):
        self.name = '二哈'
        self.sex = 'man'
    def hobby(self):
        print("玩皮球")

obj = Student()  # 这个过程叫做实例化过程,实例化一个对象 , obj就是一个对象,一个实例
print(obj) # <__main__.Student object at 0x000001FD14E1ADD8>
obj1 = Student()
print(obj1) # <__main__.Student object at 0x000002165A53AE80>

#实例化一个对象发生的三件事:
1. 在内存中创建一个对象空间
2. 自动执行__init__方法,并且将对象空间传给self参数
3. 执行__init__方法里面的代码,给对象空间封装其属性


# 从对象角度研究类 :

#对象操作对象里面的属性
obj = Student() # 实例化一个对象
print(obj)
# 查看对象的全部属性
print(obj.__dict__) # {'name': '二哈', 'sex': 'man'}

# 对象可以操作对象空间的属性 -万能的点- (增删改查)
obj.age = "2"  # 增

del obj.sex  # 删

obj.name = "三哈"  # 改

print(obj.name) # 查

print(obj.__dict__) # 查全部

*******************************************************************
# 对象查看类中的属性(传参数)
class Student:
    """
    这是构建学生类
    """
    daily = '学习'
    exam = '考试'
    def __init__(self,a,b):
        self.name = '二哈'
        self.sex = 'man'
        self.job = a
        self.hobby = b
    def work(self,c):
        self.other = c
        print("玩皮球")
obj = Student('IT','打篮球')
print(obj.__dict__) # {'name': '二哈', 'sex': 'man', 'job': 'IT', 'hobby': '打篮球'}
obj.daily = "唱歌"
print(obj.daily) # 唱歌
print(obj.__dict__) # {'name': '二哈', 'sex': 'man', 'job': 'IT', 'hobby': '打篮球', 'daily': '唱歌'}

# 对象调用类中的方法
obj.work('嘿黝黑')
print(obj.__dict__)
#
玩皮球
{'name': '二哈', 'sex': 'man', 'job': 'IT', 'hobby': '打篮球', 'other': '嘿黝黑'}

self 就是类中方法的第一个位置参数
如果通过对象执行此方法,解释器就会自动的将此对象空间当做实参传给self
约定俗成:类中的方法第一个参数一般都设置成self
```



## 5. 从空间角度研究类

### 1. 对象操作属性

### 2. 类名操作属性

### 3. 类对象指针

### 4. 对象取值顺序

### 5. 类名取值顺序

```python
对象如何查看对象空间属性 对象.__dict__

对象如何操作对象空间属性: 对象.属性名

对象查看类中的属性 : 对象.country

对象可以调用类中的方法: obj.func()
```



```python
class A:
    address = "扑朔迷离的世界"
    def __init__(self,name):
        self.name = name
    def func(self,sex):
        self.skins = '吉利服'
        self.sex = sex
obj = A('嘻嘻哈哈')
# 在类外面可以给对象封装属性
obj.age = 18
print(obj.__dict__)  \\ {'name': '嘻嘻哈哈', 'age': 18}

# 类内部封装属性
obj.func('man')
print(obj.__dict__)  \\  {'name': '嘻嘻哈哈', 'age': 18, 'sex': 'man'}

A.height = 178 # 给A加一个身高属性
print(A.__dict__) # 加height成功
obj1 = A("帅哥") # 实例化一个obj1对象
print(obj1.__dict__) # {'name': '帅哥'} 吃对象只有一个属性
print(obj1.height) # 178  但是.height确实存在这个属性
# 总结,类的静态属性需要对象先调用,才会成为对象的属性,它不会像init自动封装
```

```python
class Person:
    mind = "有思想"
    language ="会使用语言"
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def work(self):
        print('人类一般都需要工作')

p1 = Person('阿坤',18)
print(p1.__dict__) # {'name': '阿坤', 'age': 18}
p1.sex = "男"
del p1.name
print(p1.__dict__)  # {{'age': 18, 'sex': '男'}
del p1.mind # 报错, 属性错误


print(p1.mind) # 有思想
p1.mind ="没有思想"
print(p1.mind) # 没有思想
p1.job = "IT"
print(p1.__dict__) # {'age': 18, 'sex': '男', 'mind': '没有思想', 'job': 'IT'}
print(Person.mind) # 有思想
# 当改变了__init__上面的属性后,被引用的属性就会载入到p1__dict__列表里,但是类中的原属性不会改变
```

```python
# 对象如果查询一个属性: 对象空间  ----> 类空间 ----> 父类空间  --->
# 类查询一个属性: 类空间  ----> 父类空间  ---->
# 单向不可逆
# 对象与对象之间原则上互相独立(除去组合这种特殊的关系之外).
```



## 6.  类与类的关系

### 1. 依赖顺序

将一个类名或者类的对象传给另一个类的方法中

```python
#依赖关系(主从关系)

# 大象进冰箱
class Elephant:
    def __init__(self, name):
        self.name = name
        
    def open(self, ref1):
        # print(ref1)
        print(f'{self.name}默念三声: 芝麻开门')
        ref1.open_door()
        
    def close(self):
        print('大象默念三声:芝麻关门')
        
class Refrigerator:
    def __init__(self, name):
        self.name = name
        
    def open_door(self):
        print(f'{self.name}冰箱门被打开了....')

    def close_door(self):
        print('冰箱门被关上了....')

ele = Elephant('琪琪')
ele1 = Elephant('安安')
ref = Refrigerator('美菱')
ele.open(ref)
ele1.open(ref)
# 结果 :
琪琪默念三声: 芝麻开门
美菱冰箱门被打开了....
安安默念三声: 芝麻开门
美菱冰箱门被打开了....
```



### 2. 组合关系(关联组合聚合)

```python
class Boy:
    def __init__(self,name):
        self.name = name
    def meet(self,girl_friend = None):
        self.girl_friend = girl_friend  # girl_frieng = flower 
    def have_dinner(self):
        if self.girl_friend: # 如果有女友
            print(f'{self.name}请年龄为:{self.girl_friend.age},姓名为{self.girl_friend.name}一起吃六块钱的麻辣烫')
            self.girl_friend.shopping(self)  # self.girl_frieng = flower
        else:
            print('单身狗,吃什么吃')

class Girl:
    def __init__(self, name, age):
            self.name = name
            self.age = age
    def shopping(self,boy_friend):
        print(f'{boy_friend.name},{self.name}一起去购物!')

wu = Boy("吴超") # 实例化一个对象
flower = Girl('如花',18)
wu.meet(flower)
wu.have_dinner()
# 结果 :
吴超请年龄为:18,姓名为如花一起吃六块钱的麻辣烫
吴超,如花一起去购物!
```

```python
class GameRole:

    def __init__(self, name, ad, hp):

        self.name = name
        self.ad = ad
        self.hp = hp

    def attack(self,p1):
        # print(self.name)
        # print(p1.name)
        p1.hp = p1.hp - self.ad
        print(f'{self.name}攻击{p1.name},{p1.name}掉了{self.ad}血,还剩{p1.hp}血')

    def equit_weapon(self,wea):
        # print(wea)
        self.weapon = wea  # 组合: 给gailun这个对象封装了一个为weapon属性,属性值为wea == great_sword对象

class Weapon:

    def __init__(self, name, ad):
        self.name = name
        self.ad = ad

    def weapon_attack(self, p1, p2):
        # print(self)
        p2.hp = p2.hp - self.ad
        print(f'{p1.name}利用{self.name}给了{p2.name}一下,{p2.name}还剩{p2.hp}血')

# gailun = GameRole('草丛伦', 10, 100)
# jianhao = GameRole('风男', 20, 80)
# gailun.attack(jianhao)
# gailun.attack(jianhao)
# gailun.attack(jianhao)


# 利用武器攻击
# gailun = GameRole('盖伦', 10, 100)
# zhaoxin = GameRole('赵信', 20, 90)
# great_sword = Weapon('大保健', 30)
# spear = Weapon('红缨枪', 40)
# great_sword.weapon_attack(gailun, zhaoxin)
# 上面需要解决的问题: 发起武器攻击的发起者应该是人类,而不是great_sword武器对象.
# 但是weapon_attack只能有Weapon类的对象去调用.


gailun = GameRole('盖伦', 10, 100)
zhaoxin = GameRole('赵信', 20, 90)
great_sword = Weapon('大保健', 30)
# print(great_sword)
gailun.equit_weapon(great_sword)  # 依赖关系
# print(gailun.weapon)
# gailun.weapon == great_sword
# great_sword.weapon_attack()
gailun.Weapon.weapon_attack(gailun, zhaoxin)
```



****

## 7. 什么是继承

**面向对象的三个大特性:封装 ,继承 , 多态**

```python
继承:
专业角度` : B继承A类 , B叫做A的子类,派生类, A叫做B的父类,基类,超类 , B类以及B类的对象使用A类的所有属			性以及方法
字面意思  : 继承就是继承父级的所有属性,父级的所有属性和方法都可以调用
		但是子类有的就用子类的,也就是说在先去子类找,子类没有再从父类找

继承分为单继承和多继承
```



## 8. 继承的优点

```
  	1. 节省代码
  	2. 增强耦合性
  	3. 代码规范化
  	4. 重构父类代码
```

## 9. 单继承

单继承 : 子类以及对象可以调用父类的属性和方法  单继承是只有一个父类

```python
class Person:
    def __init__(self,name,sex,age):
        self.name = name
        self.age = age
        self.sex = sex

class Cat:
    def __init__(self,name,sex,age):
        self.name = name
        self.age = age
        self.sex = sex

class Dog:
    def __init__(self,name,sex,age):
        self.name = name
        self.age = age
        self.sex = sex

class Animal:
    def __init__(self, name, age, sex):
        self.name = name
        self.age = age
        self.sex = sex
        
**********************************************
# 改用继承写
class Animal:
    live = "有生命的"
    def __init__(self, name, age, sex):
        self.name = name
        self.age = age
        self.sex = sex
    def eat(self):
        print('动物都需要进食')
class Person(Animal):
    pass
class Cat(Animal):
    pass
class Dog(Animal):
    pass
# 1. 从类名执行父类的属性
print(Person.__dict__) # {'__module__': '__main__', '__doc__': None}
print(Person.live) # 有生命的
*********************************************
# 2. 从对象执行父类的一切
p1 = Person("阿坤",18,"男")
print(p1.__dict__) # {'name': '阿坤', 'age': 18, 'sex': '男'}

p1.eat() # 动物都需要进食

Person.live = 'xxx'
print(Person.live) # xxx
# 注意: 子类以及子类对象只能调用父类的属性以及方法,不能操作(增删改)


# 既执行父类方法又执行子类方法
# 两种方式 :
class Animal:
    live = "有生命的"
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def eat(self):
        print('动物都需要进食')
class Person(Animal):
    def __init__(self,name,age,hobby):
        self.hobby = hobby
        #方法1 Animal.__init__(self,name,age)
        #方法2 super(Person,self).__init__(name,age)
        super().__init__(name,age)
    def eat(self):
        print("人类也需要进食!!!")
        super().eat()
p2 = Person("阿坤",18,"唱跳rap")
print(p2.__dict__) 
p2.eat()  
# 结果：
{'hobby': '唱跳rap', 'name': '阿坤', 'age': 18}
人类也需要进食!!!
动物都需要进食
```



## 10. 多继承

```python
面向对象 :
    python2.2之前:都都是经典类
    python2.2- 2.7 在这期间存在两种类型 : 经典类和新式类
        经典类: 基类不继承object,查询规则,依靠深度优先的原则
        新式类: 基类必须继承object(自动继承),查询规则:mro算法
    python3.x 只有新式类
```

```python
# 多继承
class God:
    def fly(self):
        print('会飞')
    def climb(self):
        print('神仙也可以爬树')

class Monkey:
    def climb(self):
        print('爬树')

class MonkeySun(God, Monkey):
    pass

sun = MonkeySun()
sun.climb() # 按先后顺序找 --class MonkeySun(God, Monkey):
```

```python
# 多继承顺序

class O:
    pass

class D(O):
    pass

class E(O):
    pass

class F(O):
    pass

class B(D, E):
    pass

class C(E, F):
    pass

class A(B, C):
    pass

# 工作中用mro()方法研究新式类的继承顺序
print(A.mro())
[<class '__main__.A'>, <class '__main__.B'>, <class '__main__.D'>, <class '__main__.C'>, <class '__main__.E'>, <class '__main__.F'>, <class '__main__.O'>, <class 'object'>]
```



## 11.  面向对象三大特征

```python
面向对象三大特征 : 继承  , 封装  , 多态

#继承 :  B继承A类 , B叫做A的子类,派生类, A叫做B的父类,基类,超类 , B类以及B类的对象使用A类的	
		所有属性以及方法
      实现代码的重用，相同的代码不需要重复的编写

# 封装 : 将一些东西内容封装到一个地方,还可以取出来
        将属性和方法封装到一个抽象的对象中

​		类设置静态属性,设置一些方法
​		对象 : 对象可以在其对象空间中封装一些属性

# 多态 : 一个事实的多种状态 , python中默认支持多态       (水)
        不同的子类对象调用相同的父类方法，产生不同的执行结果
多态的功能:
    让具有不同功能的函数可以使用相同的函数名，这样就可以用一个函数名调用不同内容(功能)的函数。
多态的特点:
    1、只关心对象的实例方法是否同名，不关心对象所属的类型；
	2、对象所属的类之间，继承关系可有可无；
	3、多态的好处可以增加代码的外部调用灵活度，让代码更加通用，兼容性比较强；
	4、多态是调用方法的技巧，不会影响到类的内部设计。
多态的应用场景 :
     对象所属的类之间没有继承关系:
class Duck(object):                                  # 鸭子类
    def fly(self):
        print("鸭子沿着地面飞起来了")

class Swan(object):                                  # 天鹅类
    def fly(self):
        print("天鹅在空中翱翔")

class Plane(object):                                 # 飞机类
    def fly(self):
        print("飞机隆隆地起飞了")

def fly(obj):                                        # 实现飞的功能函数
    obj.fly()

duck = Duck()
fly(duck)

swan = Swan()
```

```python
# 鸭子类型
class A:
    def login(self):
        pass
    def register(self):
        pass
class B:
    def login(self):
        pass
    def register(self):
        pass
鸭子类型 : A,B两个类,没有任何关系,但里面的功能相似,
# A 和 B两个类完全没有耦合性，但是在某种意义上他们却统一了一个标准。
# 对于不同功能的两个类内部的方法定义了相同的名字,这两个类就互为鸭子类型.
```



## 12. 类的约束

```python
# super() 严格意义并不是执行父类的方法.
# 单继承: super() 肯定是执行父类的方法.
# 多继承: super(S,self) 严格按照self从属于的类的mro的执行顺序,执行 S类的下一位.
```

```python
约束. 其实就是⽗类对⼦类进⾏约束. ⼦类必须要写xxx⽅法. 在python中约束的⽅式和⽅法有两种:
1. 使⽤抽象类和抽象⽅法, 由于该⽅案来源是java和c#. 所以使⽤频率还是很少的
2. 使⽤⼈为抛出异常的⽅案. 并且尽量抛出的是NotImplementError. 这样比较专业, ⽽且错误比较明确.(推荐)
```

```python
# 第一版
class Payment: 
　　""" 
　　此类什么都不做，
　　就是制定一个标准，
　　谁继承我，必须定义我里面的方法。
   """
    def pay(self,money):pass

class QQpay(Payment):
    def pay(self,money):
        print('使用qq支付%s元' % money)

class Alipay(Payment):
    def pay(self,money):
        print('使用阿里支付%s元' % money)

class Wechatpay(Payment):
    def fuqian(self,money):
        print('使用微信支付%s元' % money)


def pay(obj,money):
    obj.pay(money)

a = Alipay()
b = QQpay()

pay(a,100)
pay(b,200)

c = Wechatpay()
c.fuqian(300)
# 当c这样写的话
"""
pay(c,300)
因为微信类中没有pay()函数,所有要去父类找,而父类中是的pass,因此什么都不打印
"""
```

```
此时我们要用到对类的约束，对类的约束有两种：
1. 提取⽗类. 然后在⽗类中定义好⽅法. 在这个⽅法中什么都不⽤⼲. 就抛⼀个异常就可以了. 这样所有的⼦类都必须重写这个⽅法. 否则. 访问的时候就会报错. 

2. 使⽤元类来描述⽗类. 在元类中给出⼀个抽象⽅法. 这样⼦类就不得不给出抽象⽅法的具体实现. 也可以起到约束的效果.
```

```python
# 第二版
class Payment:
    """
    此类什么都不做，就是制定一个标准，谁继承我，必须定义我里面的方法。
    """
    def pay(self,money):
        raise Exception("你没有实现pay方法") # 主动抛出异常提示

class QQpay(Payment):
    def pay(self,money):
        print('使用qq支付%s元' % money)

class Alipay(Payment):
    def pay(self,money):
        print('使用阿里支付%s元' % money)

class Wechatpay(Payment):
    def fuqian(self,money):
        print('使用微信支付%s元' % money)


def pay(obj,money):
    obj.pay(money)

a = Alipay()
b = QQpay()
c = Wechatpay()
pay(a,100)
pay(b,200)
pay(c,300)
```

```python
# 第三版
from abc import ABCMeta,abstractmethod
class Payment(metaclass=ABCMeta):    # 抽象类 接口类  规范和约束  metaclass指定的是一个元类
    @abstractmethod
    def pay(self):pass  # 抽象方法

class Alipay(Payment):
    def pay(self,money):
        print('使用支付宝支付了%s元'%money)

class QQpay(Payment):
    def pay(self,money):
        print('使用qq支付了%s元'%money)

class Wechatpay(Payment):
    # def pay(self,money):
    #     print('使用微信支付了%s元'%money)
    def recharge(self):pass

def pay(a,money):
    a.pay(money)

a = Alipay()
a.pay(100)
pay(a,100)    # 归一化设计：不管是哪一个类的对象，都调用同一个函数去完成相似的功能
q = QQpay()
q.pay(100)
pay(q,100)
w = Wechatpay()
pay(w,100)   # 到用的时候才会报错


# 抽象类和接口类做的事情 ：建立规范
# 制定一个类的metaclass是ABCMeta，
# 那么这个类就变成了一个抽象类(接口类)
# 这个类的主要功能就是建立一个规范
```



## 13. super的深入理解

**super是严格按照类的继承顺序执行！！！**

```python
# super() 严格意义并不是执行父类的方法.
# 单继承: super() 肯定是执行父类的方法.
# 多继承: super(S,self)  严格按照self从属类的mro顺序,执行S类的下一位类

```

```python
# 单继承
class A:
    def f1(self):
        print('in A f1')
    
    def f2(self):
        print('in A f2')


class Foo(A):
    def f1(self):
        super().f2()
        print('in A Foo')
        
        
obj = Foo()
obj.f1()
# in A f2
# in A Foo

```

**多继承: super(S,self) 严格按照self从属于的类的mro的执行顺序,执行 S类的下一位.**

```python
class A:
    def f1(self):
        print('in A')

class Foo(A):  
    def f1(self): # 2.执行f1 按照mro顺序,在Foo下一位找f1()
        super().f1()  
        print('in Foo') #4 执行打印

class Bar(A):
    def f1(self): # 3.执行打印
        print('in Bar')

class Info(Foo,Bar):
    def f1(self):  # 1.执行函数f1,  按照mro顺序在父类Foo找f1()
        super().f1()
        print('in Info f1')  #5 执行打印

obj = Info()
obj.f1()

'''
in Bar
in Foo
in Info f1
'''
print(Info.mro())  # [<class '__main__.Info'>, <class '__main__.Foo'>, <class '__main__.Bar'>, <class '__main__.A'>, <class 'object'>]

```



## 14. 私有成员

```python
类的成员两种形式:
    公有成员 : 在任何地方都能访问
	私有成员 : 只有在类的内部才能访问
#私有成员只有在类的内部才能访问,(不可在派生类中访问)
```

```python
细分类的成员组成:
class A:
    name = "python" 	 # 第一部分:静态字段(静态变量)
    def __init__(self): # 第二部分:方法部分
        pass
# 详细划分:
class A:
    name = "python"  # 静态变量
    __age = 18		# 私有静态变量
    def __init__(self,name,sex): # 特殊方法
        self.name = name  # d对象属性(普通字段)
        self.__sex = sex  # 私有对象属性(私有普通字段)
    def func(self): # 普通方法
        pass
    def __func(self): # 私有方法
        pass
    @classmethod # 类方法
    def class_func(cls):
        pass
    @property  # 属性
    def prop(self):
        pass
```



**私有静态属性**

```python
class B:
    school_name = '来自魔鬼中的天使'
class A(B):
    class_name = '邓紫棋'
    def func(self):
        print(self.class_name)

obj = A()
print(obj.class_name)
obj.func()
print(obj.school_name)
###
邓紫棋
邓紫棋
来自魔鬼中的天使
#*# 对于类的公有静态属性,类的外部,类的内部,派生类都可以访问.

class B:
    __music = "泡沫"
class A(B):
    __singer = "邓紫棋"
    def func(self):
        print(self.__singer)
         print(self.__singer)
obj = A()
obj.func()
#  print(self.__singer) - 邓紫棋
#  print(self.__singer) - 报错

# 私有静态属性: 类内部可以访问
# 派生类不可访问(其父级不可访问)
```

```python
# 对象的私有属性
class B:
    school_name = '老男孩'
    __consc_edu = '良心'
    def __init__(self, weight):
        self.__weight = weight
class A(B):
    def __init__(self, name, age, weight):
        super().__init__(weight)
        self.name = name
        self.__age = age
    def func(self):
        print(self.__age)  # 类的内部可以使用
        # print(self.__weight)  # 派生类中不可访问

obj = A('小马哥',18, 180)
print(obj.__age)  # 类的外部不能访问
obj.func()

# 作用 :如果想设定一些私有的或者是不想让类外面用到,密码,加密方式,等设置成私有成员.
# 但是私有成员除了在内部可以访问, 其实在外部是可以访问的

class A:
    __girlnum = '1个'
print(A.__dict__)
print(A._A__girlnum) # 1个
# python中所有的私有成员: 就是在私有成员前面加上 _类名而已.
# 但千万不要这样去访问!!!
```

## 15. 类方法

```python
# 使用装饰器@classmethod。
#类方法就是用类名调用自身类的方法.类名作为参数传给cls

class A:
    num = 1
    def func(self):
        print('实例方法')
    @classmethod  # 类方法: 由类名直接调用的方法,他会自动的将类名传给cls
    def a_func(cls):
        # print(f'cls---> {cls}')
        # print(cls.num)
        # o = cls()
        # print(o)
        # print('这是类方法')
        print(cls)
obj = A()
obj.func()
A.func(obj)
print(A)
A.a_func()
obj.a_func()  # 对象也可以调用类方法,但是会自动将其从属于的类名传给cls


# 定义一个Student类,我要统计学生的个数.
class Student:
    num = 0
    def __init__(self,name):
        self.name = name
        self.count()

    @classmethod
    def count(cls):
        cls.num = cls.num + 1

    @classmethod
    def get_num(cls):
        return cls.num


ly = Student('李业')
sq = Student('申强')
sq1 = Student('申强')
sq2 = Student('申强')
sq3 = Student('申强')
sq4 = Student('申强')
print(Student.get_num())
```

## 16. 静态方法

静态方法: 

​		不依赖于类,也不依赖于对象,他就是一个普通的函数放置于类中是结构更加清晰与合理.

```python
使用装饰器@staticmethod。

静态方法是类中的函数，不需要实例。静态方法主要是用来存放逻辑性的代码，逻辑上属于类，但是和类本身没有关系，也就是说在静态方法中，不会涉及到类中的属性和方法的操作。可以理解为，静态方法是个独立的、单纯的函数，它仅仅托管于某个类的名称空间中，便于使用和维护。

class A:
    def func(self):
        print(111)

    @classmethod
    def a_func(cls):
        print(cls)

    @staticmethod
    def static_func(a,b,c):
        print(f'{a}{b}{c}静态方法')

obj = A()
obj.static_func(1,2,3) # 123静态方法

# 例 :定义一个关于时间操作的类，其中有一个获取当前时间的函数
import time

class TimeTest(object):
    def __init__(self, hour, minute, second):
        self.hour = hour
        self.minute = minute
        self.second = second

    @staticmethod
    def showTime():
        return time.strftime("%H:%M:%S", time.localtime())

print(TimeTest.showTime())
t = TimeTest(2, 10, 10)
nowTime = t.showTime()
print(nowTime)
```



## 17. 属性

```python
什么是特性property:
property是一种特殊的属性，访问它时会执行一段功能（函数）然后返回值
```

```python
例一：BMI指数（bmi是计算而来的，但很明显它听起来像是一个属性而非方法，如果我们将其做成一个属性，更便于理解）

成人的BMI数值：
过轻：低于18.5
正常：18.5-23.9
过重：24-27
肥胖：28-32
非常肥胖, 高于32
　　体质指数（BMI）=体重（kg）÷身高^2（m）
　　EX：70kg÷（1.75×1.75）=22.86

class People:
    def __init__(self,name,weight,height):
        self.name=name
        self.weight=weight
        self.height=height
    @property
    def bmi(self):
        return self.weight / (self.height**2)

p1=People('egon',75,1.85)
print(p1.bmi)
```

```python
为什么要用property

将一个类的函数定义成特性以后，对象再去使用的时候obj.name,根本无法察觉自己的name是执行了一个函数然后计算出来的，这种特性的使用方式遵循了统一访问的原则

由于新式类中具有三种访问方式，我们可以根据他们几个属性的访问特点，分别将三个方法定义为对同一个属性：获取、修改、删除
```

```python
class Foo:
    @property
    def AAA(self):
        print('get的时候运行我啊')

    @AAA.setter
    def AAA(self,value):
        print('set的时候运行我啊')

    @AAA.deleter
    def AAA(self):
        print('delete的时候运行我啊')

#只有在属性AAA定义property后才能定义AAA.setter,AAA.deleter
f1=Foo()
f1.AAA
f1.AAA='aaa'
del f1.AAA

或者：
class Foo:
    def get_AAA(self):
        print('get的时候运行我啊')

    def set_AAA(self,value):
        print('set的时候运行我啊')

    def delete_AAA(self):
        print('delete的时候运行我啊')
    AAA=property(get_AAA,set_AAA,delete_AAA) #内置property三个参数与get,set,delete一一对应

f1=Foo()
f1.AAA
f1.AAA='aaa'
del f1.AAA
```

```python
class Goods(object):

    def __init__(self):
        # 原价
        self.original_price = 100
        # 折扣
        self.discount = 0.8

    @property
    def price(self):
        # 实际价格 = 原价 * 折扣
        new_price = self.original_price * self.discount
        return new_price

    @price.setter
    def price(self, value):
        self.original_price = value

    @price.deltter
    def price(self, value):
        del self.original_price

obj = Goods()
obj.price         # 获取商品价格
obj.price = 200   # 修改商品原价
del obj.price     # 删除商品原价


```



## 18. isinstance 和 issubclass

```python
# isinstance(a,b)：判断a是否是b类（或者b类的派生类）实例化的对象

class A:
    pass
class B(A):
    pass
obj = B()
print(isinstance(obj,B))# ture
print(isinstance(obj,A)) # ture

```

```python
# issubclass(a,b)： 判断a类是否是b类（或者b的派生类）的派生类

class A:
    pass
class B(A):
    pass
class C(B):
    pas
print(issubclass(B,A)) # ture
print(issubclass(C,A)) # ture


```

```python
# list str tuple dict等这些类与 Iterble类 的关系是什么？
from collections import Iterable
print(isinstance([1,2,3], list))  # True
print(isinstance([1,2,3], Iterable))  # True
print(issubclass(list,Iterable))  # True

# 由上面的例子可得，这些可迭代的数据类型，list str tuple dict等 都是 Iterable的子类。

```



## 18. 元类(type)  (type与object的区别)

按照Python的一切皆对象理论，类其实也是一个对象，那么类这个对象是从哪里实例化出来的呢？

```python
print(type('abc'))
print(type(True))
print(type(100))
print(type([1, 2, 3]))
print(type({'name': '太白金星'}))
print(type((1,2,3)))
print(type(object))

class A:
    pass

print(isinstance(object,type))
print(isinstance(A, type))

```

type元类是获取该对象从属于的类,而type类比较特殊，Python原则是：一切皆对象，其实类也可以理解为'对象',而type元类又称作构建类，python中大多数内置的类（包括object）以及自己定义的类，都是由type元类创造的。

\* 而type类与object类之间的关系比较独特：object是type类的实例，而type类是object类的子类，这种关系比较神奇无法使用python的代码表述，因为定义其中一个之前另一个必须存在。所以这个只作为了解。

## 19. 异常处理

```python
# 程序中难免出现错误，而错误分成两种:

1.语法错误（这种错误，根本过不了python解释器的语法检测，必须在程序执行前就改正）:
    print(haha  # 错误示例
2.逻辑错误:
	用户输入不完整(比如输入为空)或者输入非法(输入不是数字)
		num=input(">>: ")
		int(num)

```

```python
在python中不同的异常可以用不同的类型（python中统一了类与类型，类型即类）去标识，不同的类对象标识不同的异常，一个异常标识一种错误

# 触发IndexError
l=['egon','aa']
l[3]
# 触发KeyError
dic={'name':'egon'}
dic['age']

#触发ValueError
s='hello'
int(s)

```

```python
常用异常 :
AttributeError 试图访问一个对象没有的树形，比如foo.x，但是foo没有属性x
IOError 输入/输出异常；基本上是无法打开文件
ImportError 无法引入模块或包；基本上是路径问题或名称错误
IndentationError 语法错误（的子类） ；代码没有正确对齐
IndexError 下标索引超出序列边界，比如当x只有三个元素，却试图访问x[5]
KeyError 试图访问字典里不存在的键
KeyboardInterrupt Ctrl+C被按下
NameError 使用一个还未被赋予对象的变量
SyntaxError Python代码非法，代码不能编译(个人认为这是语法错误，写错了）
TypeError 传入对象类型与要求的不符合
UnboundLocalError 试图访问一个还未被设置的局部变量，基本上是由于另有一个同名的全局变量，
导致你以为正在访问它
ValueError 传入一个调用者不期望的值，即使值的类型是正确的

```

**什么是异常处理**

```python
python解释器检测到错误，触发异常（也允许程序员自己触发异常）
程序员编写特定的代码，专门用来捕捉这个异常（这段代码与程序逻辑无关，与异常处理有关）
如果捕捉成功则进入另外一个处理分支，执行你为其定制的逻辑，使程序不会崩溃，这就是异常处理

```

**如何进行异常处理**

首先须知，异常是由程序的错误引起的，语法上的错误跟异常处理无关，必须在程序运行前就修正

```python
num1=input('>>: ') #输入一个字符串试试
int(num1)

用if语句判断太多
之前的异常处理:
    
def test():
    print('test running')
choice_dic={
    '1':test
}
while True:
    choice=input('>>: ').strip()
    if not choice or choice not in choice_dic:continue #这便是一种异常处理机制啊
    choice_dic[choice]()

```

**python异常处理**

```python
try:
     被检测的代码块
except 异常类型：
     try中一旦检测到异常，就执行这个位置的逻辑

```

```python
# 什么叫异常?
# 你的程序出现中断,飘红,致使你的整个项目中断了.
# 错误类型:

# 语法错误.
# 语法错误就不应该现在你的代码中.
# if 1 > 2
#     pass
#
# # l1 = [11,22.44.556.788]
#
# while 1:
#     print(111)
#         print(222)

# 逻辑错误:
# num = input('请输入序号')
# int(num)
#
# l1 = [1, 2, 3]
# print(l1[4])

# dic = {1: 2,'a': 'b'}
# print(dic[3])
# KeyError

# 用if进行异常处理
# num = input('请输入:')
# if num.isdecimal():
#     num = int(num)
#     if 0 < num < 6 :
#         pass
#     elif num == 10:
#         pass
# else:
#     pass

# try

# 单分支

# try:
#     l1 = [1,2,3]
#     print(l1[100])
#
#     dic = {1: 2,'a': 'b'}
#     print(dic[3])
#
#     num = input('请输入序号')
#     int(num)
#
# except IndexError as e:
#     # print('处理了索引错误')
#     print(e)
#
# print(111)
# print(222)


# 多分支

# try:
#     # l1 = [1,2,3]
#     # print(l1[100])
#     #
#     # dic = {1: 2,'a': 'b'}
#     # print(dic[3])
#
#     num = input('请输入序号')
#     int(num)
#
# except IndexError as e:
#     print('处理了索引错误')
# except KeyError as e:
#     print('没有此键')
# except ValueError as e:
#     print('出现了转化错误')
#
# print(111)
# print(222)

# 及时解决异常,避免程序中断.
# 程序的分流.

dic = {
    1: 111,
    2: 333,
    3: 555,
}


# while 1:
#     try:
#         num = input('请输入序号')
#         int(num)
#         print(dic[int(num)])
#
#     except KeyError as e:
#         print('选项超出范围,请重新输入')
#     except ValueError as e:
#         print('请输入数字')

# print(111)
# print(222)

# 万能异常

# try:
#     num = input('请输入序号')
#     int(num)
#     print(dic[int(num)])
#
# except Exception as e:
#     print(e)
# print(111)

# 什么时候用万能异常,什么时候用多分支?
#如果你只是想把这个异常处理掉,让程序继续执行. 万能异常.
# 如果出现了异常,你是想根据不同的异常执行不同的逻辑流程,你要采取多分支.

# 第四种 万能 + 多分支

# dic = {
#     1: 111,
#     2: 333,
#     3: 555,
# }
#
#
# while 1:
#     try:
#         num = input('请输入序号')
#         int(num)
#         print(dic[int(num)])
#
#     except KeyError as e:
#         print('选项超出范围,请重新输入')
#     except ValueError as e:
#         print('请输入数字')
#     except Exception:
#         pass

# 异常处理其他成员

# try:
#     num = input('请输入序号')
#     int(num)
#     print(dic[int(num)])
#
# except KeyError as e:
#
#     print('选项超出范围,请重新输入')
# except Exception:
#     pass
# # else:  # 如果上面无异常执行else语句,否则不执行else语句.
# #     print(666)
#
# finally: # 在整个程序终止之前,执行finally
#     print('执行finally')

# 1. 文件操作
# f = open('register', mode='w')
# f.write('fdjsaklfd')
# f.write('fdjsaklfd')
# f.write('fdjsaklfd')
# l1 = [1,2,3]
# print(l1[1000])
# f.write('fdjsaklffjdsklaf')
#
# f.close()

# try:
#     f = open('register', mode='w')
#     f.write('fdjsaklfd')
#     f.write('fdjsaklfd')
#     f.write('fdjsaklfd')
#     l1 = [1, 2, 3]
#     print(111)
#     print(l1[1000])
#     f.write('fdjsaklffjdsklaf')
# finally:
#     print('哈哈哈哈')
    # f.close()

# 数据库: 连接数据库引擎.

# try:
#     int('e')
# finally:
#     print(777)

# 在函数中 finally.
# 结束函数之前,先要执行finally语句.

# def func():
#     try:
#         a = 1
#         b = 2
#         return a + b
#     finally:
#         print(666)
# func()

# 主动抛出异常:
# raise Exception('fdkslafjdslkf')

# 断言:
# assert 条件  # 源码上assert.
# assert 1 == 2
# print(11)
# print(22)
# print(33)


# 自定义异常(了解)

# TypeError
#
# class Connection(BaseException):
#
#     def __init__(self,msg):
#         self.msg = msg
#
#
# raise Connection('触发了连接异常')


# 异常处理总结:
# 异常处理不能经常使用:异常处理耗费性能.有些错误是需要进行分流使用.代码的可读性变差.
# 关键节点使用.


```



## 20. 反射

```python
反射 : 通过字符串去操作一个对象
    字符串 :字符串类型
    对象 : 实例, 类, 当前文件(模块), 其他模块
hasattr()	getattr()	setattr()	delattr()
```

```python
1. 对对象的反射
class Foo:
    f = "类的静态变量"
    def __init__(self,name,age):
        self.name = name
        self.age = age
    def say_hello(self):
        print("hello,%s"%self.name)
obj = Foo("泰迪",1)
# 检测是否存在某属性
print(hasattr(obj,'name')) # True
print(hasattr(obj,'age')) # True

# 获取属性
n = getattr(obj,'name')
print(n) # 泰迪
func = getattr(obj,'say_hello')
func() # hello,泰迪
print(getattr(obj,'sex',None))  #  若没有此属性,则会返回设置的内容 :None

#s 设置属性
setattr(obj,'sex','公')
print(obj.__dict__) # {'name': '泰迪', 'age': 1, 'sex': '公'}
print(obj.sex) # 公

# 删除属性
delattr(obj,'sex')
print(obj.__dict__) # {'name': '泰迪', 'age': 1}


#查看判断属性
hasattr(对象,属性名) 返回True & False

#获取属性
getattr(对象,属性名,不存在返回的内容)

# 设置属性
setattr(对象,定义的属性名,属性内容)

# 删除属性
delattr(对象,要删除的属性名)

# 调用对象中的方法
if hasattr(obj,"func"): # func必须是字符串形式
```

```python
2 对类的反射
class Foo(object):
    song = "来自天堂的魔鬼"
    def __init__(self,name):
        self.name = name
    def func(self):
        return 'func'
    @staticmethod
    def bar():
        return 'bar'
print(getattr(Foo,'song')) # 来自天堂的魔鬼
print(getattr(Foo,'func')) # 没有加 () <function Foo.func at 0x0000025CA8E2DC80>
print(getattr(Foo,'bar')()) # bar
```

```python
3. 从当前脚本研究反射 (当前文件看做是一个类)
def func1():
    print("in func1")
def func2():
    print("in func2")
def func3():
    print("in func3")
# l1 = [func1,func2,func3]
# l1 = [f'func{i}' for i in rang(1,4)]  # func(i)结果是字符串 没法执行
import sys
this_modules = sys.modules[__name__] # 本文件的文件名(对象)
print(this_modules) # <module '__main__' from 'E:/My Pythom/Day26/笔记.py'>
getattr(this_modules,"func1")() # in func1

# 针对上 func(i)结果是字符串 没法执行 解决办法
for  i in l1:
    getattr(this_modules,i)()

       
    
 class B:
    static = "静态属性"
    def func1():
        print("in func1")

    def func2():
        print("in func2")

    def func3():
        print("in func3")
import sys
this_modules = sys.modules[__name__]
cls = getattr(this_modules,"B")
obj = cls()
print(obj.static)  # 静态属性
```

```python
4. 从其他模块进行反射
# 一个模块中的代码(文件test.py)
def test():
    print('from the test')

# 另一个模块中的代码(文件index.py)
import test as obj
obj.test() # from the test

print(hasattr(obj,'test')) # True
getattr(obj,'test')() # from the test
```

```python
#反射的简单应用场景
class Auth:
    function_list = [('login',"请登录"),('register',"请注册"),('exit',"退出")]
    def login(self):
        print("登录函数")
    def register(self):
        print("注册函数")
    def exit(self):
        print("退出...")

while 1:
    obj = Auth()
    for num,option in enumerate(obj.function_list,1):
        print(num,option[1])
    choice_num = int(input("请选择 :").strip())
    if hasattr(obj, Auth.function_list[choice_num-1][0]):
        getattr(obj, Auth.function_list[choice_num-1][0])()
```





## 21. 函数vs方法

```python
# 判断函数和方法 ：
	（类名调用就是函数）
	（对象调用就是方法）
1. 通过函数名可以大致判断(print):
    function(函数)
    method(方法)
def x():
    pass
print(x) # <function x at 0x00000197BC69DB70>

class A:
    def func(self):
        pass
print(A.func) # <function A.func at 0x000002462FD1DC80>
obj = A()
print(obj.func) # <bound method A.func of <__main__.A object at 0x000001A717DA99E8>>


2.通过types模块验证 :
	from types import FunctionType
	from types import MethodType
	def func():
    	pass
	class A:
    	def func(self):
        	pass
	obj = A()
	print(isinstance(func,FunctionType)) # True
	print(isinstance(A.func,FunctionType)) # True
	print(isinstance(obj.func,FunctionType)) # False
	print(isinstance(obj.func,MethodType)) # True
    
    
3.  静态方法是函数
from types import FunctionType
from types import MethodType
class A:
    def func(self):
        pass
    @classmethod
    def func1(cls):
        pass
    @staticmethod
    def func2(self):
        pass
obj = A()
# 静态方法其实是函数
print(isinstance(A.func2,FunctionType)) # True
print(isinstance(obj.func2,FunctionType)) # True
    
    
4. 函数与方法的区别 :
函数 : 都是显性传参 如我们要指明为len()函数传递一些要处理数据。函数则跟对象无关。
方法 : 存在隐性传参 方法可以操作类内部的数据。
```

## 22. 双下方法

```python
# 单列模式
class A:
#     __instance = None
#
#     def __new__(cls, *args, **kwargs):
#         if not cls.__instance:
#             object1 = object.__new__(cls)
#             cls.__instance = object1
#         return cls.__instance
#
#
# obj = A()
# obj1 = A()
# obj2 = A()
# print(obj,obj1,obj2)
```

```python
# __len__
class A:
    def __init__(self):
        self.a = 1
        self.b = 2

    def __len__(self):
        return len(self.__dict__)
a = A()
print(len(a)) # 2

```

```python
# __hash__
class A:
    def __init__(self):
        self.a = 1
    def __hash__(self):
        return hash(str(self.a))
a = A()
print(hash(a)) # -2977365518758686125

```

```python
# __str__
class A:
    def __str__(self):
        return "a坤"
a = A()
print(a) # a坤

```

```python
# __repr__
class A:
    def __repr__(self):
        return "星星"
a = A()
print(a) # 星星
print(repr(a)) # 星星

```

```python
# __call__
class A:
    def __init__(self):
        print(111)
    def __call__(self, *args, **kwargs):
        print(222)
obj = A() # 111
obj() # 自动执行__call__  222

```

```python
class A:
    def __init__(self):
        self.a = 1
        self.b = 2

    def __eq__(self,obj):
        if  self.a == obj.a and self.b == obj.b:
            return True
a = A()
b = A()
print(a == b) # True

```

```python
# __new__
class A:
    def __init__(self):
        print("in __init__")
a = A() # in __init__


class A:
    def __init__(self):
        print("in __init__")
    def __new__(cls, *args, **kwargs):
        print(" in __new__")
a = A() # in __new__ 创造并返回一个新对象  只执行__new__  


# 单列模式  一个类只能实例化一个对象,无论你实例化多少次,内存中都只有一个对象
class A:
    status = None
    def __new__(cls, *args, **kwargs):
        if cls.status is None:
            obj = object.__new__(cls)
            cls.status = obj
        return cls.status
a = A()
b = A()
c = A()
print(a) # <__main__.A object at 0x000001C6E51499B0>
print(b) # <__main__.A object at 0x000001C6E51499B0>
print(c) # <__main__.A object at 0x000001C6E51499B0>


```

```python
# __item__
class Foo:
    def __init__(self,name):
        self.name = name
    def __getitem__(self, item):
        print(self.__dict__[item])
    def __setitem__(self, key, value):
        self.__dict__[key] = value
    def __delitem__(self, key):
        print("del obj[key]时,执行我")
        self.__dict__.pop(key)
    def __delattr__(self, item):
        print("del obj.key时,执行我")
        self.__dict__.pop(item)
f1 = Foo('阿坤')
f1['age'] = 18
print(f1.__dict__) # {'name': '阿坤', 'age': 18}
f1["age1"] = 50 # {'name': '阿坤', 'age': 18, 'age1': 50}
del f1.age1 # del obj.key时,执行我
f1["name"] = "哈哈" # {'name': '哈哈', 'age': 18}

```

```python
#上下文管理器相关
# __enter__  __exit__

# 如果想要对一个类的对象进行with  as 的操作 不行。
class A:
    def __init__(self,text):
        self.text = text
with A('金鳞岂是池中物') as f1:
    print(f1.text)
# 报错信息 :AttributeError: __enter__


class A:
    def __init__(self,text):
        self.text = text
    def __enter__(self): # 开启上下文管理器对象时触发此方法
        print("不要看金鳞")
        return self # 将实例化的对象返回给f1
    def __exit__(self, exc_type, exc_val, exc_tb): # 执行完上下文管理器对象f1时触发此方法
        print("把书赶紧烧了")
with A('金鳞') as f1:
    print(f1.text) 
print(f1.text) 
不要看金鳞
金鳞
把书赶紧烧了
金鳞

```

























