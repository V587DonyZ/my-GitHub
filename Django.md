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

  

# 5. app

```
	我们在项目中的urls中配置路由，在templates 里写HTML文件，如果项目很大，路由很多，HTML文件很多，那么就需要在项目的内部与与项目同名的同级创建APP应用，在APP应用里可以写自己的urls和views 这样主路由中的路由可以映射到APP中的子路由，这个时候就像一个树的根部到树叶扩散。
```



**创建app**

```python
CMD创建 :
进入项目文件夹下,按住shift右键进入命令行 :
	python manage.py   startapp  app名称

pycharm中 :
在Teminal命令行中键入命令 :
	python manage.py   startapp  app名称
   
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



# 6. orm

```
	对象关系映射（Object Relational Mapping，简称ORM）是通过使用描述对象和数据库之间映射的元数据，将面向对象语言程序中的对象自动持久化到关系数据库中。本质上就是将数据从一种形式转换到另外一种形式。
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

  



