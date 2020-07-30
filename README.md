# pandas.DataFrame.plot
数据分析工作日常需要使用不少的画图来做数据探索，尽管已经有matplolib/pychart/seaborn等优秀的第三方包，
但是使用pandas进行统计分析后，使用dataframe的plot画图能快速生成所需图像做探索已经能满足分析需要，故
在此对plot各功能进行研究探索


# 各参数说明如下：
Init signature: pd.DataFrame.plot(data)
Docstring:     
Make plots of Series or DataFrame.

Uses the backend specified by the
option ``plotting.backend``. By default, matplotlib is used.

Parameters
----------
data : Series or DataFrame
    The object for which the method is called.
x : label or position, default None
    Only used if data is a DataFrame.
y : label, position or list of label, positions, default None
    Allows plotting of one column versus another. Only used if data is a
    DataFrame.
kind : str
    The kind of plot to produce:

    - 'line' : line plot (default)
    - 'bar' : vertical bar plot
    - 'barh' : horizontal bar plot
    - 'hist' : histogram
    - 'box' : boxplot
    - 'kde' : Kernel Density Estimation plot
    - 'density' : same as 'kde'
    - 'area' : area plot
    - 'pie' : pie plot
    - 'scatter' : scatter plot
    - 'hexbin' : hexbin plot.

figsize : a tuple (width, height) in inches
use_index : bool, default True
    Use index as ticks for x axis.
title : str or list
    Title to use for the plot. If a string is passed, print the string
    at the top of the figure. If a list is passed and `subplots` is
    True, print each item in the list above the corresponding subplot.
grid : bool, default None (matlab style default)
    Axis grid lines.
legend : bool or {'reverse'}
    Place legend on axis subplots.
style : list or dict
    The matplotlib line style per column.
logx : bool or 'sym', default False
    Use log scaling or symlog scaling on x axis.
    .. versionchanged:: 0.25.0

logy : bool or 'sym' default False
    Use log scaling or symlog scaling on y axis.
    .. versionchanged:: 0.25.0

loglog : bool or 'sym', default False
    Use log scaling or symlog scaling on both x and y axes.
    .. versionchanged:: 0.25.0

xticks : sequence
    Values to use for the xticks.
yticks : sequence
    Values to use for the yticks.
xlim : 2-tuple/list
ylim : 2-tuple/list
rot : int, default None
    Rotation for ticks (xticks for vertical, yticks for horizontal
    plots).
fontsize : int, default None
    Font size for xticks and yticks.
colormap : str or matplotlib colormap object, default None
    Colormap to select colors from. If string, load colormap with that
    name from matplotlib.
colorbar : bool, optional
    If True, plot colorbar (only relevant for 'scatter' and 'hexbin'
    plots).
position : float
    Specify relative alignments for bar plot layout.
    From 0 (left/bottom-end) to 1 (right/top-end). Default is 0.5
    (center).
table : bool, Series or DataFrame, default False
    If True, draw a table using the data in the DataFrame and the data
    will be transposed to meet matplotlib's default layout.
    If a Series or DataFrame is passed, use passed data to draw a
    table.
yerr : DataFrame, Series, array-like, dict and str
    See :ref:`Plotting with Error Bars <visualization.errorbars>` for
    detail.
xerr : DataFrame, Series, array-like, dict and str
    Equivalent to yerr.
mark_right : bool, default True
    When using a secondary_y axis, automatically mark the column
    labels with "(right)" in the legend.
include_bool : bool, default is False
    If True, boolean values can be plotted.
backend : str, default None
    Backend to use instead of the backend specified in the option
    ``plotting.backend``. For instance, 'matplotlib'. Alternatively, to
    specify the ``plotting.backend`` for the whole session, set
    ``pd.options.plotting.backend``.

    .. versionadded:: 1.0.0

**kwargs
    Options to pass to matplotlib plotting method.

Returns
-------
:class:`matplotlib.axes.Axes` or numpy.ndarray of them
    If the backend is not the default matplotlib one, the return value
    will be the object returned by the backend.

Notes
-----
- See matplotlib documentation online for more on this subject
- If `kind` = 'bar' or 'barh', you can specify relative alignments
  for bar plot layout by `position` keyword.
  From 0 (left/bottom-end) to 1 (right/top-end). Default is 0.5
  (center)
