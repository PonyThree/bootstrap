## ����ʮ����ѧϰ 12.19
#### һ����ϰ
#### ������������
##### 1.դ��
+ col-xl-1/2/3/4/...   xl:Extra Large w>=1200px
+ col-lg-1/2/3/4/... lg:large w>=992px
+ col-md-1/2/3/4/... md:medium 768<=w<=991px
+ col-sm-1/2/3/4/... sm:small w<=676
+ xs:Extra small w<=575
col ֻдcol��ÿһ��ƽ������

��ͬ��Ļ��,�е���Ӧ������(���ϼ��ݣ���������Χ)
+ col-xl-* ֻ�Գ�������Ч
+ col-lg-* ��lg/xl����Ч
+ col-md-* ��md/lg/xl����Ч
+ col-sm-* ��sm/md/lg/xl��Ч
��ƫ��
����ͨ����ƫ����ʵ��ָ���кͺ����е�ƫ��
 offset-* (*��0~11)
 ## �������Բ���
 d-flex����d-inline-flex����һ����������
 + flex-*-row ��ͬ��Ļ�����᷽��x����
 + flex-*-column ��ͬ��Ļ�����᷽��y����
 + flex-row-reverse
 + flex-column-reverse
 + justify-content-end/center/between/around
 ��Ӧʽflex��
+ d-*-flex
+ flex-*-row
+ flex-*-column
+ flex-*-column-reverse
+ flex-*-row-reverse
+ justify-content-*-start/end/center/between/around
## �ġ���
��form���е���
+ ���������
  + form-group+form-control�ѵ�,��ֱ�������п��100%��
  + form-inline ������ ˮƽ����
  + form-control ���100%
+ form-checkд�ڵ�ѡ��ť/��ѡ��ť�ĸ���������,����Զ�λ
+ form-check-inline д�ڵ�ѡ��ť/��ѡ��ť�ĸ����������Դ����Բ���,�����ᴹֱ��
+ form-check-input �Դ����Զ�λ����Ҫ������form-check/form-check-inline���ʹ��
+ form-check-label����߾�Ϊ0
+ form-text ����߾�Ϊ0.25rem
## �塢���
boot��һЩ�����Ե�ģ��,�����˷�װ��
����ֻ��Ҫ����bootҪ��Ĳ�νṹ�Լ��������á�
�Ϳ������
+ 1.�����˵�

    �ⲿ����
    ```
        <div class="dropdown"></div>
    ```
    �ڲ��˵���ť
    ```
         <button class="btn btn-primary dropdown-toggle" data-toggle="dropdown">����</button>
    ```
    �ڲ��˵���
    ```
        <div class="dropdown-menu">
                    <div class="dropdown-header">�˵�����</div>
                    <a href="#" class="dropdown-item active">�˵�1</a>
                    <a href="#" class="dropdown-item">�˵�2</a>
                    <a href="#" class="dropdown-item">�˵�3</a>
                    <a href="#" class="dropdown-item">�˵�4</a>
                    <a href="#" class="dropdown-item">�˵�5</a>
                    <a href="#" class="dropdown-item">�˵�6</a>
        </div>
    ```
    �˵����еĲ˵���
    ```
        <div class="dropdown-header">�˵�����</div>
        <a href="#" class="dropdown-item active">�˵�1</a>
        <a href="#" class="dropdown-item">�˵�2</a>
        <a href="#" class="dropdown-item">�˵�3</a>
        <a href="#" class="dropdown-item">�˵�4</a>
        <a href="#" class="dropdown-item">�˵�5</a>
        <a href="#" class="dropdown-item">�˵�6</a>

    ```
    ��ÿ��item֮����ӷָ���
    ```
        <div class="dropdown-divider"></div>
    ```
+ 2.��ť��

    + ������������class="btn-group"  ���ڲ�����ʾ��һ��
        + ʹ��btn-group-lg/sm���ư�ť��Ĵ�С
        + ʹ��btn-group-vertical���ô�ֱ��ť��
+ 3.��Ϣ��ʾ��
    + �����class="alert"
    �����޸���ɫalert-danger/warning/info...
    ����ڲ���x��ʹ����.close,����Ҫ���alert-dismissible

        ```
            <div class="alert alert-danger w-50 alert-dismissible">
                    <span class="close" data-dismiss="alert">&times;</span>
                    �����û���Ϣ
            </div>
        ```

    + �ڲ����ı���ʾ
    + �ڲ��йر���ʾ���x
    data-dismiss="alert"
+ 4.����
    + 1.ul����������.nav .nav-justified
    .nav-justified����û���κ���ʽ,Ϊ�˸���Ԫ��item��·
    + 2.li class="nav-item"
    + 3.a class="nav-link"
    + ������ʽ
    ul�У����.nav-justified,��ζ�ŵ�����ȿ���ʾ
    �����ʹ��justify-content-*����Ķ��룬��Ҫ��.nav-justifiedɾ��
    flex-row/column/reverse��������Ч
+ 5.ѡ�����
    + �����ul class="nav nav-tabs"
    ```
        <ul class="nav nav-tabs">
                <li class="nav-item"><a href="#apple" class="nav-link active" data-toggle="tab">APPLE</a></li>
                <li class="nav-item"><a href="#huawei" class="nav-link" data-toggle="tab">HuaWei</a></li>
        </ul>
    ```
    + ul�ڲ���Ҫ������
        + ѡ�
        li class="nav-item"
        a class="nav-link"
        + ��Ӧ����
        div class="tab-content "tab-content���Լ�û���κ����Σ�Ϊ�˸��ڲ���Ԫ��.tab-pane��·
        tab-content > ele class="tab-pane" ���֮��,ele�������ˣ��������ʾ tab-content >ele class=".active"
        ```
            <div class="tab-content">
                    <div class="tab-pane active" id="apple">APPLE Lorem ipsum dolor sit amet, consectetur adipisicing elit. Alias animi architecto asperiores atque dolor eius eos eum fugit in neque nihil nisi nobis officia quaerat, quis sit temporibus ut, voluptatum.</div>
                    <div class="tab-pane" id="huawei">HuaWei Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto dignissimos dolorem dolores doloribus eligendi, est ex in inventore itaque mollitia quam quasi qui repellat sunt suscipit voluptas voluptatem voluptates voluptatum?</div>
            </div>
        ```
        + ���ѡ��Ķ���
        a.nav-link���¼��ļ��ʹ���Զ�������data-toggle="tab"ʵ���л�
        + ��ѡ�a��ǩ��href�����ݵ�id���а�
        ���ݵ�id
        ```
            <div class="tab-pane active" id="apple">APPLE Lorem</div>
        ```
        + ��ѡ�a��ǩ��href��
        ```
           <a href="#apple" class="nav-link active" data-toggle="tab">APPLE</a>
        ```
        + ҳ��ˢ�£�Ĭ����ʾ��ѡ�������û������


















