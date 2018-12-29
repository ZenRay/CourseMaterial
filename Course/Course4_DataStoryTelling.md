**目录**

[TOC]

在进入第四课程之后，将从艺术的角度来探讨数据可视化的内容，而使用的工具将是 Tableau——Tableau制作数据可视化并进行沟通也并非难事，整个过程只需要极少（甚至不需要）任何代码，并且学习曲线非常平滑。导学的内容不以 Tableau 的使用角度来探讨，重点还是关注怎么样用艺术的角度去设计数据可视化。

## $\rm I$. 可视化叙事

可视化对信息的表达，不仅仅是之前的信息表达，而且可以更加注重用户和数据的交互。叙事性更强调数据信息结合特定语境，来表达数据信息。换句话说就是需要关注怎么以讲故事的方式来表达数据信息，因此在做分析时需要以下面的信息作为参考：

* 数据内容背景了解——哪些数据可以表达出观点信息
* 分析得到的结果面向的受众
* 什么样的可视化可以表达出观点
* 描述观点要思考合适性

## $\rm II$. 可视化设计

### 2.1 基本思路

数据可视化需要合适的方式将数据元素进行组合，以表达数据需要传达出的意思。就像语言表达有专门的语法规则一样，图表的表达还是有相应的规则。主要可选择的可视化思路，见下图:

![](https://apandre.files.wordpress.com/2011/02/chartchooserincolor.jpg)

对于不同图形的选择，首先需要弄清楚需要使用图形表达什么观点、图形变量是一中什么关系——双变量关系、分布关系还是比较。以上关系能够明确选择什么图形来表达观点，之后才是思考需要什么样的方式才能让读者或者观众能够快速而准确理解表达的意思。需要强调一点在可视化的选择思路，另外还需要关注一下**数据类型**。

### 2.2 常见图形信息解读

常见的图表有以下几种，无需要更多“花哨高端“即可满足绝大部分需要



![image-20181229193104576](https://ws3.sinaimg.cn/large/006tNbRwgy1fynudxt4ruj30ax0723z6.jpg)



- 简单文本

只有一两个数据进行分享时，完全不需要任何图表，只是用数字（尽可能突出）配合辅助性的文字是最清晰有效的

- 表格（包括热力图）

展示多维度的数据，让受众根据需要自行选择关注的点。

热力图是表格的变种，通过单色（注意不要使用多种颜色）的饱和度突出数值的变化。表格注意淡化边框（窄边框或无边框）

- 散点图

展示两件事情的关系，观察是否存在及何种关系，往往配合平均线或趋势线进行使用

- 折线图

暗示点之间存在离散数据（一系列数据分割成不同类别）间没有的联系，通常，连续性数据都以时间为单位

- 柱状图

柱状图的应用广泛，可以代替饼图表示百分比，也可以直观地利用长短比较数据大小 

- 斜率图

适用于两个时间段或两组对比数据点，无需解释线的意义和具体变化是多少而直接展示数据的提升或下降以及变化速度（斜率），唯一的缺点是缺少绝对值

- 瀑布图

抽离堆叠条形图的一部分进行重点关注，展示最终数据的组成或其中上升下降等变化 

- 面积图

比较极大的数值变化时更实用

### ~~2.3 图形评价——作为了解~~

评价一个图形的有效性可以从以下几个角度:

1. 数据墨水比例(Data Ink Ratio)

   > 数据墨水公式：$data\_ink\_ratio\ =\ \frac{ink\_used\_describe\_data}{ink\_used\_describe\_everything\_else}$

2. 失真系数(Lie Factor)

   > 失真系数，指图表中展示的效果大小除以数据中展示的效果大小的比例。数学表达式：${line\_factor}\ =\ \frac{size\_of\_the\_effect\_shown\_in\_the\_graph}{size\_of\_the\_effect\_shown\_in\_the\_the\_data}$。一般理想的失真系数要求在0.95和1.05之间，当然最理想的值是1

### 2.4 图表垃圾——chartjunk

根据Edward Tufte在**《定量信息的视觉呈现》**中的描述：用于装饰图形的大量墨水并没有告诉读者更多的信息。装饰的目的各不相同，有些是为了使图形看起来更加科学和精准，有些是为了使图形更加生动，有些是为了让设计人员有机会练习艺术技能。无论什么原因，用到的都是非数据墨水或冗余数据墨水，通常都是些图表垃圾。

在数据可视化中的图表垃圾，<font color="red">主要包括**多余的表格线**、**非必要的文本**、**装饰的图标轴**、**图形中嵌入了图片**以及**其他阴影和3D效果**展示</font>。