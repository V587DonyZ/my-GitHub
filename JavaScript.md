# JavaScript基础

## 1. 什么是JavaScript

```css
1. JavaScript是一种脚本语言，其源代码在发往客户端运行之前不需经过编译，而是将文本格式的字符代码发送给浏览器由    浏览器解释运行。
2. 是一种解释性脚本语言（代码不进行预编译）
```

## 2. JavaScript的组成

### 2.1 ECMAScript

```css
1. JavaScript的语法标准
2. ECMA是一个组织，即欧洲计算机制造商协会
3. ECMAScript是ECMA制定的脚本语言的标准, 规定了一种脚本语言实现应该包含的基本内容
4. JavaScript是脚本语言的一种,所以JavaScript也必须遵守ECMAScript标准,包含ECMAScript标准中规定的基本内容
```

### 2.2 DOM

**JavaScript操作网页上的元素的API**

**文档对象模型（DOM），描述处理网页内容的方法和接口。**

### 2.3. BOM

**JavaScript操作浏览器的部分功能的API**

**浏览器对象模型（BOM），描述与浏览器进行交互的方法和接口。**

## 3. JavaScript和HTML、CSS的关系

```
Html：是用来制作网页，简单来说就是编写网页结构
CSS： 美化网页（样式）
Javascript: 实现网页与客户之间互动的桥梁，让网页具有丰富的生命力
```

## 4. JS书写方式

### 4.1. 行内式

```js
方式一 :
<button onclick="alert('今天天气很好！');">今天天气?</button>
方式二 :
<a href="javascript:alert('你点疼我了！！');">点我</a>
```

### 4.2. 页内式

```js
</body>
      ......
     <script>
        alert("今天天气很好！");
     </script>
 </body>
```

```css
注意事项:
	1. 网页是从上至下加载, 而js代码通常是给标签添加交互(操作元素), 所以需要先加载HTML, 否则如果执行js代码时HTML还未被加载, 那么js代码将无法添加交互(操作元素);
	2. HTML页面中出现<script>标签后，就会让页面暂停等待脚本的解析和执行。无论当前脚本是内嵌式还是外链式，页面的下载和渲染都必须停下来等待脚本的执行完成才能继续。
```

### 4.3. 外链式

```js
<script src="xxx.js"></script>
```

```css
注意事项 :
	1. 外链式的script代码块中不能编写js代码, 即便写了也不会执行
	2. 由于每次加载外链式的js文件都会发送一次请求, 这样非常消耗性能, 所以在企业开发中推荐将多个JS文件打包成为一个JS文件,以提升网页的性能和加载速度。
```

## 5. 输出方式

### 5.1. alert

```js
控制浏览器弹出一个警告框 :  
	<script>
        alert("Hello, World!");
    </script>
```

### 5.2. write

```js
可以向body中输出一个内容:
	<script>
        document.write("Hello World!");
    </script>
```

### 5.3 . console.log

```js
向控制台输出一个内容 :
	<script>
	console.log("Hello World!");
	console.warn("警告输出！"); 
	console.error("错误输出！"); 
    </script>
```

### 5.4. prompt

```js
在网页中弹出输入框，一般用于接收用户输入的信息 :
	<script>
		prompt("Hello, World！"); 
    </script>
```

### 5.5.  comfirm

```js
在网页中弹出提示框，显示信息，该方法一般与if判断语句结合使用:
	<script>
	 comfirm("Hello，JavaScript！"); 
    </script>
```

## 6. JS 书写规范

```js
1. 编写Javascript注意语法规范，一行代码结束后必须在代码最后加上:
		如果不写分号，浏览器会自动添加，但是会消耗一些系统资源；此外，容易加错分号，所以在开发中分号必须要写。
2. 在JavaScript中是严格区分大小写的:
		comfirm("Hello，JavaScript！");   // 正确
		COMFIRM("Hello，JavaScript！");   // 错误 
3. JavaScript中会忽略多个空格和换行
		console.log( "Hello，JavaScript！" ); 
```

## 7. JS注释

```js
// 单行注释
 /*多行注释*/
```

## 8.数据类型 

### 定义变量

```js
var 变量名=值;
var a = 1
```

### 查看变量类型

```js
var 变量名
var (变量名)
typeof 变量名
```

### 1. 数字 - number

```
整数 var a = 1
小数 var b = 3.1415
保留(3位)小数 b.toFixede(3)  //3.152结果是字符串
数字和字符串显示的颜色不一样
```

### 2. boolean 布尔值

```
全部都是小写
ture : [] {} ...
false : undefined null NaN 0 '' 
```

### 3.  null 空和undefined未定义

```
null 表示空  boolean值为false
undefined 没有定义 创建变量但是不赋值 boolean值为false
```

### 4. 字符串 - string

```
var s1 = '单引号'
var s2 = "双引号"
```

#### string类型的常用方法

```js
1. 属性 : 长度 :
	var s1 = 'asdfg'
    s1.length	// 5
2. 去除字符串空格 - 不能修改源数据
	var s2 = '   asdfg     '
    s2.trim()	// "asdfg"
3. 拼接字符串
	s1.concat(s2,'哈哈')
4. 给出索引查找出相应字符
	s1.charAt(1) // "s"
5. 给出字符查找相应索引 (默认从左向右第一个)
	s1.indexOf('s')	// 1
6. 切片取值 - 顾头不顾尾 可以负数,没有步幅
	s1.slice(0,2)  // "as"
7. 全部大/小写
	s1.toUpperCase() // "ASDFG"
	s1.toLowerCase()
8. 切割
	s1.split('d')  // (2) ["as", "fg"]
	
	var s3 = 'a,b,c,d,e,f,g'
	s3.split(',',3) // (3) ["a", "b", "c"]  只取前三个
```

## 9. 数据类型转换

### 9.1. toString()

- **其它类型的数据转换为字符串类型**

```js
   var num = 12306;
   var str= num .toString();
   console.log(str); // 12306
   console.log(typeof str); // string

   var num1 = true;
   var str1 = num1.toString();
   console.log(str1 ); // true
   console.log(typeof str1 ); // string
```

- 注意:null和undefined没有toString()方法，如果强行调用,则会报错

````js
 var num2 = undefined;
 var str2 = num2.toString(); // 报错
 console.log(str2 );

 var num3 = null;
 var str3= num3.toString(); // 报错
 console.log(res4);

 var num4 = NaN;
 var str4 = num4.toString();
 console.log(str4); // NaN
 console.log(typeof str4); // String
````

- toString()不会影响到原变量，它会将转换的结果返回

```js
 var num5 = 10;
 var str5 = str5.toString();
 console.log(typeof num5 ); // number
 console.log(typeof str5 ); // string
```

### 9.2. String()函数

- 有的时候, 某些值并没有toString()方法，这个时候可以使用String()。比如：undefined和null
  - Number和Boolean的数据就是调用的toString()方法
  - 对于null和undefined，就不会调用toString()方法, 因为没有这个方法, 会在内部生成一个新的字符串
- +
  - 任何数据和 + 连接到一起都会转换为字符串, 其内部实现原理和String()函数一样

```js
   var num1 = 100;
   var res1 = num1 + "";
   console.log(res1); // 100
   console.log(typeof res1); // string

   var num2 = true;
   var res2 = num2 + "";
   console.log(res2); // true
   console.log(typeof res2); // string

   var num3 = undefined;
   var res3 = num3 + "";
   console.log(res3); // undefined
   console.log(typeof res3); // string

   var num4 = null;
   var res4 = num4 + "";
   console.log(res4); // null
   console.log(typeof res4); // string
```

### 9.3. Number()函数

- 字符串 转 数字

  - 如果是纯数字的字符串，则直接将其转换为数字

  ```js
  var str1 = "666";
  var res1 = Number(str1);
  console.log(res1); // 666
  console.log(typeof  res1); // number
  ```

  - 如果字符串中有非数字的内容，则转换为NaN

  ```js
  var str2 = "itlike123";
  var res2 = Number(str2);
  console.log(res2); // NaN
  ```

  - 如果字符串是一个空串或者是一个全是空格的字符串，则转换为0

  ```js
  var str3 = "";
  var res3 = Number(str3);
  console.log(res3); // 0
  
  var str4 = "    ";
  var res4 = Number(str4);
  console.log(res4); // 0
  ```

- undefined 转 数字

  ```js
  var str6 = undefined;
  var res8 = Number(str6);
  console.log(res8); // NaN
  ```

- null 转 数字

  ```js
  var str5 = null;
  var res7 = Number(str5);
  console.log(res7); // 0
  ```

- 布尔 转 数字   ( true 转成1 , false转成0 )

  ```js
     var bool1 = true;
    var res5 = Number(bool1);
    console.log(res5); // 1
  
    var bool2 = false;
    var res6 = Number(bool2);
    console.log(res6); // 0
  ```

## 9.4. parseInt()函数和parseFloat()函数

```js
	Number()函数中无论混合字符串是否存在有效整数都会返回NaN, 利用parseInt()/parseFloat()可以提取字符串中的有效整数
    parseInt()和parseFloat()的区别是前者只能提取整数,后者可以提取小数
```

```js
var str7 = "300px";
 var res9 = parseInt(str7);
 console.log(res9); // 300

 var str8 = "300px250";
 var res10 = parseInt(str8);
 console.log(res10); // 300
 console.log(parseInt("abc123"));  //返回NaN，如果第一个字符不是数字或者符号就返回NaN
console.log(parseInt(""));        //空字符串返回NaN，Number("")返回0 
```

## 10. js运算

### 10.1. 算数运算

```js
1. 加法运算
		格式:  Number1 + Number2
			var res = 1 + 1;
console.log(res); // 2

var num1 = 10;
var num2 = 20;
var res2 = num1 + num2;
console.log(res2); // 30
		非Number类型的值进行运算时，会将这些值转换为Number然后在运算
			var result = true + 1;
console.log(result); // 2
result = true + false;
console.log(result); // 1
result = 2 + null; 
console.log(result);// 2
		任何值和NaN做运算都得NaN
			var result = 1 + NaN;
console.log(result); //NaN
		任何的值和字符串做加法运算，都会先转换为字符串，然后再和字符串做拼串的操作
			var result = 10 + "123";
console.log(result); // 10123
result = 1 + "true";
console.log(result); // 1rue


2. 减法运算
		格式: Number1 - Number2
			var res = 1 - 1;
console.log(res); // 0

var num1 = 10;
var num2 = 20;
var res2 = num1 - num2;
console.log(res2); // -10
		非Number类型的值进行运算时，会将这些值转换为Number然后在运算
		任何值和NaN做运算都得NaN
		字符串做减法也会转换为Number
			var result = 2 - "1";
console.log(result); // 1
result = "2" - "1";
console.log(result); // 1


3. 乘法运算
		格式: Number1 * Number2
			var res = 2 * 2;
console.log(res); // 4

var num1 = 10;
var num2 = 20;
var res2 = num1 * num2;
console.log(res2); // 200
		其它规律和减法一样
			非Number类型的值进行运算时，会将这些值转换为Number然后在运算
			任何值和NaN做运算都得NaN
			字符串做乘法也会转换为Number
            
            
4. 除法运算
		格式: Number1 / Number2
			var res = 5 / 5;
console.log(res); // 1

var num1 = 100;
var num2 = 200;
var res2 = num1 / num2;
console.log(res2); // 0.5
	其它规律和减法一样
			非Number类型的值进行运算时，会将这些值转换为Number然后在运算
			任何值和NaN做运算都得NaN
			字符串做乘法也会转换为Number
	取余运算
		格式: Number1 % Number2
		m%n 求余,相当于m/n 获取余数
			var res = 10 % 4;
console.log(res); // 2

var num1 = 10;
var num2 = 2.5;
var res2 = num1 % num2;
console.log(res2); // 0
			n等于0 返回NaN
			m等于0 结果为0
			m>n 正常求余 如:8%3 = 2
			m<n 结果是m 如:2%4 = 2
		其它规律和减法一样
			非Number类型的值进行运算时，会将这些值转换为Number然后在运算
			任何值和NaN做运算都得NaN
			字符串做乘法也会转换为Number
```

### 10.2 . 一元运算符

```js
一元运算符 - 只需要一个操作数
正号
		+ 正号不会对数字产生任何影响
                var num = 123;
                num = +num;
                console.log(num); // 123
		对于非Number类型的值,会将先转换为Number，然后再运算
                var bool = true;
                var res = +bool;
                console.log(res); // 1

                var str = "123";
                res = +str;
                console.log(res); // 123

                var str2 = "123abc";
                res = +str2;
                console.log(res); // NaN, 所以内部不是调用parseInt, 而是Number()函数

                var temp = null;
                res = +temp;
                console.log(res); // 0

负号
		- 负号可以对数字进行负号的取反
        var num = 456;
        num = -num;
        console.log(num); // -456
                var result = 1 + -"2" + 3;
        console.log("result = "+result);
```

### 10.3. 赋值运算符

```js
赋值运算符:

简单赋值运算符
	格式: 变量 = 数据
		// 将等号右边的常量100赋值给左边的变量num
					var num = 100;
		// 将等号右边的变量num中存储的值赋值给左边的变量value
					var value = num; 
	赋值运算符左边只能是变量
                      110 = 220; // 错误写法
                      var str = 110;
                      220 = str; // 错误写法
	多个赋值运算符可以组成 赋值表达式, 赋值表达式具备右结合性
                    // 从右至左计算
                    //  先将10赋值给变量c, 然后将变量c中存储的值赋值给变量b
                    // 然后将变量b中存储的值赋值给变量a, 最后a,b,c存储的都是10
                    a = b = c = 10;
	复合赋值运算符
		复合赋值运算符
                += 加后赋值 变量+=表达式 如:a+=1;即a=a+1
                -= 减后赋值 变量-=表达式 如:a-=1;即a=a-1
                *= 乘后赋值 变量=表达式 如:a=1;即a=a*1
                /= 除后赋值 变量/=表达式 如:a/=1;即a=a/1
                %= 取模后赋值 变量%=表达式 如:a%=1;即a=a%1
		复合赋值表达式运算
                格式: 变量 复合赋值运算符 表达式; 如: a *= 1 + 2;
                由于赋值运算符是右结合性, 所以会先计算等号右边, 然后再进行复合运算
                            var value = 5;
                            value *= 2 - 2; // 等价于  value = 5 * (2 - 2);
                            console.log(value); // 0
                            // 设想如果先计算复合运算符结果是什么?
                            value = (5 * 2) - 2 = 10 - 2 = 8
```

### 10.4. 自增/自减运算符

```js
自增/自减运算符
	自增、自减运算符介绍
		在程序设计中,经常遇到“i=i+1”和“i=i-1”这两种极为常用的操作。
		JavaScript语言为这种操作提供了两个更为简洁的运算符,即++和--,分别叫做自增运算符和自减运算符。
	自增、自减运算符求值过程
		无论运算符号在前还是在后, 变量在自身基础上都会改变:
                        var num = 1;
                        num++; // 等价于 num = num + 1;
                        console.log(num); // 2

                        num = 1;
                        ++num;
                        console.log(num); // 2

                        num = 1;
                        num--; // 等价于 num = num - 1;
                        console.log(num); // 0

                        num = 1;
                        --num;
                        console.log(num); // 0
		后缀表达式:x++, x--; 先用x的当前值作为表达式的值,再进行自增自减1运算。即“先用 后变”,也就是先用变量的值参与运算,变量的值再进行自增自减变化。
                        var a, b;
                        a = 20;
                        b = 30;
                        // ++ 在后, 变量先参与其它运算, 然后再自增
                        var res = (a++) + (b++);
                        console.log(res); // 50

                        a = 10;
                        b = 20;
                        // -- 在后, 变量先参与其它运算, 然后再自减
                        res = (a--) + (b--);
                        console.log(res); // 30
                        console.log(a); // 9
                        console.log(b); // 19
		前缀表达式:++x, --x; 其中x表示变量名,先完成变量的自增自减1运算,再用x的值作为表 达式的值;即“先变后用”,也就是变量的值先变,再用变量的值参与运算:
                        var a, b;
                        a = 10;
                        b = 20;
                        // ++ 在前, 变量先自增, 然后再参与其它运算
                        res = (++a) + (++b);
                        console.log(res); // 32
                        console.log(a); // 11
                        console.log(b); // 21

                        a = 10;
                        b = 20;
                        // ++ 在前, 变量先自增, 然后再参与其它运算
                        res = (--a) + (--b);
                        console.log(res); // 28
                        console.log(a); // 9
                        console.log(b); // 19
```

### 10.5.  逻辑运算符

```js
逻辑运算符
	目的
		有时候，我们需要在多个条件同时成立的时候才能执行某段代码
		比如：用户只有同时输入了QQ和密码，才能执行登录代码，如果只输入了QQ或者只输入了密码，就不能执行登录代码。这种情况下，我们就要借助于JavaScript提供的逻辑运算符。
  &&(与运算)
  ||(或运算)
  !(非运算)
		逻辑与
			格式: 条件A && 条件B
			运算结果
				只有当条件A和条件B都成立时，结果才为true；其余情况的结果都为false。因此，条件A或条件B只要有一个不成立，结果都为false
				口诀:一假则假
			逻辑与运算过程
				总是先判断条件A是否成立
				如果条件A成立，接着再判断条件B是否成立：如果条件B成立，“条件A && 条件B”的结果就为true，如果条件B不成立，结果就为false
				如果条件A不成立，就不会再去判断条件B是否成立：因为条件A已经不成立了，不管条件B如何结果肯定是false
                            //如果两个值都是true则返回true
                            var result = true && true;
                            //只要有一个false，就返回false
                            result = true && false;
                            result = false && true;
                            result = false && false;
			短路测试
                              //第一个值为true，会检查第二个值
                              true && alert("我来了！！");
                              //第一个值为false，不会检查第二个值
                              false && alert("我没有来！！");
			注意点
                                对于非Boolean类型的数值, 逻辑与会自动将其转换为Boolean类型来判断
                                如果条件A不成立, 则返回条件A的数值本身
                                如果条件A成立, 不管条件B成不成立都返回条件B数值本身
                                var result =  "123" && "abc";
                                console.log(result); // "abc"
                                result =  "123" && 0;
                                console.log(result); // 0
                                result =  null && 0;
                                console.log(result); // null
		逻辑或
			格式: 条件A || 条件B
			运算结果
				当条件A或条件B只要有一个成立时（也包括条件A和条件B都成立），结果就为true；只有当条件A和条件B都不成立时，结果才为false
				口诀:一真为真
			逻辑或运算过程
				总是先判断条件A是否成立
				如果条件A成立，就不会再去判断条件B是否成立：因为条件A已经成立了，不管条件B如何结果肯定是1，也就是true
				如果条件A不成立，接着再判断条件B是否成立：如果条件B成立，“条件A || 条件B”的结果就为true，如果条件B不成立，结果就为false
                            //两个都是false，则返回false
                            var result = false || false;
                            //只有有一个true，就返回true
                            result = true || false;
                            result = false || true ;
                            result = true || true ;
			短路测试
                              //第一个值为false，则会检查第二个值
                              false || alert("123");
                              //第一个值为true，则不再检查第二个值
                              true || alert("123");
			注意点
                            对于非Boolean类型的数值, 逻辑或自动会将其转换为Boolean类型来判断
                            如果条件A不成立, 则不管条件B成不成立都返回条件B数值本身
                            如果条件A成立, 则返回条件A的数值本身
                            var  result =  null || 0;
                            console.log(result); // 0

                            result =  "123" || "abc";
                            console.log(result); // "123"
                            result =  "123" || 0;
                            console.log(result); // "123"
		逻辑非
			格式: ! 条件A
			运算结果
				对条件A进行取反：若条件A成立，结果就为false；若条件A不成立，结果就为true。也就是说：真的变假，假的变真。
				口诀:真变假,假变真
                            var bool1 = true;
                            var res1 = !bool1;
                            console.log(res1); // false

                            var bool2 = false;
                            var res2 = !bool2;
                            console.log(res2); // true
			注意点
                    对一个值进行两次取反，它不会变化 :
                            var bool = true;
                            var res = !!bool;
                            console.log(res); // true
				对非布尔值进行操作，则会将其转换为布尔值，然后再取反 :
                            var num = 10;
                            var res = !num; // 先将10转换为true, 然后再取反
                            console.log(res); // false
                            所以, 要想将其它类型转换为Boolean类型除了Boolean()函数, 还可以使用 !!数值;
                            !!数值;的形式,实现原理和Boolean()函数一样
```

### 10.6  关系运算符

| 序号 | 符号 | 说明                 |
| ---- | ---- | -------------------- |
| 1    | >    | 大于                 |
| 2    | <    | 小于                 |
| 3    | >=   | 大于等于             |
| 4    | <=   | 小于等于             |
| 5    | ==   | 判断值是否相等       |
| 6    | !=   | 判断值是否不等       |
| 7    | ===  | 判断值和类型是否相等 |
| 8    | !==  | 判断值和类型是否不等 |

- 对于非数值进行比较时，会将其转换为数值然后在比较

- ```js
  console.log(1 > true);
  console.log(1 >= false);
  console.log(1 > "0"); 
  console.log(1 > null);
  console.log(1 > true); //false
  console.log(1 >= false); //true
  console.log(1 > "0"); //true
  console.log(1 > null); //true
  ```

- 如果符号两侧的值都是字符串时，不会将其转换为数字进行比较, 而会分别比较字符串中字符的Unicode编码



- null、undefined 、NaN比较

```js
console.log(null == 0); // false
console.log(undefined == 0); // false
// 永远不要判断两个NaN是否相等
console.log(NaN == NaN); // false

/*
 * 可以通过isNaN()函数来判断一个值是否是NaN
 *    如果该值是NaN则返回true，否则返回false
 */
var num = NaN;
console.log(isNaN(num)); // true

// undefined 衍生自 null, 所以返回true
console.log(null == undefined); // true;
console.log(null === undefined); // false;

// == 判断值是否相等
// == 会进行数据类型转换
console.log("123" == 123); // true
// === 判断值和类型时候同时相等
// === 不会进行数据类型转换
console.log("123" === 123); // false 
```

- 注意
  - 比较两个字符串型的数字，可能会得到不可预期的结果
  - 所以, 在比较两个字符串型的数字时，一定要转型
  - console.log("1111123" < "124");

### 10.7. 逗号运算符

```
	在JavaScript中逗号“,”也是一种运算符,称为逗号运算符。 其功能是把多个表达式连接起来组成一个表达式, 称为逗号表达式。
	
求值过程:
    表达式1，表达式2，… …，表达式n;
    逗号表达式的运算过程是：先算表达式1，再算表达式2，依次算到表达式n
    整个逗号表达式的值是最后一个表达式的值
```

### 10.8  三目运算符(条件运算符)

- 格式: 条件表达式 ? 语句1 : 语句2;

- ```js
  如果条件表达式为true，则执行语句1，并返回执行结果
  如果条件表达式为false，则执行语句2，并返回执行结果
  // 弹第一个
  true?alert("语句1") : alert("语句2");
  // 弹第二个
  false?alert("语句1") : alert("语句2");
  ```

- 注意点

  - 条件运算符?和:是一对运算符,不能分开单独使用
  - 如果条件的表达式的求值结果是一个非布尔值, 会将其转换为布尔值然后在运算

## 11. 流程控制语句

### 11.1. If

```js
如果条件表达式为真,则执行语句块1,否则执行语句块2
if(条件表达式){语句块1}
else{ 语句块2}
	if(age > 18){console.log("可以上网");}
	else{console.log("你妈妈喊你吃饭");}
特点 : if和else后面的代码块({})只有一个会被执行
```

**注意点**

```js
1. 如果只有一条语句时if后面的大括号可以省略
2. 分号“;”也是一条语句, 空语句
3. if else是一个整体， else匹配if的时候匹配离它最近的一个if
4. 对于非Boolean类型的值,会先转换为Boolean类型后再判断
5. 判断变量与常量问题
		但凡遇到比较一个变量等于或者不等于某一个常量的时候，把常量写在前面
	// if(a = 0)  // 错误写法, 但不会报错
    if (0 == a) {
        console.log("a的值是0\n");
    }else{
       console.log("a的值不是0\n");
    }
			 /*
    本来是先判断变量a存储的值是否等于0,
    但是如果不小心写成a=0,代表把0存储到a中.
    为了避免这种问题判断是否相等时把常量写前面,
    因为等号左边只能是变量, 所以如果少写一个等号会报错
*/
	6. if语句可以嵌套使用
		 var num = 20;
    if (num >= 10)
    {
        if(num <= 30)
        {
            console.log("一个10~30之间的数")
        }
    }
```

### 11.2. Swith

**基本格式**

```js
switch(条件表达式){
  case 表达式:
      语句1;
      break;
  case 表达式:
      语句2; 
      break;
  case 表达式n:
      语句n;
      break;
  default:
      语句n+1;
      break;
}
```

**解释结构**

```js
计算条件表达式的值。 并逐个与case后面表达式的结果值比较
当条件表达式的值与某个表达式的值全等时, 执行其后的语句,并且不会再与其它case进行比较
如果条件表达式的值与所有case后的表达式均不相同时,则执行default后的语句。
```

**实例**

```js
    var num = 3;
    switch(num){
        case 1:
            console.log("壹");
            break;
        case 2:
            console.log("贰"); 
            break;
        case 3:
            console.log("叁");  // 输出叁
            break;
        default:
            console.log("其它数字");
            break;
    }
```

**需要注意的问题**

```js
1. case全等于问题 :
	JavaScript中case判断是否相等时是全等于(===),而不是等于(==),也就是说既会判断类型是否相等又会判断值是否相等
	case后可以是常量也可以是变量
2. 判断时会先计算表达式的值,再判断
3. case的穿透问题 :
	a. switch里面的case只要匹配一次其它的都会失效，包括default.
	b. 在case语句最后增加 break 语句,使每一次执行之后均可跳出switch语句,从而避免输出不应有的结果
4. default的位置问题:
	default可以省略
	default语句可以写在switch语句中的任意位置                              
```



## 12. 循环

### 12.1. while

```js
格式 :
while ( 条件表达式 ) {
     语句1;
     语句2;
     ....
 }
```

- **break关键字**
  - ​	跳出Switch语句
  - ​    跳出循环语句

- **continue关键字**
  - ​	跳过当前循环体中剩余的语句而继续下一次	
  - ​    continue后面的语句永远不会被执行

### 12.2. do-while

- **特点**
  - 不管while中的条件是否成立，循环体中的语句至少会被执行一遍
  - 应用场景 : 口令校验

- **格式**

```js
 do {
     语句1;
     语句2;
     ....
 } while ( 条件 );
```

- **执行流程**

  - 首先会执行一次循环体中的语句

  - 接着判断while中的条件表达式是否为真，如果为真再次执行循环体中的语句

  - 重复上述过程，直到条件不成立就结束while循环

    ```js
    var num = 20;
      do{
          console.log(num); // 输出一次10
      }while (num < 10);
    ```

    

### 12.3. for

- **格式**

  ```js
  for(①初始化表达式；②循环条件表达式；④循环后操作表达式)
  {
      ③执行语句；
  }
  ```

- **执行流程**

  - for循环开始时，会先执行初始化表达式，而且在整个循环过程中只执行一次初始化表达式
  - 接着判断循环条件表达式是否为真，如果条件为真，就会执行循环体中的语句
  - 循环体执行完毕后，接下来会执行循环后的操作表达式
  - 执行完循环后操作表达式, 然后再次判断循环条件表达式是否为真，如果条件为真，就会执行循环体中的语句
  - 重复上述过程，直到条件不成立就结束for循环

## 13. Array - 数组

### 13.1. 创建数组

- **使用 Array 构造函数**

  ```js
  创建一个空数组
  var arr1 = new Array();
  
  创建一个包含2个字符串的数组
  var arr3 = new Array("中华","yann");
  ```

- **使用数组字面量**

  ```js
  创建一个空数组
  var arr4 = [];
  
  创建一个包含2个字符串的数组
  var arr6 = ["小米","锤子"]; 
  ```

### 13.2. Array常用的方法

```js
1. 数组长度(元素个数)
	lst.length	// 5
2. 尾部追加元素
	lst.push(6)
	lst	// (6) [1, 2, 3, 4, 5, 6]
3. 尾部删除一个元素
	lst.pop()
4. 头部插入元素
	lst.unshift(0)
	lst	// (7) [0, 1, 2, 3, 4, 5]
5. 头部移除一个元素
	lst.shift()
	lst	// [1, 2, 3, 4, 5]
6. 切片
	lst.slice(0,2) 	// (2) [1, 2]
7. 反转 reverse 修改源数据
	lst.reverse()	// (5) [5, 4, 3, 2, 1]
8. 将数组所有的元素用某一个连接符连接成字符串
	lst.join('-')  // "5-4-3-2-1"
	lst.join('>')  // "5>4>3>2>1"
9. concat 将多个数字合并为一个数组
	数组1.concat(数组2,数组2...)
10. sort 排序  按照ASCII码大小排序 会修改源数据
	new_lst = lst.sort((a,b) => {return a-b}) // 升序排序 b-a 降序
11. splice() 增删元素 会修改源数据
	a. 删除元素 :
	lst.splice(0,2) // 从第1个元素开始,删除两个元素
	b. 插入元素 :
    lst.splice(2,0,插入的元素1,插入的元素2...) // 从第二个元素开始删除0个元素,插入n个元素
	c. 替换元素
	lst.splice(3,2,替换元素1,替换元素2)  // 从第三个元素开始,删除2个元素,再插入2个元素	
12. map() “映射”，对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组。:
		   var arr = [1, 2, 3, 4, 5];
            var arr2 = arr.map(function(item){
            return item*item;
            });
            console.log(arr2); //[1, 4, 9, 16, 25]
13. filter() “过滤”功能，数组中的每一项运行给定函数，返回满足过滤条件组成的数组。:
		   var arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
            var arr2 = arr.filter(function(x, index) {
            return index % 3 === 0 || x >= 8;
            }); 
            console.log(arr2); //[1, 4, 7, 8, 9, 10]
14. every() 判断数组中每一项都是否满足条件，只有所有项都满足条件，才会返回true。 :
		   var arr = [1, 2, 3, 4, 5];
            var arr2 = arr.every(function(x) {
            return x < 10;
            }); 
            console.log(arr2); //true
            var arr3 = arr.every(function(x) {
            return x < 3;
            }); 
            console.log(arr3); // false
15. some() 判断数组中是否存在满足条件的项，只要有一项满足条件，就会返回true。 :
		   var arr = [1, 2, 3, 4, 5];
            var arr2 = arr.some(function(x) {
            return x < 3;
            }); 
            console.log(arr2); //true
            var arr3 = arr.some(function(x) {
            return x < 1;
            }); 
            console.log(arr3); // false
```

- **遍历数组**

  ```js
      <script>
          var arr = [1,2,3,4,8,9,5];
          for(var i = 0; arr.length>i; i++){
              console.log(arr[i])
          }
      </script>14. 函数 ( Function ) 
  ```

## 14. 函数 ( Funciton )

### 14.1. 函数声明

```js
方式一 直接声明:
	function 函数名(){执行语句}
	调用 : 函数名()
方式二 表达式声明:
	var 函数名 = function () {执行语句}
方式三(不推荐) :
	var add = new Function('num1','num2','return num1+num2');
```

- **函数直接声明和函数表达式声明的区别 :** 

  ​	**JavaScript解析器首先会把当前作用域的函数声明提前到整个作用域的最前面。** **声明提前了,但是赋值不会提前**
  
  ```js
      <script>
              function f1(){
                  var a = b = c =9
                  //等同于以下
                  // var = a 
                  // b = 9
                  // c = 9
              }
      </script>
  ```
  
  

### 14.2. 函数的参数

```
形参 ...
实参 ...
注意 : 在其它语言中实参个数必须和形参个数一致，但是JavaScript中没有函数签名的概念，实参个数和形参个数可以不相等
```

- **函数使用注意事项**

  ```js
  1. 在调用函数时，可以在()中指定实参,实参将会赋值给函数中对应的形参
  2. 调用函数时解析器不会检查实参的类型,所以开发中一般需要对参数进行类型的检查
  3. 函数的实参可以是任意的数据类型
  4. 调用函数时，解析器不会检查实参的数量, 多余实参不会被赋值,如果实参的数量少于形参的数量，则没有对应实参的形参将是undefined
  ```

### 14.3. arguments对象

```js
1. 包含了传入函数中的所有参数,  arguments并不是一个数组，只是与数组相似,  除了拥有length属性，数组的所有属性和方法都不具备。
2. arguments对象还有一个名叫callee的属性,  该属性是一个指针,  指向拥有这个arguments对象的函数;
```

**求和实例**

**length : 函数形参的个数**

```js
    <script>
    // 求多个数的和 方法一
    function sum(num) {
        var sum_values = 0; 
        for(var i = 0; i<num.length;i++){
            sum_values +=num[i];
        }
        console.log(sum_values)
    }
    sum([1,5,9,3,88,66,99])
    </script>
**************************************************************************
    <script >
    // 求多个数的和 方法二
    function sum() {
        var sum_values = 0; 
        for(var i = 0; i<arguments.length;i++){
            sum_values +=arguments[i];
        }
        console.log(sum_values)
    }
    sum(1,5,9,3,88,66,99)
    </script>
```

### 14.4.  函数返回值（return）

```js
当一个函数被调用，通常会从函数的开始执行到结束。如果想提前结束该函数的执行可以使用return语句，return语句后面的所有语句将永远不会执行。
```

**需要注意**

```js
1. 如果函数没有显示的使用 return语句 ，那么函数有默认的返回值：undefined
2. 如果函数使用 return语句，那么跟再return后面的值，就成了函数的返回值
3. 如果函数使用 return语句，但是return后面没有任何值，那么函数的返回值也是undefined
4. 推荐的做法是要么让函数始终都返回一个值，要么永远都不要返回值。
```

## 15. 匿名函数

**应用场景 :**

### 15.1  绑定事件

```js
    <script class="">
        document.onclick = function(){
            alert('点击了网页')
        }
    </script>
```

### 15.2. 定时器

```js
    <script class="">
        setInterval(function(){
            alert('每两秒弹窗一次')
        }, 2000);
    </script>
```

### 15.3. 自调用函数

```js
函数定义完，立即被调用，这种函数叫做立即执行函数
立即执行函数往往只会执行一次
格式 :(函数体)();

    <script>
        (function () {
           alert('不用调用我,我自动执行一次')
        })()
    </script>
```

### 15.4. 回调函数

```
如果把函数的指针（地址）作为参数传递给另一个函数，当这个指针被用来调用其所指向的函数时，我们就说这是回调函数。
一般用于递归
```

**例题**

```js
斐波那契数列1 1 2 3 5 8 13 21 。。。。 求第n个数 :

<script>
    function f1(n){
        // if(n==1 || n==2)return 1;
        if(n==1)return 1;
        if(n==2)return 1;
        return f1(n-1) + f1(n-2)
    }
    console.log(f1(7))
</script>
```

```js
求n个数的累加 :
    <script>
        function getSum(n){
            if(1 == n) return 1;
            return n + getSum(n-1)
        }
        console.log(getSum(100))
    </script>
```

## 16. 变量的作用域

**JavaScript的作用域针对函数中**

- **全局变量**
  - 定义在script或者不属于某个函数的变量
  - 不使用var声明的变量是全局变量，不推荐使用
- **局部变量**
  - 定义在函数内部的变量
- **定义变量的时候，变量的声明会被提升到作用域的最上面，变量的赋值不会提升。**
- **JavaScript解析器首先会把当前作用域的函数声明提前到整个作用域的最前面**



------



# JS面向对象

```
对象 :
	1. 没有顺序的键值对
	2. 值可以是数据、可以是函数、可以是对象
```



## 1. 字面量对象

```js
// 创建person对象 :
<script>
    var person = {
        name :"站长",
        age :18,
        sex :"男",
        eat:function(){
            console.log('吃')
        }
    }

    console.log(person.name)
    person.eat()      
</script>


//调用对象的属性 :
console.log(person.name)
person.eat()
```

- **遍历对象**

```js
    var person = {
        name :"站长",
        age :18,
        sex :"男",
        eat:function(){
            console.log('吃')
        }
    }

    // 循环取key
    for(var key in person) {
        console.log(key)
    }

    // 循环取每个key的值
    for(var key in person) {
        console.log(person[key])
    }
```



