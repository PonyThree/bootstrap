## 第三十七天学习 12.21
### 一、复习
### 二、今日内容
#### 1.SCSS
##### 1.1css有几个特点
+ 语法不够强大，没有变量和合理的样式复用机制
+ 使得逻辑上相关的属性必须以字面的形式重复输出
难以维护
+ 动态的样式语言为css富裕了动态语言的特征
+ 极大地提高了样式语言的可维护
##### 1.2常见的动态样式语言：
    scss/sass(scss兼容sass)
    stylus
##### 1.3less
动态语言---css的预处理器---->*.css(浏览器才可以解析)
#### 2.什么是SCSS
是一款高效强化css的辅助工具
在css的语法上，增加了变量，嵌套，混合，导入，函数等高级功能。这些拓展让css更加强大与优雅。
#### 3.scss的作用，有助于更高的管理样式文件，以及更高效的开发项目
#### 4.scss的使用
##### 4.1在服务器端使用
+ (1)scss在服务器端使用
        + 安装nodedjs解释器
+ (2)安装scss的编译程序
在线安装 npm install -g node-sass
webstorm中alt+f12打开控制台
注意：要求nodejs版本在8.11以上
##### 4.2把scss包中的4个文件拷贝到nodejs目录下
##### 4.3编写01.scss文件
把.scss转换成.css文件
在正确的路径下，打开黑窗口，输入
node-sass scss/01.scss css/01.css
如果生成01.css则正确
批量把scss转换成css，多文件转换命令
node-sass 文件夹 -o css文件夹
 单文件监听命令,scss文件一旦保存，自动转换为css文件
 node-sass -w scss/01.scss css/01.css
 多文件监听命令
 node-sass -w scss -o css
## 三、SCSS的基础语法
使用$表示变量
变量的命名规范，遵循css中选择器的命名规范
可以包含_ -,不能以纯数字开头，见名知意
$jd_red:#f10125;颜色变量
$w:100px;数值变量
注意：
+ 声明变量时，变量值可以应用其他
+ 如果变量已经声明赋值了，那就用它之前的声明的值
否则使用现在声明的值
##### 群组选择器的嵌套
```
    nav,div,footer{
      a{
        color:#000;
        &:hover{
          color:#f00;
        }
      }
    }
```
##### 属性嵌套
```
    div{
      border:{style:solid;width:1px;color:red;}
    }
```
练习：一个200*200的div,红色背景，鼠标悬停过渡到黄色背景，并且变为圆形，历时两秒。使用scss。
#### 2.导入scss文件
在scss中，局部文件名以下划线开头
这样做，sass在编译的时候就不会编译以下划线开头的文件，而只是把这个文件用作导入

引用局部文件时，是关键字@import"局部文件名"，局部文件省略了下划线和后缀名。并且一个局部文件可以被多个scss文件引用。
#### 3.混合器
把需要在多个样式中出现的，相同的部分提取出来，封装到混合器中。
关键字@mixin 混合器名称{重用的样式}
使用时，关键字@include 混合器名称。就可以在很多的样式中，使用封装好的样式了。
练习：a标签文字为灰色无下划线，用列表布局。ul>li*3>a
在scss中编写,边框圆角，使用混合器方式编写。
鼠标悬停在链接上，文字颜色变红。
+ 带参数的混合器
定义混合器的时候，在()添加参数
调用混合器的时候，在()把参数补上
```
   @mixin lin-colors($normal,$hover,$visited){
     color:$normal;
     &:hover{color:$hover};
     &:visited{color:$visited};
   }
   ul li a{
     @include lin-colors(#f00,#0f0,#00f);
   }

```
#### 4.继承
继承就是一个选择器可以继承另一个选择器定义的所有样式
在css中的表现形式是一个???
在css中的表现形式是两个选择器共有的部分，变成了群组选择器
练习：
在选择器中.my-border中定义1px solid transparent
宽度400 ，距离左边有20px。
在选择器.my-bottom-border 中继承.my-border
设置底边框为红色，鼠标悬停时底边框为蓝色
#### 5.scss中的运算
+ 1.数字
加减乘除，求模取整
会在不同单位间转换值
width:1in+8pt ;
scss不能转换相对单位
height:1rem+1em;转换失败
(1)注意：加法
```
    p::before{
      content:"Microsoftyahei";
      font-family: A+"rial";
    }

```
+ 可以用于连接字符串
如果用引号去连接无引号的字符串，结果是有引号的
如果用无引号去连接有引号的字符串，结果是无引号
(2)减法
-会被有限解析为变量名，所以使用变量和减法，需要-前后添加空格
width:$size - $my-width;
(3)除法
在scss中，除号经常起到分割的用途/
在以下的情况视为除法运算
+ 1.如果值，或者值的一部分，是变量或者函数的返回值
+ 2.如果值被小括号包裹，视为除法
+ 3.如果值是算数表达式的一部分，视为除法
(4)运算表达式与其他值连用时,用空格做连接
margin:4px + 5px auto;
(5)在有引号的字符串中，
```
    content:"I ate #{16+23} baozis";
```
+ 2.颜色
颜色值是分段计算的，红+红  绿+绿 蓝+蓝
```
    p{
      color:#010203+#010203;
    }
    p{
      color:rgb(11,22,33)+rgb(11,22,33);
    }
    p{
      color:rgba(11,22,33,0.5)+rgba(11,22,33,0.5);
    }

```
两个rgba相加，alpha的值，必须相等才可以计算，因为算数运算符不会作用到alpha
## 四、函数
+ 1.scss定义了多种函数，有些函数喊谁呢之直接在css中调用
    + 1.颜色函数
    rgba(red,green,blue,alpha)
    + 2.hsl(hue,saturation,lightness)
    hue:色调 取值0~360 3个色段 每一个120一个色段
    saturation:饱和度 0.0%~100.0%
    linghtness:亮度0.0%~100.0%
+ 2.数字函数
    + round($value)四舍五入
    + ceil($value)向上取整
    + floor($value)向下取整
    + max($v1,$v2,...)
    + min($v1,$v2...)
    + random() 随机数
+ 3.字符串函数
    + 3.1
    unquote($string)删除字符串的引号
    quote($string)给字符串添加引号
    To-upper-case()转换成大写
    To-lower-case()转换成小写
    + 3.2自定义函数
    ```
        @function 函数名($n){
                函数体;
                @return 结果;
        }
    ```
## 五、控制指令
@if,@else if,@else
boolean表达式，可以添加括号，也可以不加。








