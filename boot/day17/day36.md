## ����ʮ���� 12.20
### һ����ϰ
### ������������
#### 1.���
##### 1.1����
+ ���ҵ���
.nav-pills ���ѡ�������.nav-tabs
data-toggle="pill"
��������ͬѡ�����
+ ������
��ul������һ��div,�Ͱѵ�����Ϊ�˵�����
    + ������,div.navbar  ����+��Զ�λ
 ������� navbar-expand-lg/md/sm(��ϵ���ul.navbar-nav)
 �˴�����Ӧʽ�������õ�����ĳһ����Ļ�º�����ʾ��������Ļ������ʾ(���ϼ���)
    + ��������ʹ��ul�����.navbar-nav(Ĭ�ϵ��ԣ�����Ϊcolumn)
    ���֮ǰ��navbar-expand-lg/md/sm.����ʹ�����Ϊrow
    + li.nav-item>a.nav-link
    ע�⣺��������У�����ʹbg-color,���õ�������ɫ
    ����������������ʾ������������ʾ���ǿ�navbar-expand-lg/md/sm���Ƶ�
+ �۵�
�������ݵ���ʾ������
��button�����  data-toggle="collapse"���۵�Ŀ��data-target="#����id"#����id��Ӧ�۵����ݵ�id
���ʹ��a��ǩ,ֱ����href����д��Ӧ���ݵ�id
�����������id�ͺ�class="collapse"ʵ���۵�
+ �۵�������
    + �ⲿ����div.navbar .navbar-expand-* .bg-dark .nav-dark .bg-dark,.navbar-dark����һ�£�����dark/light
    .navbar-dark����û����ʽ��Ϊ��Ԫ��ѡ������·
    Ӱ�����Ԫ����.navbar-brand .navbar-link .navbar-toggler .navbar-toggler-icon
    + ��������ڲ�
        + ���۵���ѡ��
        a.navbar-brand
        + �۵���ťbutton.navbar-toggler
        .navbar-expand-*  .navbar-toggler{����ʲôʱ����ʾ��ʾ/����}
        btn��Ҫд�Զ�������data-toggle="collapse" data-target="#�۵�����id"
        + ����div.collapse .navbar-collapse id="�۵����ݵ�id"
        .navbar-collapse�����۵������򿪵�λ��
            + ����������
            ul.navbar-nav>li.nav-item>a.nav-link
##### 1.2 ��Ƭ
ͨ��.card����һ����Ƭ
+ .card-header��Ƭ��ͷ��
+ .card-body ��Ƭ������
+ .card-footer��Ƭ�ĵײ�
һ���������ֺ�ͼƬ����ʾ
##### 1.3�ַ���
��Ƭ���۵��Ľ��
+ ��������  div#parent �����id��Ϊ����data-parent="#parent"Ŀ���ǣ�һ���۵���ÿ�������������������۵����Լ��ر�
+ div.card>div.card-header>a.card-link
    a��ǩ��д�۵����¼����۵�����
    data-toggle="collapse" href="#id"
+ �۵�����
div.collapse#p1>div.card-body>p
+ ע�⣬.card-body��.collapse������ͬһ��div�ϣ����ͻ���Ῠ��
+ ���ϣ��һ����Ƭ�򿪣�������Ƭ���۵�����Ҫ���۵�Ԫ��������¼�data-parent="#parent"��������ID
##### 1.5ý�����
�������.media(flex)
��Ŀ��img
    div.media-body
����img�������div���ǵ�����Ŀ������ʹ�õ��Բ��ֵ�һ����
����img.align-self-center
##### 1.6�ֲ�
.carousel��תľ��
���������������ͼƬ�ֲ�������
div.carousel data-ride="carousel"
+ ͼƬ�ֲ�
���ͼƬ�İ���.carousel-inner
ÿһ��ͼƬ�İ���.carousel-item
��ʾ��ͼƬ.active
��ѡ����ʽ����
��ͼƬ��������ֺͱ���.carousel-caption
+ ����ָʾ��
ul.carousel-indicators
li data-slide-to="0" ��������һ��ͼƬ,��0��ʼ
data-target="�������� .carousel��id"
��дboot�ṩ����ʽ,��ָʾ����ΪԲ��,��ɫΪ#0aa1ed;
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
+ ���Ҽ�ͷ
a.carousel-control-prev>span.carousel-control-prev-icon
a.carousel-control-next>span.carousel-control-next-icon
a��ǩ�����¼�data-slide="prev/next"
�¼���Ŀ��href="#demo"
��ʽ�޸�
```
    .carousel-control-next,.carousel-control-prev{
                background-color: rgba(0, 0, 0, .4);
                width: 3%;
                height: 20%;
                margin:auto;
    }
```
##### 1.7ģ̬��
modalģ̬���Ǹ����ڸ������ϵ��Ӵ���
ģ̬������ڲ��뿪�����������£����û��������ύһЩ������Ϣ
+ �����div.modal
+ div.modal�ڲ�һ��div.modal-dialog
+ div.modal-dialog�ڲ�һ��div.modal-content
+ div.modal-content�ڲ�����modal-header modal-body modal-footer
## �����������
+ 1.����
���������ɫ��ʽ��Բ��
.badge .badge-pill .badge-danger/warning
+ 2.��Ļ
�޴���ڱ߾�
div.jumbotron
+ 3.��ҳ
�����ul.pagination������ҳ
ʹ��pagination-lg/sm���÷�ҳ�Ĵ�С
�ڲ�ʹ��li.page>a.page-link
ʹ��active��disabled����li
+ 4.���м����
���м����һ�������в�ι�ϵ�ĵ���
ul.breadcrumb>li.breaadcrumb-item>a
�ı�item�����ӷ���
```
    .breadcrumb-item + .breadcrumb-item::before {
                content: "��";
    }
```
+ ������
�������Ĳ�div.progress
�������ڲ���дdiv.progress-bar
w-* �ǿ��
bg-* �ǽ�������ɫ
progress-bar-striped�������ƽ�����
progress-bar-animatedΪ���������ö���
������ͬһ�����ϣ���Ӷ��������
boot�ص�
+ ý���ѯ
+ դ�񲼾�
+ scss
��ҵ��
+ ���boot������ҳ���۵�������
+ ���ѧ����ҳ���ֲ�ͼ
����













