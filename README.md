# pandas.DataFrame.plot
数据分析工作日常需要使用不少的画图来做数据探索，尽管已经有matplolib/pychart/seaborn等优秀的第三方包，
但是使用pandas进行统计分析后，使用dataframe的plot画图能快速生成所需图像做探索已经能满足分析需要，故
在此对plot各功能进行研究探索


# 各参数说明如下：

官网：http://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.html

Eg.hexbin蜂巢图：http://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.plot.hexbin.html

x : label or position, default None#指数据列的标签或位置参数
y : label, position or list of label, positions, default None
kind : str#绘图类型
‘line’ : line plot (default)#折线图

‘bar’ : vertical bar plot#条形图。stacked为True时为堆叠的柱状图

‘barh’ : horizontal bar plot#横向条形图

‘hist’ : histogram#直方图（数值频率分布）

‘box’ : boxplot#箱型图

‘kde’ : Kernel Density Estimation plot#密度图，主要对柱状图添加Kernel 概率密度线

‘density’ : same as ‘kde’

‘area’ : area plot#与x轴所围区域图（面积图）。Stacked=True时，每列必须全部为正或负值，stacked=False时，对数据没有要求

‘pie’ : pie plot#饼图。数值必须为正值，需指定Y轴或者subplots=True

‘scatter’ : scatter plot#散点图。需指定X轴Y轴

‘hexbin’ : hexbin plot#蜂巢图。需指定X轴Y轴

ax : matplotlib axes object, default None#**子图(axes, 也可以理解成坐标轴) 要在其上进行绘制的matplotlib subplot对象。如果没有设置，则使用当前matplotlib subplot**其中，变量和函数通过改变figure和axes中的元素（例如：title,label,点和线等等）一起描述figure和axes，也就是在画布上绘图。
subplots : boolean, default False#是否对列分别作子图
sharex : boolean, default True if ax is None else False#如果ax为None，则默认为True，否则为False
In case subplots=True, share x axis and set some x axis labels to invisible; defaults to True if ax is None otherwise False if an ax is passed in; Be aware, that passing in both an ax and sharex=True will alter all x axis labels for all axis in a figure!

sharey : boolean, default False#如果有子图，子图共y轴刻度，标签
In case subplots=True, share y axis and set some y axis labels to invisible

layout : tuple (rows, columns) for the layout of subplots#子图的行列布局

figsize : a tuple (width, height) in inches#图片尺寸大小
use_index : boolean, default True#默认用索引做x轴
title : string#图片的标题用字符串
Title to use for the plot

grid : boolean, default None#图片是否有网格
legend : False/True/’reverse’#子图的图例 (默认为True)
style : list or dict#对每列折线图设置线的类型
logx : boolean, default False#设置x轴刻度是否取对数
logy : boolean, default False
loglog : boolean, default False#同时设置x，y轴刻度是否取对数
xticks : sequence#设置x轴刻度值，序列形式（比如列表）
对图无影响，只是改变坐标轴，如何改坐标轴的刻度Eg.转化为文字？

yticks : sequence#设置y轴刻度，序列形式（比如列表）
xlim : float/2-tuple/list#设置坐标轴的范围。数值（最小值），列表或元组（区间范围）
ylim : float/2-tuple/list
rot : int, default None#设置轴标签（轴刻度）的显示旋转度数  

fontsize : int, default None#设置轴刻度的字体大小
colormap : str or matplotlib colormap object, default None#设置图的区域颜色
colorbar : boolean, optional  #柱子颜色
If True, plot colorbar (only relevant for ‘scatter’ and ‘hexbin’ plots)

position : float  #条形图的对齐方式，取值范围[0,1]，即左下端到右上端默认0.5（中间对齐） 
layout : tuple (optional)  #布局。layout=(2, 3)两行三列，layout=(2, -1)两行自适应列数
Eg. df.plot(subplots=True, layout=(2, -1), sharex=False)

table : boolean, Series or DataFrame, default False  #图下添加表。如果为True，则使用DataFrame中的数据绘制表格，并且数据将被转置以满足matplotlib的默认布局。。
yerr : DataFrame, Series, array-like, dict and str
See Plotting with Error Bars for detail.

xerr : same types as yerr.
stacked : boolean, default False in line and bar plots, and True in area plot. If True, create stacked plot. #前面有介绍
sort_columns : boolean, default False  #对列名称进行排序以确定绘图顺序
secondary_y : boolean or sequence, default False  #设置第二个y轴（右辅助y轴）
Whether to plot on the secondary y-axis If a list/tuple, which columns to plot on secondary y-axis

mark_right : boolean, default True
When using a secondary_y axis, automatically mark the column labels with “(right)” in the legend

1.2 其他说明
1.2.1 其他参数
color:颜色
s:散点图大小
1.2.2 设置X、Y轴名称
ax.set_ylabel('yyy')

ax.set_xlabel('xxx')

1.2.3 plt.legend(loc='best')
loc:图列位置
1.3 其他画图步骤
1）首先定义画图的画布：fig = plt.figure( )

2）然后定义子图ax ，使用 ax= fig.add_subplot( 行，列，位置标)

3）用 ax.plot( )函数或者 df.plot(ax = ax)

4）结尾加plt.show()

注意：在jupternotebook 需要用%定义：%matplotlib notebook；如果是在脚本编译器上则不用，但是需要一次性按流程把代码写完
