## ����ʮ����ѧϰ 12.21
### һ����ϰ
### ������������
#### 1.SCSS
##### 1.1css�м����ص�
+ �﷨����ǿ��û�б����ͺ�������ʽ���û���
+ ʹ���߼�����ص����Ա������������ʽ�ظ����
����ά��
+ ��̬����ʽ����Ϊcss��ԣ�˶�̬���Ե�����
+ ������������ʽ���ԵĿ�ά��
##### 1.2�����Ķ�̬��ʽ���ԣ�
    scss/sass(scss����sass)
    stylus
##### 1.3less
��̬����---css��Ԥ������---->*.css(������ſ��Խ���)
#### 2.ʲô��SCSS
��һ���Чǿ��css�ĸ�������
��css���﷨�ϣ������˱�����Ƕ�ף���ϣ����룬�����ȸ߼����ܡ���Щ��չ��css����ǿ�������š�
#### 3.scss�����ã������ڸ��ߵĹ�����ʽ�ļ����Լ�����Ч�Ŀ�����Ŀ
#### 4.scss��ʹ��
##### 4.1�ڷ�������ʹ��
+ (1)scss�ڷ�������ʹ��
        + ��װnodedjs������
+ (2)��װscss�ı������
���߰�װ npm install -g node-sass
webstorm��alt+f12�򿪿���̨
ע�⣺Ҫ��nodejs�汾��8.11����
##### 4.2��scss���е�4���ļ�������nodejsĿ¼��
##### 4.3��д01.scss�ļ�
��.scssת����.css�ļ�
����ȷ��·���£��򿪺ڴ��ڣ�����
node-sass scss/01.scss css/01.css
�������01.css����ȷ
������scssת����css�����ļ�ת������
node-sass �ļ��� -o css�ļ���
 ���ļ���������,scss�ļ�һ�����棬�Զ�ת��Ϊcss�ļ�
 node-sass -w scss/01.scss css/01.css
 ���ļ���������
 node-sass -w scss -o css
## ����SCSS�Ļ����﷨
ʹ��$��ʾ����
�����������淶����ѭcss��ѡ�����������淶
���԰���_ -,�����Դ����ֿ�ͷ������֪��
$jd_red:#f10125;��ɫ����
$w:100px;��ֵ����
ע�⣺
+ ��������ʱ������ֵ����Ӧ������
+ ��������Ѿ�������ֵ�ˣ��Ǿ�����֮ǰ��������ֵ
����ʹ������������ֵ
##### Ⱥ��ѡ������Ƕ��
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
##### ����Ƕ��
```
    div{
      border:{style:solid;width:1px;color:red;}
    }
```
��ϰ��һ��200*200��div,��ɫ�����������ͣ���ɵ���ɫ���������ұ�ΪԲ�Σ���ʱ���롣ʹ��scss��
#### 2.����scss�ļ�
��scss�У��ֲ��ļ������»��߿�ͷ
��������sass�ڱ����ʱ��Ͳ���������»��߿�ͷ���ļ�����ֻ�ǰ�����ļ���������

���þֲ��ļ�ʱ���ǹؼ���@import"�ֲ��ļ���"���ֲ��ļ�ʡ�����»��ߺͺ�׺��������һ���ֲ��ļ����Ա����scss�ļ����á�
#### 3.�����
����Ҫ�ڶ����ʽ�г��ֵģ���ͬ�Ĳ�����ȡ��������װ��������С�
�ؼ���@mixin ���������{���õ���ʽ}
ʹ��ʱ���ؼ���@include ��������ơ��Ϳ����ںܶ����ʽ�У�ʹ�÷�װ�õ���ʽ�ˡ�
��ϰ��a��ǩ����Ϊ��ɫ���»��ߣ����б����֡�ul>li*3>a
��scss�б�д,�߿�Բ�ǣ�ʹ�û������ʽ��д��
�����ͣ�������ϣ�������ɫ��졣
+ �������Ļ����
����������ʱ����()���Ӳ���
���û������ʱ����()�Ѳ�������
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
#### 4.�̳�
�̳о���һ��ѡ�������Լ̳���һ��ѡ���������������ʽ
��css�еı�����ʽ��һ��???
��css�еı�����ʽ������ѡ�������еĲ��֣������Ⱥ��ѡ����
��ϰ��
��ѡ������.my-border�ж���1px solid transparent
����400 �����������20px��
��ѡ����.my-bottom-border �м̳�.my-border
���õױ߿�Ϊ��ɫ�������ͣʱ�ױ߿�Ϊ��ɫ
#### 5.scss�е�����
+ 1.����
�Ӽ��˳�����ģȡ��
���ڲ�ͬ��λ��ת��ֵ
width:1in+8pt ;
scss����ת����Ե�λ
height:1rem+1em;ת��ʧ��
(1)ע�⣺�ӷ�
```
    p::before{
      content:"Microsoftyahei";
      font-family: A+"rial";
    }

```
+ �������������ַ���
���������ȥ���������ŵ��ַ���������������ŵ�
�����������ȥ���������ŵ��ַ����������������
(2)����
-�ᱻ���޽���Ϊ������������ʹ�ñ����ͼ�������Ҫ-ǰ�����ӿո�
width:$size - $my-width;
(3)����
��scss�У����ž����𵽷ָ����;/
�����µ������Ϊ��������
+ 1.���ֵ������ֵ��һ���֣��Ǳ������ߺ����ķ���ֵ
+ 2.���ֵ��С���Ű�������Ϊ����
+ 3.���ֵ����������ʽ��һ���֣���Ϊ����
(4)�������ʽ������ֵ����ʱ,�ÿո�������
margin:4px + 5px auto;
(5)�������ŵ��ַ����У�
```
    content:"I ate #{16+23} baozis";
```
+ 2.��ɫ
��ɫֵ�Ƿֶμ���ģ���+��  ��+�� ��+��
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
����rgba��ӣ�alpha��ֵ��������Ȳſ��Լ��㣬��Ϊ����������������õ�alpha
## �ġ�����
+ 1.scss�����˶��ֺ�������Щ������˭��ֱ֮����css�е���
    + 1.��ɫ����
    rgba(red,green,blue,alpha)
    + 2.hsl(hue,saturation,lightness)
    hue:ɫ�� ȡֵ0~360 3��ɫ�� ÿһ��120һ��ɫ��
    saturation:���Ͷ� 0.0%~100.0%
    linghtness:����0.0%~100.0%
+ 2.���ֺ���
    + round($value)��������
    + ceil($value)����ȡ��
    + floor($value)����ȡ��
    + max($v1,$v2,...)
    + min($v1,$v2...)
    + random() �����
+ 3.�ַ�������
    + 3.1
    unquote($string)ɾ���ַ���������
    quote($string)���ַ�����������
    To-upper-case()ת���ɴ�д
    To-lower-case()ת����Сд
    + 3.2�Զ��庯��
    ```
        @function ������($n){
                ������;
                @return ���;
        }
    ```
## �塢����ָ��
@if,@else if,@else
boolean����ʽ�������������ţ�Ҳ���Բ��ӡ�







