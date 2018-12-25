## 第三十五天学习 12.19
#### 一、复习
#### 二、今日内容
##### 1.栅格
+ col-xl-1/2/3/4/...   xl:Extra Large w>=1200px
+ col-lg-1/2/3/4/... lg:large w>=992px
+ col-md-1/2/3/4/... md:medium 768<=w<=991px
+ col-sm-1/2/3/4/... sm:small w<=676
+ xs:Extra small w<=575
col 只写col，每一列平均分配

不同屏幕下,列的适应性问题(向上兼容，导致扩大范围)
+ col-xl-* 只对超大屏生效
+ col-lg-* 对lg/xl屏生效
+ col-md-* 对md/lg/xl屏生效
+ col-sm-* 对sm/md/lg/xl生效
列偏移
可以通过列偏移类实现指定列和后面列的偏移
 offset-* (*：0~11)
 ## 三、弹性布局
 d-flex或者d-inline-flex创建一个弹性容器
 + flex-*-row 不同屏幕下主轴方向x对齐
 + flex-*-column 不同屏幕下主轴方向y对齐
 + flex-row-reverse
 + flex-column-reverse
 + justify-content-end/center/between/around
 响应式flex类
+ d-*-flex
+ flex-*-row
+ flex-*-column
+ flex-*-column-reverse
+ flex-*-row-reverse
+ justify-content-*-start/end/center/between/around
## 四、表单
在form表中的类
+ 方向的排列
  + form-group+form-control堆叠,垂直方向排列宽度100%，
  + form-inline 内联表单 水平排列
  + form-control 宽度100%
+ form-check写在单选按钮/多选按钮的父级容器中,有相对定位
+ form-check-inline 写在单选按钮/多选按钮的父级容器中自带弹性布局,交叉轴垂直居
+ form-check-input 自带绝对定位，需要与上面form-check/form-check-inline配合使用
+ form-check-label底外边距为0
+ form-text 上外边距为0.25rem
## 五、组件
boot把一些功能性的模块,进行了封装。
我们只需要按照boot要求的层次结构以及类名套用。
就可以完成
+ 1.下拉菜单

    外部包裹
    ```
        <div class="dropdown"></div>
    ```
    内部菜单按钮
    ```
         <button class="btn btn-primary dropdown-toggle" data-toggle="dropdown">下拉</button>
    ```
    内部菜单栏
    ```
        <div class="dropdown-menu">
                    <div class="dropdown-header">菜单标题</div>
                    <a href="#" class="dropdown-item active">菜单1</a>
                    <a href="#" class="dropdown-item">菜单2</a>
                    <a href="#" class="dropdown-item">菜单3</a>
                    <a href="#" class="dropdown-item">菜单4</a>
                    <a href="#" class="dropdown-item">菜单5</a>
                    <a href="#" class="dropdown-item">菜单6</a>
        </div>
    ```
    菜单栏中的菜单项
    ```
        <div class="dropdown-header">菜单标题</div>
        <a href="#" class="dropdown-item active">菜单1</a>
        <a href="#" class="dropdown-item">菜单2</a>
        <a href="#" class="dropdown-item">菜单3</a>
        <a href="#" class="dropdown-item">菜单4</a>
        <a href="#" class="dropdown-item">菜单5</a>
        <a href="#" class="dropdown-item">菜单6</a>

    ```
    在每个item之间添加分割线
    ```
        <div class="dropdown-divider"></div>
    ```
+ 2.按钮组

    + 外包裹添加类名class="btn-group"  把内部的显示成一组
        + 使用btn-group-lg/sm控制按钮组的大小
        + 使用btn-group-vertical设置垂直按钮组
+ 3.信息提示框
    + 外包裹class="alert"
    可以修改颜色alert-danger/warning/info...
    如果内部的x想使用类.close,父级要添加alert-dismissible

        ```
            <div class="alert alert-danger w-50 alert-dismissible">
                    <span class="close" data-dismiss="alert">&times;</span>
                    请检查用户信息
            </div>
        ```

    + 内部有文本提示
    + 内部有关闭提示框的x
    data-dismiss="alert"
+ 4.导航
    + 1.ul必须有类名.nav .nav-justified
    .nav-justified本身没有任何样式,为了给子元素item引路
    + 2.li class="nav-item"
    + 3.a class="nav-link"
    + 其他样式
    ul中，如果.nav-justified,意味着导航项等宽显示
    如果想使用justify-content-*主轴的对齐，需要把.nav-justified删掉
    flex-row/column/reverse都可以生效
+ 5.选项卡导航
    + 外包裹ul class="nav nav-tabs"
    ```
        <ul class="nav nav-tabs">
                <li class="nav-item"><a href="#apple" class="nav-link active" data-toggle="tab">APPLE</a></li>
                <li class="nav-item"><a href="#huawei" class="nav-link" data-toggle="tab">HuaWei</a></li>
        </ul>
    ```
    + ul内部需要有两套
        + 选项卡
        li class="nav-item"
        a class="nav-link"
        + 对应内容
        div class="tab-content "tab-content对自己没有任何修饰，为了给内部子元素.tab-pane引路
        tab-content > ele class="tab-pane" 组合之后,ele就隐藏了，如果想显示 tab-content >ele class=".active"
        ```
            <div class="tab-content">
                    <div class="tab-pane active" id="apple">APPLE Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias animi architecto asperiores atque dolor eius eos eum fugit in neque nihil nisi nobis officia quaerat, quis sit temporibus ut, voluptatum.</div>
                    <div class="tab-pane" id="huawei">HuaWei Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto dignissimos dolorem dolores doloribus eligendi, est ex in inventore itaque mollitia quam quasi qui repellat sunt suscipit voluptas voluptatem voluptates voluptatum?</div>
            </div>
        ```
        + 点击选项卡的动作
        a.nav-link有事件的激活，使用自定义属性data-toggle="tab"实现切换
        + 把选项卡a标签的href和内容的id进行绑定
        内容的id
        ```
            <div class="tab-pane active" id="apple">APPLE Lorem</div>
        ```
        + 与选项卡a标签的href绑定
        ```
           <a href="#apple" class="nav-link active" data-toggle="tab">APPLE</a>
        ```
        + 页面刷新，默认显示的选项卡和内容没有设置


















