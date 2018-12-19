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








