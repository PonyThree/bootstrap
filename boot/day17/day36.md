## 第三十六天 12.20
### 一、复习
### 二、今日内容
#### 1.组件
##### 1.1导航
+ 胶囊导航
.nav-pills 替代选项卡导航的.nav-tabs
data-toggle="pill"
其他部分同选项卡导航
+ 导航栏
在ul外层包裹一个div,就把导航变为了导航栏
    + 外层包裹,div.navbar  弹性+相对定位
 后面紧跟 navbar-expand-lg/md/sm(配合的类ul.navbar-nav)
 此处的响应式，是设置导航在某一个屏幕下横向显示，其他屏幕纵向显示(向上兼容)
    + 导航可以使用ul。添加.navbar-nav(默认弹性，主轴为column)
    配合之前的navbar-expand-lg/md/sm.可以使主轴变为row
    + li.nav-item>a.nav-link
    注意：在外包裹中，可以使bg-color,设置导航栏颜色
    整个导航栏横向显示，还是纵向显示。是靠navbar-expand-lg/md/sm控制的
+ 折叠
控制内容的显示与隐藏
在button中添加  data-toggle="collapse"和折叠目标data-target="#内容id"#内容id对应折叠内容的id
如果使用a标签,直接在href中填写对应内容的id
在内容中添加id和和class="collapse"实现折叠
+ 折叠导航栏
    + 外部包裹div.navbar .navbar-expand-* .bg-dark .nav-dark .bg-dark,.navbar-dark保持一致，都是dark/light
    .navbar-dark本身没有样式，为子元素选择器引路
    影响的子元素有.navbar-brand .navbar-link .navbar-toggler .navbar-toggler-icon
    + 外包裹的内部
        + 不折叠的选项
        a.navbar-brand
        + 折叠按钮button.navbar-toggler
        .navbar-expand-*  .navbar-toggler{设置什么时候显示显示/隐藏}
        btn需要写自定义属性data-toggle="collapse" data-target="#折叠内容id"
        + 内容div.collapse .navbar-collapse id="折叠内容的id"
        .navbar-collapse设置折叠导航打开的位置
            + 导航的内容
            ul.navbar-nav>li.nav-item>a.nav-link
##### 1.2 卡片
通过.card创建一个卡片
+ .card-header卡片的头部
+ .card-body 卡片的内容
+ .card-footer卡片的底部
一般用于文字和图片的显示
##### 1.3手风琴
卡片和折叠的结合
+ 最外层包裹  div#parent 这里的id是为了做data-parent="#parent"目的是，一个折叠打得开，其他在这个包裹的折叠都自己关闭
+ div.card>div.card-header>a.card-link
    a标签中写折叠的事件和折叠对象
    data-toggle="collapse" href="#id"
+ 折叠内容
div.collapse#p1>div.card-body>p
+ 注意，.card-body和.collapse不能在同一个div上，会冲突，会卡顿
+ 如果希望一个卡片打开，其它卡片都折叠，需要在折叠元素上添加事件data-parent="#parent"外层包裹的ID
##### 1.5媒体对象
容器添加.media(flex)
项目有img
    div.media-body
由于img和里面的div都是弹性项目，可以使用弹性布局的一切类
比如img.align-self-center
##### 1.6轮播
.carousel旋转木马
最外层大包裹负责让图片轮播动起来
div.carousel data-ride="carousel"
+ 图片轮播
添加图片的包裹.carousel-inner
每一张图片的包裹.carousel-item
显示的图片.active
可选择样式类名
在图片上添加文字和标题.carousel-caption
+ 导航指示符
ul.carousel-indicators
li data-slide-to="0" 滑动至哪一张图片,从0开始
data-target="最外层包裹 .carousel的id"
重写boot提供的样式,让指示器变为圆点,颜色为#0aa1ed;
```
    .carousel-indicators li{
                width: 0.5rem;
                height: 0.5rem;
                border-radius:50%;
            }
            .carousel-indicators .active{
                background-color: #0aa1ed;
            }
```
+ 左右箭头
a.carousel-control-prev>span.carousel-control-prev-icon
a.carousel-control-next>span.carousel-control-next-icon
a标签中有事件data-slide="prev/next"
事件的目标href="#demo"
样式修改
```
    .carousel-control-next,.carousel-control-prev{
                background-color: rgba(0, 0, 0, .4);
                width: 3%;
                height: 20%;
                margin:auto;
    }
```
##### 1.7模态框
modal模态框是覆盖在父窗体上的子窗体
模态框可以在不离开父窗体的情况下，与用户交互，提交一些交互信息
+ 外包裹div.modal
+ div.modal内部一个div.modal-dialog
+ div.modal-dialog内部一个div.modal-content
+ div.modal-content内部中有modal-header modal-body modal-footer
## 三、其他组件
+ 1.徽章
就是添加颜色样式和圆角
.badge .badge-pill .badge-danger/warning
+ 2.巨幕
巨大的内边距
div.jumbotron
+ 3.分页
外包裹ul.pagination创建分页
使用pagination-lg/sm设置分页的大小
内部使用li.page>a.page-link
使用active和disabled修饰li
+ 4.面包屑导航
面包屑导航一般用于有层次关系的导航
ul.breadcrumb>li.breaadcrumb-item>a
改变item的连接符号
```
    .breadcrumb-item + .breadcrumb-item::before {
                content: "→";
    }
```
+ 进度条
进度条的槽div.progress
进度条在槽里写div.progress-bar
w-* 是宽度
bg-* 是进度条颜色
progress-bar-striped设置条纹进度条
progress-bar-animated为进度条设置动画
可以在同一个槽上，添加多个进度条
boot重点
+ 媒体查询
+ 栅格布局
+ scss
作业：
+ 完成boot中文主页，折叠导航栏
+ 完成学子首页，轮播图
不能













