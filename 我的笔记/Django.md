# 1. web框架

## HTTP协议

**发送HTTP请求**

```
通过TCP套接字,客户端Web服务器发送一个文本的请求报文,一个请求报文由请求行、请求头部、空行、和	请求数据四部分组成
```



**服务器接受请求并返回HTTP响应**

```
Web服务器解析请求，定位请求资源。服务器将资源副本写到TCP套接字，由客户端读取。一个响应由状态行、响应头部、空行和响应数据四部分组成
```



**在浏览器地址栏键入URL，按下回车之后经历的过程**

```python
1. 浏览器向DNS服务器请求解析该URL中的域名所对应的IP地址。
2. 解析出IP地址后，根据该IP地址和默认端口80，和服务器建立TCP连接。
3. 浏览器发出读取文件（URL中域名后面部分对应的文件）的HTTP请求，该请求报文作为TCP三次握手的第三次报文的数据发送给服务器
4. 服务器对浏览器作出响应,并把对应的html文本发送给浏览器
5. 释放TCP连接
6. 浏览器渲染HTML并显示内容
```

**HTTP请求方法**

- HTTP/1.1协议中共定义了八种方法(动作),来以不同方式操作指定的资源:

```python
1. GET :
	向指定的资源发出"显示"请求。使用GET方法应该只用在读取数据上，而不应被用于产生"副作用"的操作中,例如在Web Application中,其中一个原因是GET可能会被网络蜘蛛等随意访问.
    
2. HEAD :
    与GET方法一样，都是向服务器发出指定资源的请求。只不过服务器将不传回资源的本文部分。它的好处在于，使用这个方法可以在不必传输全部内容的情况下，就可以获取其中“关于该资源的信息”（元信息或称元数据）。
    
3. POST :
    向指定资源提交数据，请求服务器进行处理（例如提交表单或者上传文件）。数据被包含在请求本文中。这个请求可能会创建新的资源或修改现有资源，或二者皆有。
    
4. PUT :
    向指定资源位置上传其最新内容。
   
5. DELETE :
    请求服务器删除Request-URI所标识的资源。
    
6. TRACE :
    回显服务器收到的请求，主要用于测试或诊断。
    
7. OPTIONS :
    这个方法可使服务器传回该资源所支持的所有HTTP请求方法。用'*'来代替资源名称，向Web服务器发送OPTIONS请求，可以测试服务器功能是否正常运作。
    
 8. CONNECT :
    HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。通常用于SSL加密服务器的链接（经由非加密的HTTP代理服务器）
```



- **HTTP状态码**

  - 所有HTTP响应的第一行都是状态行，依次是当前HTTP版本号，3位数字组成的状态代码，以及描述状态的短语，彼此由空格分隔。

  ```python
  1xx消息——请求已被服务器接收，继续处理
  2xx成功——请求已成功被服务器接收、理解、并接受 :
  	200 ok - 请求成功	
  3xx重定向——需要后续操作才能完成这一请求
  4xx请求错误——请求含有词法错误或者无法被执行 :
      403 Forbidden - 服务器已经理解请求，但是拒绝执行它
      404 Not Found - 请求失败，请求所希望得到的资源未被在服务器上发现。
  5xx服务器错误——服务器在处理某个正确请求时发生错误
  ```

  

- **URL**

  - 超文本传输协议（HTTP）的统一资源定位符将从因特网获取信息的五个基本元素包括在一个简单的地址中：

  ```python
  1. 传送协议。
  2. 层级URL标记符号(为[//],固定不变)
  3. 访问资源需要的凭证信息（可省略）
  4. 服务器。（通常为域名，有时为IP地址）
  5. 端口号。（以数字方式表示，若为HTTP的默认值“:80”可省略）
  6. 路径。（以“/”字符区别路径中的每一个目录名称）
  7. 查询。（GET模式的窗体参数，以“?”字符为起点，每个参数以“&”隔开，再以“=”分开参数名称与数据，通常以UTF8的 	 URL编码，避开字符冲突的问题）
  8. 片段。以“#”字符为起点
  ```

- **HTTP请求格式**

  ```python
  请求方法 | 空格 | URL | 空格 | 协议版本 | 回车符 | 换行符		--→ 	请求行
  
  头部字段名 | : | 值 | 回车符 | 换行符 				 }
      		...									 }	--→   请求头部
  头部字段名 | : | 值 | 回车符 | 换行符 				 }
      
  !@#$%^&* ...										--→  请求数据
  ```

  

- **HTTP相应格式**

  ```python
  协议版本 | 空格 | 状态码 | 空格 | 状态码描述 | 回车符 | 换行符     --→ 	状态行
  
  头部字段名 | : | 值 | 回车符 | 换行符 				 }
      		...									 }	   --→   响应头部
  头部字段名 | : | 值 | 回车符 | 换行符 				 }
      
  请求方法 | 空格 | URL | 空格 | 协议版本 | 回车符 | 换行符		--→ 	响应正文
  ```

------



# 2. Django的使用

## 2.1. 自己写的Web框架

```python
mport socket

# 创建一个socket对象
sk = socket.socket()

# 绑定ip和端口
sk.bind(('127.0.0.1', 8848))

# 监听
sk.listen()


def index(url):
    ret = '欢迎进入红浪漫! - {}'.format(url)
    return ret.encode('utf-8')


def home(url):
    ret = '欢迎回家! - {}'.format(url)
    return ret.encode('utf-8')


def help_me(url):
    ret = '再等30年,你又是条好汉! - {}'.format(url)
    return ret.encode('utf-8')


list1 = [
    ('/index', index),
    ('/home', home),
    ('/help_me', help_me),
]

# 等待连接
while True:
    conn, addr = sk.accept()

    data = conn.recv(1024)
    url = data.decode('utf-8').split()[1]  # 获取用户输入的路径

    # for i in list1:
    #     if url == i[0]:
    #         ret = i[1](url)
    #         break
    # else:
    #     ret = '被查办了!'.encode('utf-8')

    func = None
    for i in list1:
        if url == i[0]:
            func = i[1]
            break
    if func:
        ret = func(url)
    else:
        ret = '被查办了!'.encode('utf-8')

    conn.send(b'HTTP/1.1 200 OK\r\ncontent-type: text/html; charset=utf-8\r\n\r\n')
    conn.send(ret)

    conn.close()
```



## 2.2 Django的安装

- **命令行下载安装**

  ```python
  pip3 install django	 - 下载安装的是最新版本
  pip3 install django==1.11.23 -i https://pypi.tuna.tsinghua.edu.cn/simple	- 选择版本,选择安装源
  ```

  - **创建项目**

    ```python
    1. 首先进入要创建项目的文件夹
    2. SHIFT + 鼠标右键 打开命令行
    3. 执行命令 : django-admin startproject 项目名
    ```
    
  - **启动项目**
    ```python
  	python manage.py runserver	# 默认127.0.0.1 : 80000
  python manage.py runserver 80 # 修改 80端口
  python manage.py runserver 0.0.0.0:80 # 修改地址和端口
    ```
  
- **pycharm**

  - **创建项目**

    ```python
    1. New Project
    2. Django - 选择项目目录 - 选python版本 - Create
    ```

  - **启动项目**

    ```python
    选中项目目录 - run(图标)
    ```

  - **pycharm创建项目的一些说明**

    ```python
    1. settings.py会在项目根目录下自动创建一个名字为 templates 用于放HTML等文件的文件夹 :
    	'DIRS': [os.path.join(BASE_DIR, 'templates')]
    2. 导入模块 ( urls.py ):
       from django.shortcuts import HttpResponse,render
        def index(request):
            return HttpResponse('欢迎进入红浪漫!')  #   返回字符串
        def home(request):
            return render(request,'home.html') # 返回html页面
        urlpatterns = [
            url(r'^admin/', admin.site.urls),
            url(r'^home/', home),
            url(r'^index/', index),
        ]
    3. 修改ip和端口 :
    	Run → Edit Configurations
    ```
    

------



# 3. 静态文件的配置

## 3.1. STATIC_URL配置

- **项目中`settings.py`文件下 :**

  ```python
  STATIC_URL = '/static/'
  
  STATICFILES_DIRS = [    #按照列表的顺序进行查找
      os.path.join(BASE_DIR,'static'),
      os.path.join(BASE_DIR,'xxx')
  ]
  
  
  os.path.join(BASEDIR, 'static', 'css')是静态文件存放的实际路径，STATIC_URL='/static/'中的/statis/是这个路径的别名。两者是一个映射关系，如果要使用该静态文件，那么静态文件的URL中的"实际路径部分"就要使用别名来代替
  ```

  - `settings.py`配置好后, 需要在项目下新建文件`static`, 这个`static`是存放 `CSS, JavaScript, Images`等静态文件的一个根目录

------



# 4. 登录验证

**form表单**

```html
 form表单中 action 填写提交表单的ip地址和端口 method 是提交请求方式 默认GET请求,html中要小写
<form class="form-signin" action = "" method="post">
```

```html
<input class="form-control" id="inputEmail" autofocus="" required="" type="email" placeholder="Email address" >

required="" 是表单的必填项,删除后,就可以了
```

```html
<input class="form-control" id="inputEmail" autofocus="" required="" type="email" name="username" placeholder="Email address">
<input class="form-control" id="inputPassword" required="" type="password" name="password" placeholder="Password">
设置name的键值对
```



- **关掉pycharm的校验请求功能** - **csrf 中间件**  

  ```python
  在settings.py中
  
  MIDDLEWARE = [
      'django.middleware.security.SecurityMiddleware',
      'django.contrib.sessions.middleware.SessionMiddleware',
      'django.middleware.common.CommonMiddleware',
      # 'django.middleware.csrf.CsrfViewMiddleware',
      'django.contrib.auth.middleware.AuthenticationMiddleware',
      'django.contrib.messages.middleware.MessageMiddleware',
      'django.middleware.clickjacking.XFrameOptionsMiddleware',
  ]
  
  ```

- **禁用前端校验**

  ```html
  form表单中添加 novalidate
  <form class="form-signin" action = "" method="post" novalidate>
  ```

  

- `urls.py` **中校验请求(用户名密码校验)**

  ```python
  from django.shortcuts import HttpResponse, render, redirect
  
  
  def index(request):
      # 业务逻辑
      return HttpResponse('欢迎进入红浪漫!')
  
  
  def home(request):
      return render(request, 'home.html')
  
  
  def login(request):
      if request.method == 'GET':
          # 返回登录页面
          return render(request, 'login.html')
      elif request.method == 'POST':
          # 获取提交的数据 request.POST
          username = request.POST.get('username')
          password = request.POST.get('password')
          # 对用户名和密码进行校验
          if username == 'alex' and password == 'alexdsb':
              # 校验成功 跳转到首页(重定向)
              # return HttpResponse('欢迎进入红浪漫!')
              return redirect('/index/')
          else:
              # 校验失败 重新登陆
              return render(request, 'login.html')
  
  ```

  ------
  
  

# 5. app

```
	我们在项目中的urls中配置路由，在templates 里写HTML文件，如果项目很大，路由很多，HTML文件很多，那么就需要在项目的内部与与项目同名的同级创建APP应用，在APP应用里可以写自己的urls和views 这样主路由中的路由可以映射到APP中的子路由，这个时候就像一个树的根部到树叶扩散。
```



**创建app**

```python
CMD创建 :
进入项目文件夹下,按住shift右键进入命令行 :
	python manage.py startapp  app名称

pycharm中 :
在Teminal命令行中键入命令 :
	python manage.py  startapp  app名称
   
利用pycharm中的tools工具创建 :
    1. 调出窗口 : tools → Run manage.py Task ... 
    2. 键入命令 : startapp app名
```

**注册app**	

```python
在settings中 :

INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'app01',  # 第一种方式
    'app01.apps.App01Config', # 第二种方式  推荐写法
]
```

**app下的目录解释**

```python
	admin.py   django admin 

​	apps.py  app的信息

​	models.py    模型  model  跟数据库有关

​	views.py   写函数(之前在urlspy中写的函数写在这里
```



**将`urls.py`中的函数转移到创建的`app`下的`views.py` :**

**views.py下的全面内容**

```python
from django.shortcuts import render,redirect,HttpResponse

def login(requset):
    if requset.method == 'GET':
        # 返回登录页面
        return render(requset,'login.html')
    elif requset.method == 'POST':
        # 获取提交的数据 (用户名和密码) 
        username = requset.POST.get('username')
        password = requset.POST.get('password')
        # 对用户名和密码进行校验
        if username == 'python' and password == '123':
            # 校验成功,跳转到设置页面(重定向)
            return redirect('http://donyz.s567.tw/')
        else:
            # 校验失败,重新登录
            return render(requset,'login.html')
```

**将`views.py`中的函数导入到`urls.py`中**

```python
urls.py文件下 :
    
from app01 import views  # 导入
urlpatterns = [
    url(r'^admin/', admin.site.urls),
    url(r'^login/', views.login),  # 引用
]
```

------



# 6. orm

```
	对象关系映射（Object Relational Mapping，简称ORM）是通过使用描述对象和数据库之间映射的元数据，将面向对象语言程序中的对象自动持久化到关系数据库中。本质上就是将数据从一种形式转换到另外一种形式。
	
	对应关系
	 类  -- 表
	对象 -- 数据行
	属性 -- 字段
* orm可以操作表,操作数据行
```

## 6.1. 配置数据库

- **1. CMD命令行创建数据库 : **  `create database Day54`

- **2. `settings.py`的配置**

  ```python
  # settings.py下 :
  DATABASES = {
      'default': {
          'ENGINE' : 'django.db.backends.mysql',	# 数据库类型
          'NAME' : 'Day54',	# 数据库名
          'HOST' : '127.0.0.1',	 # IP地址
          'PORT' : 3306,	# 数据库的端口
          'USER' : 'root'	# 数据库用户名
          'PASSWORD' : '2108'	# 密码
      }
  }
  ```

- **3. 使用`pymysql`模块连接mysql数据库 (`__init__.py`)**

  ```python
  在项目同名的文件夹下的__init__.py中 :  下面这两行代码也可以不在__init__.py中,只要能运行就可以
  	# 导入pymysql模块
  	import pymysql	
  	# 用pymysql模块替换掉mysqldb模块  因为默认使用的是mysldb模块,此模块仅支持python2,
  	pymysql.install_as_MySQLdb()	
     
  ```

- **4. 写`pymysql`模块与数据库的对应关系  **

  ```python
  在app下的models.py中写表结构 :
  from django.db import models
  class User(models.Model):   # 创建类,继承Model类的功能
      username = models.CharField(max_length=32) # 数据库中表的字段 类型为varchar(32)
      password = models.CharField(max_length=32) # 数据库中表的字段 类型为varchar(32)
  ```

- **5. 执行创数据库迁移的命令**

  ```python
  pycharm的Teminal命令窗口下 :
  python manage.py  makemigrations  # 记录下models.py的变更记录并更新到 migrations 文件夹下的	             							001_inittal.py文件中
  python manage.py migrate   # 把变更记录同步到数据库中  这样上面的数据库表结构就写入数据库了 
  ```

- **6. 利用`pycharm`查看数据库**

  - **最新版的pycharm在连接中遇到由于时区贰无法连接数据库的问题的解决办法  :**

    ```
    在连接数据库窗口: 
    	在数据库路径后加 ?serverTimezone=GMT  即可
    ```

  - **注意 :**

    ​	**在pycharm中修改数据库后需要提交,修改才会生效**

- **7. 利用数据库进行用户名密码校验**

  ```python
  from django.shortcuts import render,redirect
  
  from app01 import models # 导入models.py中的User等类
  
  def login(requset):
      if requset.method == 'GET':
          # 返回登录页面
          return render(requset,'login.html')
      elif requset.method == 'POST':
          # 获取提交的数据 (用户名和密码)
          user = requset.POST.get('username')
          pwd = requset.POST.get('password')
          # 对用户名和密码进行校验
          ret = models.User.objects.filter(username=user,password=pwd)
          #  filter - 过滤筛选  查不到为空(False)对象列表
         # ret = models.User.objects.get(username=user,password=pwd) 
         #  get - 找不到会报错,找到多个也会报错
          if ret:
              # 校验成功,跳转到设置页面(重定向)
              return redirect('http://donyz.s567.tw/')
          else:
              # 校验失败,重新登录
              return render(requset,'login.html')
  ```



------



# 7. 图书管理系统

出版社 | 图书 | 作者

## 7.1. 出版社的管理

- 展示
- 新增
- 删除
- 编辑

**具体流程**

### 7.11. 配置数据库

- **a. 命令行创建数据库 :**

  **`create database day55_bookmanager`**

- **b. 项目配置数据库 :**

  **`settings.py`下**

  ```python
  DATABASES = {
      'default': {
          'ENGINE': 'django.db.backends.mysql',
          'NAME': 'day55_bookmanager',
          'HOST': '127.0.0.1',
          "PORT": 3306,
          "USER": 'root',
          'PASSWORD': '2108'
      }
  }
  ```

- **c. 用pymysql替换MYSQLdb模块 :**

  **项目下 `__init.py`文件 :**

  ```python
  import pymysql
  pymysql.install_as_MySQLdb()
  ```

- **d. app下创建表结构 :**

  **`modes.py`文件下 :**

  ```python
  from django.db import models
  
  class Publisher(models.Model):
      #  AutoField -自增长类型，映射到数据库中是11位的整数，使用此字段时，必须传递primary_key=True，
      # 否则在生成迁移脚本文件时，就会报错
      pid = models.AutoField(primary_key=True)
      name = models.CharField(max_length=32)
      def __str__(self): # 帮助打印对象中具体的属性值
          return "{}{}".format(self.pid,self.name) 
  ```

- **e. 执行创数据库迁移的命令 :**

  ```python
  pycharm的Teminal命令窗口下 :
  1. python manage.py  makemigrations  
  # 记录下models.py的变更记录并更新到 migrations 文件夹下001_inittal.py文件中
  2. python manage.py migrate   
  # 把变更记录同步到数据库中  这样上面的数据库表结构就写入数据库了 
  ```

- **给表添加一些数据**

### 7.1.2 展示出版社页面

- **A.`urls.py` 写对应关系:**

  ```python
  from app01 import views
  
  urlpatterns = [
      url(r'^admin/', admin.site.urls),
      url(r'^publisher_list/', views.publisher_list),
  ]
  ```

  

- **B.`app`中`views.py`写业务逻辑 :**

  ```python
  from django.shortcuts import render
  from app01 import models
  def publisher_list(request):
      # 从数据库中查询所有的出版社
      all_pubilshers = models.Publisher.objects.all() # 获取数据库全部数据,返回的是一个对象列表
      # 返回一个页面
      return render(request,'publisher_list.html',{'xxx':all_pubilshers})
      # xxx为自定义的key,在前端页面用固定格式 :{{xxx}} 可以引用xxxkey的值all_pubilshers
  ```

  

- **C.`publisher_list.html`图书管理网页**

  ```html
  <table border="1">
      <thead>  <!-- 表头 -->
      <tr>    <!-- 一行 -->
          <th>序号</th>
          <th>ID</th>
          <th>出版社名称</th>
      </tr>
      </thead>
      <tbody>  <!-- 主体内容 -->
          {% for publisher in xxx%} <!-- 循环语句  xxx为后端数据库的所有数据-->
              <tr>
              <td>{{ forloop.counter }}</td> <!--forloop.counter 为for循环次数计数 对应序号-->
              <td>{{ publisher.pid }}</td> <!--pid等同于pk (primarykey)-->
              <td>{{ publisher.name }}</td>
              </tr>
          {% endfor %} <!-- 闭合语句 -->
      </tbody>
  </table>
  ```

  

### 7.13. 新增数据 ( 新增出版社)

​	

- **数据库修改唯一 :**

  ```python
  from django.db import models
  
  class Publisher(models.Model):
      #  AutoField -自增长类型，映射到数据库中是11位的整数，使用此字段时，必须传递primary_key=True，
      # 否则在生成迁移脚本文件时，就会报错
      pid = models.AutoField(primary_key=True)
      name = models.CharField(max_length=32,unique=True) # 唯一
      def __str__(self): #帮助打印对象中具体的属性值
          return "{}{}".format(self.pid,self.name)
      
  执行创数据库迁移的命令 :
  pycharm的Teminal命令窗口下 :
  1. python manage.py  makemigrations  
  # 记录下models.py的变更记录并更新到 migrations 文件夹下001_inittal.py文件中
  2. python manage.py migrate   
  # 把变更记录同步到数据库中  这样上面的数据库表结构就写入数据库了 
  ```

  

- **提交新增图书页面**

  ```html
  <body>
  <form action="" method="post">
      <p>
          请输入新增出版社名称 : <input type="text" name="pub_name" value="{{ pub_name }}">
          <span style="color: red">{{ error }}</span>
      </p>
      <button>提交</button>
  </form>
  </body>
  ```

- **展示页面**

  ```html
  <body>
  <table border="1">
      <thead>  <!-- 表头 -->
      <tr>    <!-- 一行 -->
          <th>序号</th>
          <th>ID</th>
          <th>出版社名称</th>
      </tr>
      </thead>
      <tbody>  <!-- 主体内容 -->
          {% for publisher in xxx%} <!-- 循环语句  xxx为后端数据库的所有数据-->
              <tr>
              <td>{{ forloop.counter }}</td> <!--forloop.counter 为for循环次数计数 对应序号-->
              <td>{{ publisher.pid }}</td> <!--pid等同于pk (primarykey)-->
              <td>{{ publisher.name }}</td>
              </tr>
          {% endfor %} <!-- 闭合语句 -->
      </tbody>
  </table>
  <a href="/publisher_add/"><button>添加</button></a>	<!--<a href="/" ></a> 表示链接到网站根目录.
  <a href="/porducts/" ></a> 表示链接到根目录下的products目录.-->
  </body>
  ```

- **`app`中`views.py`写业务逻辑**

  ```python
  def publisher_add(requset):
      pub_name,error = '', ''
      if requset.method == "POST":
          # 获取用户提交的信息 (出版社名字)
          pub_name = requset.POST.get('pub_name')
          if not pub_name:
              # 输入为空
              error = "输入不能为空"
          elif models.Publisher.objects.filter(name=pub_name):
              # 数据已经存在
              error = "数据已经存在"
          else:
              # 用户输入正确,数据写入数据库
              # 方式一 :
              models.Publisher.objects.create(name=pub_name)
              # 方式二 :
              # obj = models.Publisher(name = pub_name) # 在内存中实例化对象
              # obj.save()
              # 跳转到展示页面
              return redirect('/publisher_list/')
      return render(requset,'publisher_add.html',{'pub_name':pub_name,'error':error})
  ```

- **`urls.py` 写对应关系**

  ```python
  from app01 import views
  
  urlpatterns = [
      url(r'^admin/', admin.site.urls),
      url(r'^publisher_list/', views.publisher_list),
      url(r'^publisher_add/', views.publisher_add),
  ]
  ```

  

### 7.14. 删除数据 (删除出版社)

- **在之前基础上需要修改的**

  - **展示界面添加操作相关按钮**

    ```html
    <body>
    <table border="1">
        <thead>  <!-- 表头 -->
        <tr>    <!-- 一行 -->
            <th>序号</th>
            <th>ID</th>
            <th>出版社名称</th>
            <th>操作</th>
        </tr>
        </thead>
        <tbody>  <!-- 主体内容 -->
            {% for publisher in xxx%} <!-- 循环语句  xxx为后端数据库的所有数据-->
                <tr>
                <td>{{ forloop.counter }}</td> <!--forloop.counter 为for循环次数计数 对应序号-->
                <td>{{ publisher.pid }}</td> <!--pid等同于pk (primarykey)-->
                <td>{{ publisher.name }}</td>
                <td><a href="/publisher_del/?pk={{ publisher.pk }}"><button>删除</button></a></td>
                </tr>
            {% endfor %} <!-- 闭合语句 -->
        </tbody>
    </table>
    <a href="/publisher_add/"><button>添加</button></a>
    </body>
    ```

    

- **`urls.py`写对应关系**

  ```python
  from app01 import views
  
  urlpatterns = [
      url(r'^admin/', admin.site.urls),
      url(r'^publisher_list/', views.publisher_list),
      url(r'^publisher_add/', views.publisher_add),
      url(r'^publisher_del/', views.publisher_del),
  ]
  ```

  

- **`views.py`增加定义函数,写业务逻辑代码**

  ```python
  # 删除数据
  def publisher_del(request):
      # 利用get请求拿到要删除的数据id
      pk = request.GET.get('pk')
      # 验证要删除的数据是否存在
      query = models.Publisher.objects.filter(pid=pk)
      if not query :
          # 数据不存在返回一个字符串
          return HttpResponse('要删除的数据不存在')
      # 通过queryset删除查到的所有数据
      # 删除方式一 :
      query.delete()
      # # 删除方式二 删除一个对象:
      # query[0].delete()
      # 跳转到展示页面
      return redirect('/publisher_list/')
  ```

  

### 7.15. 编辑数据 (编辑出版社)

- **编辑页面**

  ```html
  <body>
  <form action="" method="post">
      <p>
          请输入编辑出版社的新名称 : <input type="text" name="pub_name" value="{{ obj.name }}">
          <span style="color: red">{{ error }}</span>
      </p>
      <button>提交</button>
  </form>
  </body>
  ```

  

- **展示界面添加操作相关按钮**

  ```html
  <body>
  <table border="1">
      <thead>  <!-- 表头 -->
      <tr>    <!-- 一行 -->
          <th>序号</th>
          <th>ID</th>
          <th>出版社名称</th>
          <th>操作</th>
      </tr>
      </thead>
      <tbody>  <!-- 主体内容 -->
          {% for publisher in xxx%} <!-- 循环语句  xxx为后端数据库的所有数据-->
              <tr>
              <td>{{ forloop.counter }}</td> <!--forloop.counter 为for循环次数计数 对应序号-->
              <td>{{ publisher.pid }}</td> <!--pid等同于pk (primarykey)-->
              <td>{{ publisher.name }}</td>
              <td><a href="/publisher_del/?pk={{ publisher.pk }}"><button>删除</button></a>
                  <a href="/publisher_edit/?pk={{ publisher.pk }}"><button>编辑</button></a>
              </td>
              </tr>
          {% endfor %} <!-- 闭合语句 -->
      </tbody>
  </table>
  <a href="/publisher_add/"><button>添加</button></a>
  </body>
  ```

- **`urls.py`写对应关系**

  ```python
  from app01 import views
  
  urlpatterns = [
      url(r'^admin/', admin.site.urls),
      url(r'^publisher_list/', views.publisher_list),
      url(r'^publisher_add/', views.publisher_add),
      url(r'^publisher_del/', views.publisher_del),
      url(r'^publisher_edit/', views.publisher_edit),
  ]
  ```

  

- **`views.py`增加定义函数,写业务逻辑代码**

  ```python
  # 编辑数据
  def publisher_edit(request):
      error = ''
      # 获取要查询的ID
      pk = request.GET.get('pk')
      # 查询要编辑的对象
      obj = models.Publisher.objects.filter(pk =pk).first()  # 获取对象列表的第一个对象
      if not obj:
          return HttpResponse('要编辑的对象不存在')
      if request.method == "POST":
          # 获取新提交的数据
          pub_name = request.POST.get('pub_name')
  
          if not pub_name:
              # 输入为空
              error = "输入不能为空"
          elif models.Publisher.objects.filter(name=pub_name):
              # 数据已经存在
              error = "数据已经存在"
          else:
              # 编辑原始数据
              obj.name = pub_name
              obj.save()
              # 跳转到展示页面
              return redirect('/publisher_list/')
      return render(request,'publisher_edit.html',{'obj':obj,'error':error})
  ```

  ​	
  
  ------
  
  

# 8. 外键

## 8.1. get 和 post的区别

```python
get :

发get请求的方式：
1. form表单     不指定method
2. 在地址栏中直接输入地址 回车
3. a标题 
？k1=v1&k2=v2      request.GET     request.GET.get('k1')

post :

form表单     method='post'	
request.POST     request.POST.get('k1')
```

## 8.2. orm - 表操作

```python
面向对象和关系型数据库的一种映射

对应关系：
​	类     ——》    表
​	对象  ——》    记录 （数据行）
​	属性  ——》    字段

from app import  models

查询：

​	models.Publisher.objects.get(name='xxxxx')       # 查询一个对象  有且唯一   差不多或者多个就报错
​	models.Publisher.objects.filter(name='xxxxx')      # 查询满足条件所有对象     对象列表  queryset  

​	models.Publisher.objects.all()   # 查询所有的数据  对象列表  queryset  

新增：
​	models.Publisher.objects.create(name='xxxxx')   # 返回值 就是新建的对象
​	obj = models.Publisher(name='xxxxx')     obj.save()

删除：
​	models.Publisher.objects.filter(pk=1) .delete() 
​	obj = models.Publisher.objects.filter(pk=1) .first()   obj.delete()

修改：
​	obj = models.Publisher.objects.filter(pk=1) .first()
​	obj.name =  'xxxxx'
​	obj.save()
```

## 8.3 外键 的设置

**一对多的对应关系**  - **外键创建在多的一方**

```python
class Book(models.Model):
    title = models.CharField(max_length=32)
    pid = models.ForeignKey('Publisher', on_delete=models.CASCADE)
    # 外键  Publisher为对应关联的表
    #  on_delete  django2.0中 必填 
```

**on_delete参数的各个值的含义:**

```python
1. on_delete=None,               # 删除关联表中的数据时,当前表与其关联的field的行为
2. on_delete=models.CASCADE,     # 删除关联数据,与之关联也删除 - 级联删除
3. on_delete=models.DO_NOTHING,  # 删除关联数据,什么也不做
4. on_delete=models.PROTECT,     # 删除关联数据,引发错误ProtectedError

models.ForeignKey('关联表', on_delete=models.SET_NULL, blank=True, null=True)

5. on_delete=models.SET_NULL,
# 删除关联数据,与之关联的值设置为null（前提FK字段需要设置为可空,一对一同理）

models.ForeignKey('关联表', on_delete=models.SET_DEFAULT, default='默认值')

6. on_delete=models.SET_DEFAULT,
# 删除关联数据,与之关联的值设置为默认值（前提FK字段需要设置默认值,一对一同理）

7. on_delete=models.SET,         # 删除关联数据,
 a. 与之关联的值设置为指定值,设置：models.SET(值)
 b. 与之关联的值设置为可执行对象的返回值,设置：models.SET(可执行对象)
```

**查询：**

```python
all_books = models.Book.objects.all()
print(all_books)
for book in all_books:
    print(book)
    print(book.pk)
    print(book.title)
    print(book.pub,type(book.pub))  # book.pub为所关联的对象
    print(book.pub_id,type(book.pub_id))  # 所关联的对象的pk
```

**新增 :**

```python
models.Book.objects.create(title=title,pub=models.Publisher.objects.get(pk=pub_id))
models.Book.objects.create(title=title, pub_id=pub_id)
```



**删除 :**

```python
pk = request.GET.get('pk')
models.Book.objects.filter(pk=pk).delete()
```

**编辑 :**

```python
book_obj.title = title
book_obj.pub_id = pub_id
# book_obj.pub = models.Publisher.objects.get(pk=pub_id)
book_obj.save()
```

------



# 9. 多对多表结构设计

## 表结构的设计

```python
class Book(models.Model):
    title = models.CharField(max_length=32)
    pid = models.ForeignKey('Publisher',on_delete=models.CASCADE)

class Author(models.Model):
    name = models.CharField(max_length=32)
    book = models.ManyToManyField('Book') # 描述多对的关系 不生成此字段,而是生成Author-Book的关系表
```

## 查表

```python
all_authors = models.Author.objects.all().order_by('id')
for author in all_authors:
    print(author.name)
    print(author.pk)
    print(author.books)  # 关系管理对象
    print(author.books.all())  # 所关联的所有对象
```

```python
models.py :
class Book(models.Model):
    title = models.CharField(max_length=32)
    pid = models.ForeignKey('Publisher',on_delete=models.CASCADE)
    def __repr__(self):
        return self.title
    __str__ = __repr__

class Author(models.Model):
    name = models.CharField(max_length=32)
    book = models.ManyToManyField('Book') # 描述多对的关系 不生成此字段,而是生成Author-Book的关系表
```

```python
author.html页面 :
    <tr>
    <td>{{ forloop.counter }}</td>
    <td>{{ author.pk }}</td>
    <td>{{ author.name }}</td>
    <td>{% for book in author.book.all %}
        {{ book }}
    {% endfor %}</td>
```

```python
views.py 逻辑
def author_list(request):
    all_author = models.Author.objects.all()
    return render(request, 'author_list.html', {'all_author': all_author})
```

## 新增

```python
books = request.POST.getlist('books')   # 获取多个元素

# 新建作者
author_obj = models.Author.objects.create(name=name)
# 给作者和书籍绑定关系
author_obj.books.set(books) # 
```

**创建多对多的表的方法**

- django通过ManyToManyField自动创建第三张表

  ```python
  class Book(models.Model):
      title = models.CharField(max_length=32)
      pub = models.ForeignKey('Publisher', on_delete=models.CASCADE)
      # authors = models.ManyToManyField('Author')  # 描述多对多的关系   不生成字段  生成关系表
  
      def __repr__(self):
          return self.title
  
      __str__ = __repr__
  
  class Author(models.Model):
      name = models.CharField(max_length=32)
      books = models.ManyToManyField('Book')  # 描述多对多的关系   不生成字段  生成关系表
  ```

- 自己手动创建

  ```python
  class Book(models.Model):
      title = models.CharField(max_length=32)
  
  
  class Author(models.Model):
      name = models.CharField(max_length=32)
  
  
  class Book_Author(models.Model):
      book = models.ForeignKey(Book, on_delete=models.CASCADE)
      author = models.ForeignKey(Author, on_delete=models.CASCADE)
      date = models.DateField()
  ```

- 自己创建 + ManyToManyField

  ```python
  class Book(models.Model):
      title = models.CharField(max_length=32)
  
  
  class Author(models.Model):
      name = models.CharField(max_length=32)
      books = models.ManyToManyField(Book, through='Book_Author')
  
  
  class Book_Author(models.Model):
      book = models.ForeignKey(Book, on_delete=models.CASCADE)
      author = models.ForeignKey(Author, on_delete=models.CASCADE)
      date = models.DateField()
  ```

  

------

## 设计表结构

`nodels`

```python
<form class="form-inline" method="post">
    <div class="form-group">
        <input type="text" class="form-control" id="exampleInputEmail3" name="author_name"
                placeholder="{{ author_obj.name }}">
        <span style="color: crimson">{{ error }}</span>
        著作 :<select name="book_id" multiple>
        {% for book in all_books %}
            {% if book in author_obj.book.all %}
             <option selected value="{{ book.pk }}">{{ book.title }}</option>
                {% else %}
                  <option value="{{ book.pk }}">{{ book.title }}</option>
            {% endif %}
        {% endfor %}
    </select>
    </div>
    <button type="submit" class="btn btn-default">提交</button>
</form>
```



## 展示

`views`

```python
def author_list(request):
    all_author = models.Author.objects.all()
    return render(request, 'author_list.html', {'all_author': all_author})
```

`html`

```python
<table class="table table-striped table table-hover">
    <thead>
    <tr>
        <th>序号</th>
        <th>ID</th>
        <th>作者</th>
        <th>著作</th>
        <th>操作</th>
    </tr>
    </thead>
    <tbody>
    {% for author in all_author %}
        <tr>
            <td>{{ forloop.counter }}</td>
            <td>{{ author.pk }}</td>
            <td>{{ author.name }}</td>
            <td>{% for book in author.book.all %}
                《{{ book }}》
            {% endfor %}</td>
            <td><a href="/author_del/?pk={{ author.pk }}" class="btn btn-danger">删除</a>
                <a href="/author_edit/?pk={{ author.pk}}" class="btn btn-warning">编辑</a></td>
        </tr>
    {% endfor %}
    </tbody>
</table>
```





## 删除

`views`

```python
def author_del(request):
    pk = request.GET.get('pk')
    obj_author = models.Author.objects.filter(pk=pk)
    obj_author.delete()
    return redirect('/author_list/')
```





## 新增

`views`

```python
def author_add(request):
    error = ''
    if request.method == "POST":
        author_name = request.POST.get('author_name')
        book = request.POST.getlist('list_book')
        if not author_name or not book:
            error = '输入或选择不能为空!'
        elif models.Author.objects.filter(name=author_name):
            error = '作者已存在!'
        else:
            author_obj = models.Author.objects.create(name=author_name)
            author_obj.book.set(book)
            return redirect('/author_list/')
    all_books = models.Book.objects.all()
    return render(request, 'author_add.html', {'all_books': all_books, 'error': error})
```

`html`

```python
<form class="form-inline" method="post">
    <div class="form-group">
        <input type="text" class="form-control" id="exampleInputEmail3" name="author_name"
               placeholder="请填写作者">
        <span style="color: crimson">{{ error }}</span>
            著作:
            <select name="list_book"  multiple>
                {% for book in all_books %}
                    <option value="{{ book.pk }}">{{ book.title }}</option>
                {% endfor %}
            </select>
    </div>
    <button type="submit" class="btn btn-default">提交</button>
</form>
```



## 编辑

`views`

```python
def author_edit(request):
    error = ''
    pk = request.GET.get('pk')
    author_obj = models.Author.objects.filter(pk=pk).first()
    if not models.Author.objects.filter(pk=pk):
        return HttpResponse('数据不合法!')
    if request.method == "POST":
        author_name = request.POST.get('author_name')
        book_id = request.POST.getlist('book_id')
        if not author_name or not book_id:
            error = '输入或选择不能为空'
        elif models.Author.objects.filter(name=author_name):
            error = '作者已存在!'
        else:
            author_obj.name = author_name
            author_obj.save()
            author_obj.book.set(book_id)
            return redirect('/author_list/')
    all_books = models.Book.objects.all()
    return render(request, 'author_edit.html', {'all_books': all_books, 'error': error, 'author_obj': author_obj})
```

`html`

```python
<form class="form-inline" method="post">
    <div class="form-group">
        <input type="text" class="form-control" id="exampleInputEmail3" name="author_name"
                placeholder="{{ author_obj.name }}">
        <span style="color: crimson">{{ error }}</span>
        著作 :<select name="book_id" multiple>
        {% for book in all_books %}
            {% if book in author_obj.book.all %}
             <option selected value="{{ book.pk }}">{{ book.title }}</option>
                {% else %}
                  <option value="{{ book.pk }}">{{ book.title }}</option>
            {% endif %}
        {% endfor %}
    </select>
    </div>
    <button type="submit" class="btn btn-default">提交</button>
</form>
```

------



# 10. MVC和MTV框架

### MVC

```python
	MVC全名是Model View Controller，是模型(model)－视图(view)－控制器(controller)的缩写，一种软件设计典范，用一种业务逻辑、数据、界面显示分离的方法组织代码，将业务逻辑聚集到一个部件里面，在改进和个性化定制界面及用户交互的同时，不需要重新编写业务逻辑。具有耦合性低、重用性高、生命周期成本低等优点。
```

#### 结构

```python
1. Model (模型): 
    核心的"数据层"（Model），也就是程序需要操作的数据或信息。
2. View (视图): 
    直接面向最终用户的"视图层"（View）。它是提供给用户的操作界面，是程序的外壳。
3. Controller (控制层) : 
    是"控制层"（Controller），它负责根据用户从"视图层"输入的指令，选取"数据层"中的数据，然后对其进行相应的操作，产生最终结果。
```

### MTV

**MTV** 是Django定义的一种开发规范

#### 结构

```python
Model(模型)：负责业务对象与数据库的对象(ORM)
Template(模版)：负责如何把页面展示给用户
View(视图)：负责业务逻辑，并在适当的时候调用Model和Template
```

------



# 11. Django模板系统

### 常用语法

```python
{{  }}和 {% %}
{{ }}表示变量，在模板渲染的时候替换成值，{% %}表示逻辑相关的操作。
```

```python
{{ 变量名 }}
变量名由字母数字和下划线组成。
点（.）在模板语言中有特殊的含义，用来获取对象的相应属性值。
```

```python
views.py中的数据:
    context = {
        "filter_list": ['西游记', '水浒传', '红楼梦', '三国演义'],
        "filter_dict": {
            'name': "小猪佩奇",
            'age': 3,
            'hobby': "睡觉"
        }
    }
前端页面操作 :
# 取filter_list中的第一个参数
{{ filter_list.0 }} # 西游记

# 取字典中key的值 
{{ filter_dict.name }} # 小猪佩奇
{# 取对象的name属性 #}
{{ person_list.name }}
{# .操作只能调用不带参数的方法 #}
{{ person_list.dream }}
```

```python
注：当模板系统遇到一个（.）时，会按照如下的顺序去查询：
	1. 在字典中查询
	2. 属性或者方法
	3. 数字索引
```

### filters - 过滤器

**filters - 用来修饰变量的显示结果**

```python
语法： {{ value|filter_name:参数 }}
':'左右没有空格没有空格没有空格
```

#### **default**　　

```python
{{ value|default:"nothing"}}

如果value值没传的话就显示nothing
注：TEMPLATES的OPTIONS可以增加一个选项：string_if_invalid：'找不到'，可以替代default的的作用
```

#### filesizeformat

将值格式化为一个 “人类可读的” 文件尺寸 （例如 '13 KB', '4.1 MB', '102 bytes', 等等）。

`{{ value|filesizeformat }}`

#### add

给前端变量加参数

`{{ value|add:"2" }}` 

`{{ first|add:second }}` 如果first、second都是列表

如first=`[1,2,3]`,second = `[4,5,6]`, 那么结果是两个列表的合并 :`[1,2,3,4,5,6]`

#### lower/upper - 大小写 

`{{ value|lower }}`   `{{ value|upper}}`

#### title  -标题

`{{ value|title }}`

#### length

`{{ value|length }}`  - 返回的是value的长度

#### slice - 切片

`{{value|slice:"2:-1"}}`

#### first/last -取 第一个/最后一个

`{{ value|first }}`  `{{ value|last }}`

#### join - 拼接字符串

使用字符串拼接列表。同python的str.join(list)。 `{{ value|join:" // " }}`

#### truncatechars - 截断

truncatewords - 按照单词截断

如果字符串字符多于指定的字符数量，那么会被截断。截断的字符串将以可翻译的省略号序列（“...”）结尾。

参数：截断的字符数	`{{ value|truncatechars:9}}`

#### date  -日期

日期格式化	`{{ value|date:"Y-m-d H:i:s"}}`

```python
views.py中
import datetime
context{
	'now':datetime.datetime.now(),
}
{{ now|date:"Y-m-d H:i:s"}}

```

```python
settings的配置：
USE_L10N = False
DATETIME_FORMAT = 'Y-m-d H:i:s'
DATE_FORMAT = 'Y-m-d'
TIME_FORMAT = 'H:i:s'

```

#### safe

**在前后端传输变量数据的时候,前端引用的后端的可能是一串前端代码,在默认的情况下,为了安全,前端会转义成字符串, 如果想要运行这串引用的代码,就需要加safe	`{{ value|safe}}**`

**在py后台中先解除不安全**

```python
from django.utils.safestring import mark_safe	# 导入模块

'a':mark_safe('<a href="http://www.baidu.com">跳转</a>')	# 定义数据的时候用mark_safe(数据)

```

### 自定义过滤器

#### 步骤  :

```python
1. 在app下创建名字必须为 templatetags 的python包
2. 在templatetags包内创建python文件 :
    from django import template # 导入模板
    register = template.Library() # register 为固定写法,不能变
    # 写过滤器
    @register.filter  # 必须加装饰器
    def 过滤器名(value,arg=None): # 至多可以接收两个参数,一个是value变量,一个是过滤器的参数(:后面的参数)
        return value.upper() # 变成大写
    
 3. 前端页面写法 
	{% load python文件 %} # 加载过滤器
    {{ value|过滤器名 }}

```

------



# 12. Tags - 标签

## for -循环

```html
<ul>
{% for user in user_list %}
    <li>{{ user.name }}</li>
{% endfor %}
</ul>
```

### for...empty

```html
<ul>
{% for user in user_list %}
    <li>{{ user.name }}</li>
{% empty %}
    <li>空的数据</li>
{% endfor %}
</ul>
<!--若for循环取不到值,则会执行empty中的内容-->
```

### 取余数

```html
{% num|divisibleby:2 %}  <!-- 对num取2的余数-->
```

## if,elif和lese

```html
{% if age<18 %}
  未成年
{% elif age<30 %}
  青年人
{% else %}
  中年人
{% endif %}
```



**if语句支持 and 、or、==、>、<、!=、<=、>=、in、not in、is、is not判断  **

**且 if 不支持算数运算、不支持连续判断**



## with

**定义中间变量 , 给变量起别名**

```html
方式一 :
{% with 旧名字 as 新的名字 %}
这里就可以引用新的名字
{% endwith %}

方式二 :
{% with 新的名字=旧名字  %}
这里就可以引用新的名字
{% endwith %}
```

## csrf_token

**这个标签用于跨站请求伪造保护。**

**在页面的form表单里面写上 `{% csrf_token %}`**

```html
<form action='' method="POST">
    {% csrf_token% }
    <input type="text" class="" name='name'>
    <button>提交</button>
</form>
```



------

# 13. 模板和继承

### **写模板**

下面的表格模拟html模板 ( 假设这个页面叫 " 模板.html " )

| 固定页面 | 固定页面                                                     |
| -------- | ------------------------------------------------------------ |
| 固定页面 | '' 需要替换的页面 ''<br /><br />content 为这个模块的名称<br />content{% block content %}<br /><br />{% endblock %} |

### 继承使用模板

```html
{ % extends '模板.html'%}	<!-- 导入模板-->

{ % block 模块名% }	<!-- 这里的模块么要和模板的模块名一致-->

这里写自己的内容

{ % endblock% }
```



**如果子页面要单独用一个样式css 或js,**

**那么就可以单独的使用block块引用,避免其他子页面的时候也加载了不必要的样式**



------



### 小组件

在主界面需要插入小组件的地方如 导航栏等 写入代码`{%include '组件名.html%}`

组件名.html 中,不需要head,body等,可以直接写代码





------



# 14. 静态文件别名

**动态获取static别名**

**方式一 :**

```html
{% load stati %}	加载动态static别名
<!--这样无论配置中的static别名设置成什么,都可以用static动态获取到 -->
<!--引用文件直接在{%staticc 'css/xxcss' %} -->
例 :
<link rel="stylesheet" href="{% static 'css/dashboard.css' %}">
```

**方式二 :**

```html
{% load stati %}
<!--获取动态文件前缀 { % get_static_prefix %}  - 找到动态文件别名-->
例 :
<link rel="stylesheet" href="{% get_static_prefix %}css/cssyangs.css">
```

------

# 15. 自定义simpletag

```python
在templatetags中的py文件中
from django import template
register = template.Library() 
        
@register.simple_tag
def join_str(*args, **kwargs):
    return '_'join(args) + "*".join(kwargs.values())

前端页面引用 :
{% load my_tags %}  # my_tags 为 emplatetags 的py文件
{% join_str 'v1' 'v2' k3='k3' k4='v4' %}  # 结果 : v1_v2k3*k4
```

------



# 16. 自定义inclusion_tag

## 分页

1. 在app中创建名字为`templatetags`的python包

2. 在templatetags中出创建python文件my_tags.py

3. 在创建的python中写自定义函数

   ```python
   from django import template
   register = template.Library() 
   
   @register.inclusion_tag('html模板.html')
   def page(num):
       return {'num':range(1,num+1)}	# 返回的必须是个字典 会把num传到html模板.html
   ```

4. html模板,写分页模板

   ```html
   <nav aria-label="Page navigation">
     <ul class="pagination">
       <li>
         <a href="#" aria-label="Previous">
           <span aria-hidden="true">&laquo;</span>
         </a>
       </li>
       {% for i in num %}
         <li><a href="#">{{i}}</a></li>
         {% endfor %}
       <li>
         <a href="#" aria-label="Next">
           <span aria-hidden="true">&raquo;</span>
         </a>
       </li>
     </ul>
   </nav>
   ```

5. 在需要分页的页面导入分页小组件

   ```html
   {% load my_tags %} # 加载自定义模块my_tags
   {% page 5 %}	# 会把5这个参数传回到函数中,表示的是分5页
   ```

   

------



# 17. 三种自定义函数+装饰器

```python
1.
@register.filter
def add_arg(value,arg):
   return  "{}_{}".format(value,arg) 
前端页面写法 :
	{% load python文件 %} # 加载过滤器
    {{ value|过滤器名 }}
    
2.
@register.simple_tag
def join_str(*args, **kwargs):
    return '_'.join(args) + "*".join(kwargs.values())
前端页面引用 :
{% load my_tags %}  # my_tags 为 emplatetags 的py文件
{% join_str 'v1' 'v2' k3='k3' k4='v4' %}  # 结果 : v1_v2k3*k4

3.
@register.inclusion_tag('page.html')
def page(num):
    return {'num':range(1,num+1)}
前端页面写法 :
{% load my_tags %} # 加载自定义模块my_tags
{% page 5 %}
```

------

# 18. Django的view视图

一个视图函数(类), 简称视图, 是一个简单的python函数(类),它接收web请求并且返回Web响应.，响应可以是一张网页的HTML内容，一个重定向，一个404错误，一个XML文档，或者一张图片。

## FBV 和CBV

**FBV - function based view ：基于函数的view**

**CBV - class based view ：基于类的view**

**定义CBV :**

**在`views.py`中**

```python
from django.views import View # 继承Django的类
class AddPublisher(View): # 自定义一个类
    def get(self.request): # get函数为固定写法，表示处理GET请求
        # 处理get请求
        return render（request, 'index.html'
    def post(self,request):
        ...
```

**在 `urls.py`中写对应关系**

```python
from django import models
urlpatterns = [
    url(r'^publisher_add/', views.AddPublisher.as_view()),
]
```



## CBV流程

1. 项目启动时，运行urls.py。

   url(r'^publisher_add/',views.AddPublisher.as_view() ),
   AddPublisher.as_view() 执行  ——》   view函数

2. 请求到来时，实行view函数：

   1. 实例化AddPublisher  ——》  self 

   2. self.request = request  

   3. 执行View中self.dispatch(request, *args, **kwargs)

      1. 判断请求方式是否被允许

         1. 允许

            通过反射获取请求方式对应的方法   ——》 handler

         2. 不允许

            self.http_method_not_allowed  ——》 handler

      2. 执行handler 获取到响应

## 视图加装饰器

### 1.  定义允许访问的请求方式

```python
from django.views import View # 继承Django的类
class AddPublisher(View): # 自定义一个类
    
     # 定义允许访问的请求方式
     http_method_names = ['get', 'post', 'put', 'patch', 'delete', 'head', 'options', 'trace']
    
    def get(self.request,*args,**kwargs): # get函数为固定写法，表示处理GET请求
        # 处理get请求
        return render（request, 'index.html'
    def post(self,request,*args,**kwargs):
        ...
```

**视图加装饰器**

------

```python
views.py :
      
from django.shortcuts import render, HttpResponse, redirect
from app01 import models
import time

# 写一个装饰器
def timer(func):
    def inner(request, *args, **kwargs):
        start = time.time()
        print(func)
        print(args)
        ret = func(request, *args, **kwargs)
        print('{}'.format(time.time() - start))
        return ret
    return inner
```

### 2. FBV 视图加装饰器 :

**直接加**

```python
@timer
def publisher_list(request):
    ...
```



### 3. CBV 视图加装饰器 :

**加装饰器之前要导入模块 :**

```python
from django.utils.decorators import method_decorator
```

**1. 加在类下面的方法上 :**

```python
@method_decorator(timer)
def get(self, request):
    ...
```

**2. 加在dispath方法上 :**

`dispath`方法是父类的方法,下面的是重写`dispath`方法

```python
@method_decorator(timer)
def dispatch(self, request, *args, **kwargs):
    # start = time.time()
    ret = super().dispatch(request, *args, **kwargs)
    # print('{}'.format(time.time() - start))
    return ret
```

**3. 直接加在类上 :**

**需要指定类下面的哪个方法**

```python
@method_decorator(timer, name='dispatch') # 指定dispath方法
class AddPublisher(View):
    ...
    
@method_decorator(timer, name='post')
@method_decorator(timer, name='get')
class AddPublisher(View):
```

------

# 19. request对象



```python
request.method   获取请求方式  GET POST 
request.GET.get()    url上携带的参数  {}   
request.POST.get()   post请求提交的参数  {} 
request.path_info # 获取的是url的路径信息  不包含IP和端口 也不包含查询参数 /路径/
request.body   #  前端的请求体的具体数据  POST获取的数据 是从body中提取的

request.scheme  - http 或https
request.COOKIES   # cookie
request.session   # session 
request.FILES    # 上传的文件  
request.META   # 头的信息 {}


方法 :
request.get_full_path()   # 完整的路径信息 不包含IP和端口 包含查询参数
request.is_ajax()   # 判断是否是ajax请求
```



**上传文件** 

```python
views.py :
    class FileLoad(View):
    def get(self, request):
        return render(request, 'file_upload.html')
    def post(self, request):
        file_obj = request.FILES.get('file1')   # request.FILES 是一个字典
        with open(file_obj.name, 'wb')as f1:    # file_obj.name 是封装好的 获取的上传的文件的名字
            for file in file_obj.chunks():  # chunks() 是提供的一个方法,一段一段的取
                f1.write(file)
        return HttpResponse("OK")
```

```html
前端页面 :
<form action="" method="post" enctype="multipart/form-data">
    {% csrf_token %}
    <p>
        上传文件: <input type="file" name="file1">
    </p>
    <button>上传</button>
</form>
```

​	**`FILES`文件上传 需要注意的**

```python
1. FILES 只有在请求的方法为POST 且提交的<form> 带有enctype="multipart/form-data" 的情况下才会包含数据。否	则，FILES 将为一个空的类似于字典的对象
2. input  type='file'
3. request.FILES.get('file1')
4. {% csrf_token %}
```

------

# 20. response

```python
1. HttpResponse('字符串')   # 返回字符串
2. render(request,'模板的文件名'，{})    # 返回一个完整的页面
3. redirect（'/要跳转的地址/'）  # 重定向   响应头  Location：  url 
```



**JSON - 前后端自动  序列化→反序列化 :**

```python
from django.http.response import JsonResponse

return JsonResponse(data)
return JsonResponse(dict)   # 自动修改为 Content-type = 'application/json' 这样前端会自动反序列化
return JsonResponse(list,safe=False)  # 非字典类型的 要有个参数 safe = False
```



------



# 21. Django路由系统

**url基本格式 :**

```python
from django.conf.urls import url
from django.contrib import admin
from app01 import views
urlpatterns = [
     url(正则表达式, views视图，参数，别名),
]


url(r'^admin/$', admin.site.urls),
1. 从上到下匹配
2. 匹配到后就不再匹配
3. 根据第二点,要在后面加$ ,防止截胡
4. 开头不用加/ :
    Django配置文件settings.py默认没有APPEND_SLASH这个参数,默认是True
    作用是自动在网址结尾加 "/"
```

```python
from django.conf.urls import url
from app01 import views

urlpatterns = [
    url(r'^articles/2003/$', views.special_case_2003),
    url(r'^articles/([0-9]{4})/$', views.year_archive),
    url(r'^articles/([0-9]{4})/([0-9]{2})/$', views.month_archive),
    url(r'^articles/([0-9]{4})/([0-9]{2})/([0-9]+)/$', views.article_detail),
]

参数说明 :
正则表达式：一个正则表达式字符串
views视图：一个可调用对象，通常为一个视图函数
参数：可选的要传递给视图函数的默认参数（字典形式）
别名：一个可选的name参数
```

**Django 2.0版本中的路由系统的写法 :**

```python
from django.urls import path，re_path

urlpatterns = [
    path('articles/2003/', views.special_case_2003),
    path('articles/<int:year>/', views.year_archive),
    path('articles/<int:year>/<int:month>/', views.month_archive),
    path('articles/<int:year>/<int:month>/<slug:slug>/', views.article_detail),
]
2.0版本中re_path和1.11版本的url是一样的用法
```

`settings.py`下的`ROOT_URLCONF = 'book_manager.urls'`为配置`url`路由

`settings.py`下的`DEBUG = True`为调试模式,改成`False`网页报错就不会有大黄框了





## 21.1 **正则表达式 :**



| 字符        | 描述                                     |
| ----------- | ---------------------------------------- |
| .           | 匹配任意字符 ( 除了\n )                  |
| \d          | 匹配数字                                 |
| /D          | 匹配非数字                               |
| [0-9]{4}    | 匹配0-9的四位数                          |
| \s          | 匹配空白字符                             |
| \S          | 匹配非空白字符                           |
| \w          | 匹配单词字符 [a~z , A~Z,0~9]             |
| \W          | 匹配非单词字符                           |
| *           | 匹配前一个字符0次或者无限次              |
| +           | 匹配前一个字符1次或者无限次              |
| ?           | 匹配前一个字符0次或者一次                |
| {m} , {m,n} | 匹配前面一个字符m次或者n次               |
| ^           | 匹配字符串开头                           |
| $           | 匹配字符串结尾                           |
| \A \Z       | 指定的字符串匹配必须出现在在开头 /  结尾 |

## 21.2 . 分组命名匹配

### 21.2.1. 分组  - 位置参数

**正则表达式分组匹配（通过圆括号）捕获URL中的值并以位置参数形式传递给视图函数**

`urls.py :`

```python
url(r'^blog/([0-9]{4})/([0-9]{2})/$',views.blogs)
```

`views.py :`

```python
def blogs(request,year,month):
    ...
```



### 21.2.2. 命名分组  - 关键字参数   

- 在Python的正则表达式中，分组命名正则表达式组的语法是`(?P<name>pattern)`，其中`name`是组的名称，`pattern`是要匹配的模式
- 获的值作为关键字参数而不是位置参数传递给视图函数。

`urls.py :`

```python
url(r'^blog/(?p<year>[0-9]{4})/(?p<month>[0-9]{2})/$',views.blogs)
```

`views.py :`

```python
def blogs(request,year,month):  # 这里的参数必须是year,month
    ...
```

### 21.2.3. 捕获的参数永远都是字符串

每个在URLconf中捕获的参数都作为一个普通的Python字符串传递给视图，无论正则表达式使用的是什么匹配方式。例如，下面这行URLconf 中：

```
url(r'^articles/(?P<year>[0-9]{4})/$', views.year_archive),
```

传递到视图函数`views.year_archive()` 中的`year`参数永远是一个字符串类型

### 21.2.4. 视图函数中指定默认值

```python
# urls.py中
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^blog/$', views.page),
    url(r'^blog/page(?P<num>[0-9]+)/$', views.page),
]

# views.py中，可以为num指定默认值
def page(request, num="1"):
    pass
```

​		在上面的例子中，两个URL模式指向相同的view - views.page - 但是第一个模式并没有从URL中捕获任何东西。

​		如果第一个模式匹配上了，page()函数将使用其默认参数num=“1”,如果第二个模式匹配，page()将使用正则表达式捕获到的num值。

## 21.3. include其他的URLconfs

### 21.3.1. 路由分发

**在一个项目中可能存在多个应用，为了方便区分和管理，在项目的总路由urls.py中会进行路由分发 :**

**项目总路由`urls.py` :**

```python
from django.conf.urls import url,include
	url(r'^app01/',include('app01.urls')),
    url(r'^app02/',include('app02.urls')),
    ... 
```

**子应用中创建自己的分路由`urls.py`，进行URLConf配置 :**

```python
from django.conf.urls import  url
from app01 import views

urlpatters=[
	url(r'^blog/(?p<year>[0-9]{4})/(?p<month>[0-9]{2})/$',views.blogs),
    ...
]
```



### 21.3.2. 传递额外的参数给视图函数

**`django.conf.urls.url()` 可以接收一个可选的第三个参数，它是一个字典，表示想要传递给视图函数的额外关键字参数。**

```python
urls.py:
    
from django.conf.urls import url
from . import views

urlpatterns = [
    url(r'^blog/(?P<year>[0-9]{4})/$', views.func, {'foo': 'bar'}),
]

```

```python
viws.py

def func(request,*args,**kwargs):
    print(kwargs)  #  {'foo': 'bar'}
```

**注意 :**

​		**当传递额外参数的字典中的参数和URL中捕获值的命名关键字参数同名时，函数调用时将使用的是字典中的参数，而不是URL中捕获的参数**

## 21.4. 命名URL和URL反向解析

### 21.4.1. 静态路由

`urls.py :`

**给URL匹配规则起个名字，一个URL匹配模式起一个名字 :**

```python
urlpatterns = [
    url(r'^blog/', views.blog,name = 'blog'),
]
# 这样前后端配置好后,无论正则匹配blog怎样修改,前端页面代码地址都会相应改变,不会影响
```

**前端页面 :**

```html
<a href="{% url 'blog' %}">博客</a>
```

**后端`views.py`配置 :**

```python
from django.shortcuts import redirect,reversre 
from django.urls import reverse # reverse也可以这样导入,上下二选一
def blog(request):
    return redirect(reverse('blog'))
	# 由于redirect内部会尝试将 'blog' 当做url别名并自动反向解析
    return redirect('blog')
```



### 21.4.2. 动态路由 ( 分组 ) 

`urls.py :`

```python
urlpatterns = [
    url(r'blog/([0-9]{4})/([0-9]{2})/$',views.blog,name='blog')
```

**前端页面 :**

```html
<a href="{% url 'blog' '2019' '09' %}">博客</a>
```

**后端`views.py`配置 :**

```python
from django.shortcuts import redirect,reversre 

def blog(request):
    return redirect('blog', '2019', '09')
	# 另一写法
	return redirect(reverse('blog', args=('2019', '09'))	
    # 若args只有一个参数,注意参数后面加 逗号 ","
```

### 21.4.3. 命名分组动态路由

**传参方式变了  - 关键字参数 (也可位置参数传参)**

`urls.py :`

```python
url(r'^blog/(?p<year>[0-9]{4})/(?p<month>[0-9]{2})/$',views.blogs)
```

**前端页面 :**

```html
<a href="{% url 'blog' year='2019' month='9' %}">博客</a>
```

**后端`views.py`配置 :**

```python
def blog(request):
    return redirect(reverse('blog',kwargs={'year':'2019','month':'9'}))
```



### 24.4.4. 名称空间区分不同app下的相同名字

**不同的APP使用相同的URL名称，URL的命名空间模式也可以唯一反转命名的URL。**

**namespace :**

**主urls.py :**

```python
from django.conf.urls import include, url

urlpatterns = [
    url(r'^app01',include('app01.urls',namespace='app01')),
    url(r'^app02',include('app02.urls',namespace='app02')),
]
```

**前端页面 :**

```html
<a href = "{% url 'app01:blog' month = '9' year = '2019' %}">博客</a>
```

**views.py 下 :**

```python
def blog(request,*args,**kwargs):
    return render(request,revers('app01:index'))
```

------

# 22. ORM

​		 **对象关系映射（Object Relational Mapping，简称ORM）模式是一种为了解决面向对象与关系数据库存在的互不匹配的现象的技术。**

## 22.1. ORM常用字段

**settings.py配置 :**

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'day57_book_manager',
        'HOST': '127.0.0.1',
        'PORT': 3306,
        'USER': 'root',
        'PASSWORD': '2108'
    }
}
import pymysql
pymysql.install_as_MySQLdb()	# 告诉Django使用pymysql模块连接MySQL数据库:
```

**models.py 下创建表结构 :**

```python
from django.db import models
class Person(models.Model):
    pid = models.AutoField(primary_key=True)    # 自增主键
    name = models.CharField(max_length=32)  # varchar类型
    age = models.IntegerField() 	# 整数类型
    birth = models.DateTimeField(auto_now=True)  # 日期时间字段
```

**数据迁移 :**

```python
python manage.py makemigrations
python manage.py migrate
```





------

**pycharm中python Console窗口下创建数据 :**

```python
>>>from app01 import models
>>>models.Person.object.create(name='Tony',age=46)
```



## 22.2 常用字段 

[Django官网查询所有字段](https://docs.djangoproject.com/en/1.11/ref/models/fields/#field-types"Django官网")

| 字段          | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| AutoField     | 自增的整形字段，必填参数primary_key=True，则成为数据库的主键。无该字段时，django自动创建。一个model不能有两个AutoField字段。 |
| IntegerField  | 一个整数类型。数值的范围是 -2147483648 ~ 2147483647。        |
| CharField     | 字符类型，必须提供max_length参数。max_length表示字符的长度。 |
| TextField     | 存长字符串                                                   |
| DateField     | 日期类型，日期格式为YYYY-MM-DD，相当于Python中的datetime.date的实例<br />参数：<br />auto_now：每次修改时修改为当前日期时间。<br /> auto_now_add：新创建对象时自动添加当前日期时间。<br />auto_now和auto_now_add和default参数是互斥的，不能同时设置。 |
| DatetimeField | 日期时间字段，格式为YYYY-MM-DD HH:MM[:ss[.uuuuuu]][TZ]，相当于Python中的datetime.datetime的实例。 |
| BooleanField  | 布尔值                                                       |
| DecimalField  | 十进制小数<br />相关参数 ：<br />max_ digits=5 小数总长度<br />decimal_ p laces=2 小数位长度 |

## 22.3. 字段的参数 

DateField 日期

```python
null=True 数据库中该字段可以为空
blank=True Django中form表单可以为空
一般 null=True 和 blank=True 一起使用

db_column = 'username' 指定字段按在数据库中的名字()
default   默认值
unique  唯一索引
verbose_name   admin后台管理中显示的字段名称

choices=((True, '男'), (False, '女'))    可选择的参数
gender = models.BooleanField(default=True,choices = ((True,'男),(False,'女'))
```



## 22.4. 自定义字段

```python
class MyCharField(models.Field):
    """
    自定义的char类型的字段类
    """
    def __init__(self, max_length, *args, **kwargs):
        self.max_length = max_length
        super(MyCharField, self).__init__(max_length=max_length, *args, **kwargs)
 
    def db_type(self, connection):
        """
        限定生成数据库表的字段类型为char，长度为max_length指定的值
        """
        return 'char(%s)' % self.max_length
```



## 22.5. Model Meta参数

在类内定义类 [官网](https://docs.djangoproject.com/en/1.11/ref/models/options/#model-meta-options)

```python
class UserInfo(models.Model):
    nid = models.AutoField(primary_key=True)
    username = models.CharField(max_length=32)
 
    class Meta:
        # 数据库中生成的表名称 默认 app名称 + 下划线 + 类名
        db_table = "table_name"
 
        # admin中显示的表名称
        verbose_name = '个人信息'
 
        # verbose_name加s
        verbose_name_plural = '所有用户信息'
 
        # 联合索引 
        index_together = [
            ("pub_date", "deadline"),   # 应为两个存在的字段
        ]
 
        # 联合唯一索引
        unique_together = (("driver", "restaurant"),)   # 应为两个存在的字段
```



## 22.6. admin后台管理

1. 创建超级用户

   ```python
   python manage.py createsuperuser
   ```

2. admin后台管理改成中文

   ```python
   settings.py中
   LANGUAGE_CODE = 'en-us'  修改为 "zh_hans"	
   ```

3. 注册自己的数据库

   ```python
   app01.py下的admin.py文件中 :
   from app01 import models	# 导入models
   admin.site.register(models.Person)	# 注册自己的数据库
   ```

   

## 22.7. ORM操作

单文件执行操作数据库

```python
1. manage.py下复制这条语句
 os.environ.setdefault("DJANGO_SETTINGS_MODULE", "book_manager.settings")
2. 根目录下新建py文件 :
import os
os.environ.setdefault("DJANGO_SETTINGS_MODULE", "book_manager.settings")
import Django
Django.setup()
from app01 import models
ret = models.Person.object.all()
print(ret)
```

### 基本用法 :

#### 1. 返回queryset对象列表

| 函数          | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| all()         | 获取所有数据  返回的是对象列表                               |
|               | ret = models.Person.objects.all()                            |
| filter()      | 获取所有满足条件的数据  返回的是对象列表                     |
|               | ret = models.Person.objects.filter(pk=100                    |
| exclude()     | 排除满足条件的数据   返回的是对象列表                        |
|               | ret = models.Person.objects.exclude(pk=100)                  |
| values()      | 把所有对象以列表的形式返回,列表的每一个元素是个个对象的数据字典形式 |
|               | ret= models.Person.objects.all().values('pid','name')        |
| values_list() | 返回的是元组不是字典                                         |
|               | ret= models.Person.objects.all().values_list('name','pid',)  |
| order_by()    | 排序  默认升序   若要降序,在字段前加 "-"	order_by("-pid") |
|               | ret = models.Person.objects.all().order_by('age','-pid')     |
| reverse()     | 对已经排序的数据进行反转                                     |
|               | ret = models.Person.objects.all().order_by('age','-pid').reverse() |
| distinct()    | 去重                                                         |
|               | ret = models.Person.objects.values('age').distinct()         |

#### 2. 返回一个对象/布尔值/数字

| 函数       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| get()      | 获取一个满足条件的数据	返回的是一个对象 存在且唯一,查不到会报错 |
|            | ret = models.Person.objects.get(pk=1)                        |
| first()    | 返回第一个对象	拿不到返回None                             |
|            | ret = models.Person.objects.all().first()                    |
| last()     | 返回最后一个对象	拿不到返回None                           |
|            | ret = models.Person.objects.all().last()                     |
| 返回布尔值 |                                                              |
| exists()   | 存在就是Ture  不存在就是False                                |
|            | ret = models.Person.objects.filter(pk=100).exists()          |
| 返回数字   |                                                              |
| count()    | 计数                                                         |
|            | ret = models.Person.objects.all().count()                    |



## 22.8. 单表查询之神奇的双下划线

| 函数        | s说明                                                        |
| ----------- | ------------------------------------------------------------ |
| gt          | 获取pk大于1的数据	greater than                            |
|             | ret = models.Person.objects.filter(pk__gt=1)                 |
| lt          | 获取pk小于5的数据	less than                               |
|             | ret = models.Person.objects.filter(pk__lt=5)                 |
| gte         | 获取pk大于等于1的数据	greater than equal                  |
|             | ret = models.Person.objects.filter(pk__gte=1)                |
| lte         | 获取pk小于等于5的数据  less than  equal                      |
|             | ret = models.Person.objects.filter(pk__lte=5)                |
| range       | 获取pk1-5且包含1,包含5的数据                                 |
|             | ret = models.Person.objects.filter(pk__range=[1,5])          |
| in          | 获取pk中含有列表里的数据                                     |
|             | ret = models.Person.objects.filter(pk__in=[1,5,7,9])         |
| contains    | 获取name中包含alex字符串的数据                               |
|             | ret = models.Person.objects.filter(name__contains='alex')    # like |
| icontains   | 获取name中包含alex字符串的数据 忽略大小写                    |
|             | ret = models.Person.objects.filter(name__icontains='aLex')     # like ignore |
| startswith  | 以什么开头                                                   |
|             | ret = models.Person.objects.filter(name__startswith='a')    # 以什么开头 |
| istartswith | 以什么开头 ignore 忽略大小写                                 |
|             | ret = models.Person.objects.filter(name__istartswith='a')  # 以什么开头 gnore 忽略大小写 |
| endswith    | 以什么结尾                                                   |
|             | ret = models.Person.objects.filter(name__endswith='x')  # 以什么结尾 |
| iendswith   | 以什么结尾 ignore 忽略大小写                                 |
|             | ret = models.Person.objects. filter(name__iendswith='a')  # 以什么结尾 gnore 忽略大小写 |
| year        | 查年份   birth是字段名                                       |
|             | ret = models.Person.objects.filter(birth__year='2020')       |
|             | ret = models.Person.objects.filter(birth__contains='2020-10') |
| isnull      | 查为空的数据                                                 |
|             | ret = models.Person.objects.filter(age__isnull=False)        |

