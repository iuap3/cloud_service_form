## 如何使用金额控件？

用友云表单V3.0除了增加了一些新控件外，还提升了一些控件自身的功能，金额控件就是其中之一，新的金额控件较之前版本增加了如下功能：当金额控件在子表中，除了可以求列合计外，增加了求最大值、最小值和平均值的功能。

### 1、 金额控件在设计器中的位置：



控件页签的系统分类下面，如图一所示。

![](/articles/form/4-2/images/image_je01.png)

图一



### 2、 金额控件的属性：



如图二所示。

![](/articles/form/4-2/images/image_je02.png)


图二



小数位数：取值范围0-2，默认值为2；



显示金额大写：定义是否将该控件的值显示为中文大写金额，勾选为显示大写金额，默认不勾选；



计算：定义该控件的值是否为通过计算取得。勾选为通过计算获得，默认不勾选；



最大值：定义该字段的最大取值，为空时不控制；



最小值：定义该字段的最小取值，为空时则不控制；



列运算：当金额控件位于明细子表布局上时的特有属性，用于定义该列是否需要求合计、最大值、最小值及平均值；



主表字段：当金额控件位于明细子表布局上时的特有属性，用于将上面定义的列运算的值保存到主表的某个字段上，待选字段为主表上的所有数值或金额型字段；



子表中是否显示：当金额控件位于明细子表布局上时的特有属性，用于定义在子表上是否将列运算的值显示出来，默认勾选；



当勾选了计算属性后，界面如图三所示。



![](/articles/form/4-2/images/image_je03.png)

图三



取值后面的下拉框显示的是当前表单内主表范围内/或某个子表范围内，除当前选中控件外的所有数值和金额控件。



系统支持以下计算：



当前字段的取值等于常量；



当前字段的取值等于某个数值或金额字段的值；



当前字段的取值等于某几个数值或金额字段的简单四则运算后的结果；



### 3、 主表金额控件的计算：



金额控件可以位于主表，也可以位于子表。两者在功能上有些许不同。下面分别来讲解一下。



如图四所示，图中的”金额合计“是个金额控件，位于主表。金额合计=已付金额+未付金额，我们看下这个该如何设置。



![](/articles/form/4-2/images/image_je04.png)




图四



a、在设计器中选中控件“金额合计”，在右边的属性区，勾选“计算”属性；



b、“取值=”后面的下拉框中显示出默认的常量、以及主表上的两个金额字段：未付金额、已付金额，我们选择已付金额；



c、点击标记②处的“+”，界面增加运算符（标记③处）及另一行待选字段，这里我们选择未付字段；



运算符支持+、-、*、/，默认是只显示“+”，点击“+”会全部展开；



点击标记②处的“+”可以继续添加字段，直至添加完所需字段，点击标记②处的垃圾桶则删除不需要的字段；



运行态如图五所示。通过计算得出来的金额合计是不可编辑的。

![](/articles/form/4-2/images/image_je05.png)


图五



### 4、 子表金额控件的计算：



位于子表的金额控件，除了提供和主表一样的功能外，根据其子表的自身特性，提供了求列合计、最大值、最小值及平均值的功能，同时还可以将子表列的计算结果保存到主表的某个字段中。



如图六所示，子表”合计“是金额控件，合计=单价*数量，该列求合计，并将合计结果保存到主表的”子表合计金额“字段中，显示中文大子表不显示合计；数量列求最大值，结果不传入子表字段，子表显示求出的最大值；我们看下这个例子该如何设置：



![](/articles/form/4-2/images/image_je06.png)


图六



a、在设计器的明细子表布局中选中控件“合计”（图中的①标识），在右边的属性区，勾选“计算”属性；



b、按前面的方法定义：合计=单价*数量；



c、勾选“列运算”，默认选“合计”（图中的②标识）；



d、设置列合计传入的主表字段（图中的③标识）：点开主表字段的下拉框，里面列示出主表中所有的数值和金额字段，选中要传入的字段--子表合计金额；



e、根据实际情况设置子表中是否需要将列运算的结果显示出来（图中的④标识），这个例子是不在子表中显示，所以需要去掉勾选；



f、设置子表合计金额大写：在主表中增加字段“子表合计金额大写”，将其值设置为等于“子表合计金额”字段，同时勾选“显示金额大写”，如图七所示

![](/articles/form/4-2/images/image_je07.png)


图七



g、设置子表中数量字段的列运算如图八，列运算选取最大值，主表字段不选，在子表中显示。



![](/articles/form/4-2/images/image_je08.png)


图八



运行态如图九所示。子表传入到主表的数据及转换的金额大写在运行态均不可编辑。

![](/articles/form/4-2/images/image_je09.png)


图九




































