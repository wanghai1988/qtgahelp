================================
 1 Getting Started (软件介绍)
================================

.. image:: ../images/mainform2.png
    :align: center 

1.1 Introduction (简介)
------------------------

地震（构造）大地测量软件（Tectonic Geodesy Applications, TGA）前身为2009年开发的活动断层地震危险性评估系统。该系统主要功能包括专业绘图、地壳形变和地震目录数据分析、地震位错格林函数计算、同震滑动分布和断层震间闭锁反演等，其中绘图功能基于美国ESRI公司的ArcObjects组件开发实现。由于ArcObjects只支持32位运行模式，导致软件的反演和模型分析能力受到制约。为此，2018年我们开始基于开源的QGIS软件研发64位版本，目标是为构造（地震）大地测量领域贡献一套集2D/3D专业绘图、形变和地震数据分析、地震位错格林函数计算和地震周期形变正/反演等功能为一体的软件。

本软件主要面向从事大地测量、地球物理和地质等方面工作的专业人员，最大的特点是易学易用，所见即所得。目前64位版本软件主要功能包括：

1. 通用和专业数据导入与显示，包括栅格数据、矢量数据、震源机制解、GNSS位移、旋转率、主应变率等；

2. 各类专题图制作，包括构造背景、InSAR形变、折中曲线、滑动分布、断层应力变化等；

3. 专业数据编辑，包括高程、形变、地震数据的提取，经纬度与UTM格式转换，栅格数据的裁剪、拼接、叠加、差分、降采样，以及InSAR数据的反缠绕与合成LOS位移等；

4. 专业数据分析，包括InSAR和DEM栅格数据分析、GNSS数据剖面分析，GNSS数据时序分析，地震目录数据分析等；

5. 断层3D几何模型构建，支持矩形位错元和三角形位错元剖分；

6. 格林函数计算，支持弹性半空间位错模型，以及区域分层地壳位错模型；

7. 同震和震后地表形变和库仑应力扰动计算；

8. 震间地表形变和断裂带应力积累速率计算。

此外，我们也非常欢迎大家基于我们的软件平台定制其他功能模块。如果您在软件使用过程遇到问题，欢迎加入QQ群讨论交流，群号为252716902。

1.2 Download (软件下载)
------------------------------------------------------------------------
:download:`TGA下载 <https://github.com/wanghai1988/TGA_Publish/releases/download/TGA7/TGA.rar>`  更新时间：2024年1月1日

:download:`测试数据下载 <https://github.com/wanghai1988/TGA_Data/archive/refs/tags/v1.zip>`

1.3 Runtime Environment (运行环境)
------------------------------------------------------------------------

(1) 操作系统：软件目前支持Windows 7/10/11 64位操作系统
(2) 依赖环境：

    * 软件运行需依赖 MATLAB R2020a，因此需要安装MATLAB R2020a软件或安装R2020a版本对应的MATLAB Runtime（:download:`下载地址 <https://ww2.mathworks.cn/products/compiler/matlab-runtime.html>`）
    * MATLAB R2020a软件建议全组件安装
    * 软件同时依赖VC++ Runtime，如果出现“找不到VCRUNTIME140_1.dll”类似错误，请参考下列解决方案：`解决方案1 <https://zhuanlan.zhihu.com/p/520529084>`_、`解决方案2 <https://www.bilibili.com/read/cv14363122/>`_

1.4 Data Files (数据文件)
------------------------------------

1.4.1 地图工程文件
~~~~~~~~~~~~~~~~~~

软件使用QGIS标准的.qgz与.qgs作为地图工程文件格式，类似 ArcGIS的.mxd文件，工程文件记录 了 一个工程所引用的图层、渲染样式及其他用 QGIS开发接口实现的配置信息。.qgz是二进制格式 ，.qgs则是 XML格式的文本文件，可以在普通的文本编辑器中直接进行编辑。

1.4.2 GDAL栅格数据
~~~~~~~~~~~~~~~~~~

软件使用QGIS封装的GDAL/OGR库进行GIS数据的独写。考虑到构造大地测量制图领域常用的数据格式，软件实现了对4种标准GDAL栅格格式的支持，如表2.1所示。其中，GTiff与HFA是GIS中最常用的两种栅格影像存储格式；STRMHGT是NASA航天飞机雷达地形任务（Shttle Radar Topographic Mission, SRTM）的DEM产品格式，该产品覆盖全球80%以上，由USGS免费分发；由于GDAL驱动的限制，软件对GMT NetCDF文件支持有体积上限，为2GB。

.. list-table:: 表2.1 软件支持的栅格地理空间数据格式
   :widths: 20 15 40
   :header-rows: 1

   * - GDAL代码
     - 后缀
     - 说明
   * - GTiff
     - tiff
     - 可以带有空间参考的TIF格式
   * - HFA
     - img
     - 常用于卫星影像数据
   * - SRTMHGT
     - hgt
     - SRTM高程数据
   * - GMT
     - grd
     - GMT常用的NetCDF网格文件

1.4.3 OGR矢量格式
~~~~~~~~~~~~~~~~~~

考虑到构造大地测量制图领域常用的数据格式，软件实现了对4种标准OGR矢量格式的支持，如表2.2所示。其中，ESRI shapefile是美国环境系统研究所公司（ESRI）开发的空间数据开放格式，该文件格式也是地理信息软件界的开放标准；GMT指的是GMT5新定义的OGR兼容格式，包含空间信息 、属性信息和元数据（包括版本号、空间投影等，使其可以被其他GIS软件调用，该格式的详细介绍可以参见 https://docs.gmt-china.org/latest/table/ogr/，非OGR兼容格式的旧版本GMT格式见1.2.4节；GeoJSON是近年来开始流行的地理空间数据格式，相比ESRI Shapefile，GeoJSON格式的数据更为简洁，并且是JSON格式的纯文本，更具可读性。

.. list-table:: 表2.2 软件支持的矢量地理空间数据格式
   :widths: 20 15 40
   :header-rows: 1

   * - OGR代码
     - 后缀
     - 说明
   * - ESRI Shapefile
     - shp
     - 应用最广泛的矢量GIS格式
   * - KML
     - kml 
     - Google Earth默认格式，基于XML
   * - GMT
     - gmt
     - GMT默认ASCII矢量格式       
   * - GeoJSON
     - geojson
     - 轻量级矢量格式，基于JSON


1.4.4 站点数据文件格式
~~~~~~~~~~~~~~~~~~

站点数据支持.nll和.nxy两种格式。
其中，.nll格式结构包括点位的站号（Name1）、别名（Name2）、经度（Long）与纬度（Lati），格式请参考 `站点数据格式.nll <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%AB%99%E7%82%B9%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.nll>`_ ，下面是一个简单的示例。

.. code-block:: go

     Name1  Name2  Long(deg)  Lati(deg)                                                 
       0      0     100.735    31.304 
       1      1     100.825    31.229  
       2      2     101.130    31.100  
       3      3     101.201    30.988  
       4      4     101.113    30.962   
       5      5     101.169    30.938

其次，.nxy格式结构包括点位的站号（Name1）、别名（Name2）、X坐标（X）与Y坐标（Y），其中XY为相对某点的相对坐标偏移量，格式请参考 `站点数据格式.nxy <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%AB%99%E7%82%B9%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.nxy>`_ ，下面是一个简单的示例。

.. code-block:: go

     Name1    Name2       X(m)              Y(m)  
     A-33      A-33       1084.11505761    -3646.41292
     S-1225    S-1225     3322.39191767     3409.499403
     1-A-4     1-A-4      73.97556776      -352.770468
     1-A-3     1-A-3      900.92929580     -380.454743
     C-31      C-31       3332.36216476     1627.343375

1.4.5 GNSS形变数据文件格式
~~~~~~~~~~~~~~~~~~

GNSS形变场（或速度场）的数据结构包括站点名（Site）、经度（Long）、纬度（Lati）、高程（H）、东方向形变（DisE）、北方向形变（DisN）、垂直向形变（DisH）、东方向标准差（SigE）、北方向标准差（SigN）、相关性系数（Corr）、垂直向误差（SigH）、以及站点的观测时间（Time）。文件后缀为 .gnss格式，示例格式请参考 `GNSS形变数据格式.gnss <https://github.com/wanghai1988/qtgahelp/edit/main/files/GNSS%E5%BD%A2%E5%8F%98%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.gnss>`_。时间格式为YYYY/MM/DD-YYYY/MM/DD，下面是一个简单的示例 。

.. code-block:: go

 Site          Long(deg)      Lati(deg)       H(m)    DisE(cm)  DisN(cm)  SigE(cm) SigN(cm)   Corr  DisH(cm)  SigH(cm)    Time
 BESI        84.38000000    28.22900000      0.000     0.170    -0.090     1.360    0.300   -0.0150  0.220    1.080       2010/04/17-2010/11/03
 BNDP        84.39510000    27.94950000      0.000     0.160    -0.050     0.320    0.300    0.0460  0.230    0.770       2010/04/17-2010/11/03
 CHLM        85.31410000    28.20720000      0.000    -0.130    -1.970     0.290    0.170   -0.0280  0.160    0.490       2010/04/17-2010/11/03
 CHWN        84.38540000    27.66830000      0.000     0.040    -0.040     0.550    0.240    0.0300  0.250    0.810       2010/04/17-2010/11/03
 DMAU        84.26500000    27.97300000      0.000     0.370    -0.050     0.750    0.250    0.0330  0.220    0.740       2010/04/17-2010/11/03

1.4.6 水准形变数据文件格式
~~~~~~~~~~~~~~~~~~~~

水准形变数据格式包括站点名（Site）、经度（Long）、纬度（Lati）、高程（H）、垂向形变（Val）、标准差（Sig）与观测时间（Time）。文件后缀为 .lev，格式请参考 `水准形变数据输入格式.lev <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%B0%B4%E5%87%86%E8%A7%82%E6%B5%8B%E6%95%B0%E6%8D%AE%E8%BE%93%E5%85%A5%E6%A0%BC%E5%BC%8F.lev>`_   。形变量与精度的单位不做要求，时间格式为YYYY/MM/DD-YYYY/MM/DD，下面是一个简单的示例。

.. code-block:: go

    Site	 Long(deg)	 Lati(deg)	 H(m)	 	 Val(cm)	 Sig(cm)	  Time
    SITEA	 96.153	 	 33.795	 	 11.866	 	 -2.632	 	 1.00	 	 2010/04/17-2010/11/03
    SITEB	 96.154	 	 33.770	 	 12.481	 	 -2.711	 	 1.00	 	 2010/04/17-2010/11/03
    SITEC	 96.155	 	 33.746	 	 13.140	 	 -2.794	 	 1.00	 	 2010/04/17-2010/11/03
    SITED	 96.156	 	 33.722	 	 13.845	 	 -2.884	 	 1.00	 	 2010/04/17-2010/11/03
    SITEE	 96.157	 	 33.697	 	 14.601	 	 -2.982	 	 1.00	 	 2010/04/17-2010/11/03

1.4.7 主应变率-旋转率场数据文件格式
~~~~~~~~~~~~~~~~~~~~

主应变率-旋转率场数据格式包括格网点的经纬度（Long、Lati）、最大应变率（E1）、最大应变率标准差（Sig1）、最小应变率（E2）、最小应变率标准差（Sig2）、方位角（Azi）、方位角标准差（Sig3）、旋转率值域（R）和旋转率标准差（Sig4），文件后缀为 .rsr，格式请参考 `主应变率-旋转率场数据输入格式.rsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E4%B8%BB%E5%BA%94%E5%8F%98%E7%8E%87-%E6%97%8B%E8%BD%AC%E7%8E%87%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rsr>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long(deg) Lati(deg) E1(nanostr/yr) Sig1(nanostr/yr) E2(nanostr/yr) Sig2(nanostr/yr) Azi(deg) Sig3(deg) R(nanorad/yr) Sig4(nanorad/yr)
    96.2403     23.7896      -2.24          0.69             16.55         0.34            99.64    1.12        22.3         0.3630

1.4.8 震源机制解数据文件格式
~~~~~~~~~~~~~~~~~~~~

震源机制解数据格式包括地震名称（Name）、震中经度（Long）、震中纬度（Lati）、深度（Depth）、矩震级（Mw）、两个P波初动节面的走向角（Strike1、Strike2）、倾角（Dip1、Dip2）和滑动角（Rake1、Rake2），以及发震的日期和时间（Datetime），文件后缀为 .fms，格式请参考 `震源机制解数据输入格式.fms <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E9%9C%87%E6%BA%90%E6%9C%BA%E5%88%B6%E8%A7%A3%E6%95%B0%E6%8D%AE%E8%BE%93%E5%85%A5%E6%A0%BC%E5%BC%8F.fms>`_ ，下面是一个简单的示例。

.. code-block:: go

    Name      Long(deg)  Lati(deg)  Depth(km)  Mw   Strike1(deg)  Dip1(deg)  Rake1(deg)  Strike2(deg)  Dip2(deg)  Rake2(deg)  Datetime
    Ludian    103.3400   27.0994    11.0       6.1  165           87           6            74         84         177         2014-08-03T00:00:00
    Jinggu    100.5000   23.3000     6.0       5.9  161           74         171           253         81          16         2014-12-06T18:20:00
    Kangding  101.7000   30.3000    18.0       6.3  140           82          -9           231         81        -172         2014-11-22T00:00:00

1.4.9 地壳分层模型数据文件格式
~~~~~~~~~~~~~~~~~~~~

地壳分层模型数据格式包括深度（Depth）、厚度（Thickness）、地震矩震级（Vp）、P波速度（Vp）、S波速度（Vs）、地壳密度（Rho）、和地壳粘度（Viscosity），文件后缀为 .lcm，格式请参考 `地壳分层模型格式输入格式.lcm <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E5%9C%B0%E5%A3%B3%E5%88%86%E5%B1%82%E6%A8%A1%E5%9E%8B.lcm>`_ ，下面是一个简单的示例。

.. code-block:: go

  Depth(km)  Thickness(km)  Vp(m/s)  Vs(m/s)  Rho(kg/m^3)  Viscosity(Pas)
      0.00          1.00     4500     2400     2.700E+3       0.0E+00
      1.00         10.00     6100     3500     2.750E+3       0.0E+00
     11.00         10.00     6300     3600     2.800E+3       0.0E+00
     21.00         10.00     6500     3700     2.850E+3       0.0E+00
     31.00         10.00     6700     3800     2.900E+3       0.0E+00
     41.00         30.00     8000     4600     3.300E+3       0.0E+00

1.4.10 断层分段参数数据文件格式
~~~~~~~~~~~~~~~~~~~~

断层分段参数数据格式包括起点经纬度（Long1、Lati1）、终点经纬度（Long2、Lati2）、深度（Depth）、走向（Strike）、宽度（Width）、倾角（Dip）、滑移（Slip）、滑移角（Rake）、张量（Tens）、上盘对应块体（HWBlock）、下盘对应块体（FWBlock），文件后缀为 .flt。请注意，每行数据表示一个断层分段格式，其中的多个宽度和倾角则表明该分段沿倾向存在变化，并且宽度和倾角必须是一一对应的。具体情况请参考 `断层分段参数数据格式.flt <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%96%AD%E5%B1%82%E5%88%86%E6%AE%B5%E5%8F%82%E6%95%B0%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.flt>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long1(deg)    Lati1(deg)    Long2(deg)    Lati2(deg)   Depth(km)  Strike(deg)   Width(km)   Dip(deg)   Slip(m) Rake(deg) Tens(cm)   HWBlock   FWBlock
   37.23435950   37.53685497   37.15368230   37.40391552    0.0000    205.801675   (20,30)       (30,60)    0.00    0.000     0.00      Unknown   Unknown
   37.15368230   37.40391552   37.11368539   37.25099322    0.0000    191.810497   (20,30,80)   (30,60,80)  0.00    0.000     0.00      Unknown   Unknown
   37.11368539   37.25099322   37.01368539   37.07778814    0.0000    210.000000   (20,40)       (30,60)    0.00    0.000     0.00      Unknown   Unknown
  

1.4.11 矩形位错模型数据文件格式
~~~~~~~~~~~~~~~~~~~~

矩形位错模型数据格式包括位错元左下角坐标经纬度（Long、Lati）、深度（H）、宽度（Width）、长度（Length）、走向（Strike）、倾角（Dip）、相对走滑分量（U1）、相对倾滑分量（U2）、相对张性错动分量（U3）、邻接矩形位错元序号（Adj1左、Adj2上、Adj3右、Adj4下）、上盘对应块体（HWBlock）、下盘对应块体（FWBlock），文件后缀为 .rec，格式请参考 `矩形位错模型数据格式.rec <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%9F%A9%E5%BD%A2%E4%BD%8D%E9%94%99%E6%A8%A1%E5%9E%8B%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rec>`_ ，下面是一个简单的示例。

.. code-block:: go

     Long(deg)     Lati(deg)        H(m)   Width(m)  Length(m) Strike(deg)   Dip(deg)   U1(cm)   U2(cm)   U3(cm)   Adj1   Adj2   Adj3   Adj4  HWBlock    FWBlock
  105.83200000   32.90600000  -2800.0000   2973.734   4005.421  220.006210  70.318103     0.00     0.00     0.00    0      0      0      0    Unknown    Unknown
  105.79900000   32.88300000  -2800.0000   2973.781   3936.298  218.735962  70.315615     0.00     9.00     0.00    0      0      0      0    Unknown    Unknown
  105.76600000   32.86000000  -2800.0000   2950.988   4006.567  219.955457  71.592503     0.00    27.00     0.00    0      0      0      0    Unknown    Unknown
  105.73300000   32.83800000  -2800.0000   2973.871   4007.155  219.929958  70.310744     0.00    14.00     0.00    0      0      0      0    Unknown    Unknown
  105.70000000   32.81500000  -2800.0000   2973.917   4007.743  219.904489  70.308248     0.00     6.00     0.00    0      0      0      0    Unknown    Unknown 
  
1.4.12 三角位错模型数据文件格式
~~~~~~~~~~~~~~~~~~~~

三角位错模型数据格式包括三个顶点经纬度和深度（Long1、Lati1、H1、Long2、Lati2、H2、Long3、Lati3、H3）、相对走滑分量（U1）、相对倾滑分量（U2）、相对张性错动分量（U3）、邻接三角位错元序号（Adj1、Adj2、Adj3）、上盘对应块体（HWBlock）、下盘对应块体（FWBlock），文件后缀为 .tri，格式请参考 `三角位错模型数据格式.tri <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%9F%A9%E5%BD%A2%E4%BD%8D%E9%94%99%E6%A8%A1%E5%9E%8B%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rec>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long1(deg)    Lati1(deg)        H1(m)    Long2(deg)    Lati2(deg)        H2(m)    Long3(deg)    Lati3(deg)        H3(m)    Strike(deg)   Dip(deg)   U1(cm)   U2(cm)   U3(cm)  Adj1  Adj2  Adj3  HWBlock    FWBlock
   96.28032985   33.29127015       0.0000   96.29874568   33.28819664       0.0000   96.27967682   33.28850310   -1975.3767    220.006210   70.318103   2.30     1.97     0.00     0     0    49    Unknown    Unknown
   96.29874568   33.28819664       0.0000   96.31716005   33.28516345       0.0000   96.29806497   33.28543415   -1975.3767    218.735962   70.315615   0.06     2.39     0.00    49     0    50    Unknown    Unknown
   96.31716005   33.28516345       0.0000   96.33557420   33.28188167       0.0000   96.31645166   33.28240573   -1975.3767    219.955457   71.592503   0.00     3.03     0.00    50     0    51    Unknown    Unknown
   96.33557420   33.28188167       0.0000   96.35399779   33.27585936       0.0000   96.33483814   33.27912848   -1975.3767    219.929958   70.310744   2.16     2.64     0.00    51     0    52    Unknown    Unknown

1.4.13 InSAR LOS形变数据文件格式
~~~~~~~~~~~~~~~~~~~~

InSAR LOS形变数据格式包括经度（Long）、纬度（Lati）、高程（H）、视线向距离（LOS）、 方位角（Azi）、入射角（Inc）、标准差（Sig），文件后缀为 .los，格式请参考 `InSAR LOS形变数据.los <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%20LOS%E5%BD%A2%E5%8F%98%E6%95%B0%E6%8D%AE.los>`_ ，下面是一个简单的示例。
注：LOS（cm）数据视线向距离缩短为正值，视线向距离拉长为负值。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)      Sig(cm)
    36.16833496    39.70527649       0.00    -19.727  -171.21905518    48.28219604       0.00
    36.59500122    39.70527649       0.00    -12.799  -170.94995117    46.37073517       0.00
    36.91500092    39.59860992       0.00      1.063  -170.72946167    44.77532578       0.00
    37.12833405    39.59860992       0.00    -18.749  -170.59454346    43.73011398       0.00
    
1.4.14 InSAR方位向偏移数据文件格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移数据格式包括经度（Long）、纬度（Lati）、高程（H）、视线方向形变（LOS）、 方位角（Azi）、入射角（Inc）、标准差（Sig），文件后缀为 .aos ，格式请参考 `InSAR方位向偏移量数据.aos <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E6%96%B9%E4%BD%8D%E5%90%91%E5%81%8F%E7%A7%BB%E9%87%8F%E6%95%B0%E6%8D%AE.aos>`_ ，下面是一个简单的示例。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)      Sig(cm)
    35.91361237    38.48583221       0.00      0.224   -10.04328918    39.39117432       0.00
    36.34027863    38.48583221       0.00      0.389    -9.77897644    41.53480530       0.00
    36.76694489    38.48583221       0.00      0.405    -9.51591492    43.55602646       0.00
    37.19361115    38.48583221       0.00      0.169    -9.25372314    45.49477768       0.00
    
1.4.15 InSAR距离向偏移数据文件格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移数据格式包括经度（Long）、纬度（Lati）、高程（H）、视线方向形变（LOS）、 方位角（Azi）、入射角（Inc）、标准差（Sig），文件后缀为 .ros ，格式请参考 `InSAR距离向偏移量数据.ros <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E8%B7%9D%E7%A6%BB%E5%90%91%E5%81%8F%E7%A7%BB%E9%87%8F%E6%95%B0%E6%8D%AE.ros>`_ ，下面是一个简单的示例。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)      Sig(cm)
    35.91361237    38.48583221       0.00     -0.050   -10.04328918    39.39117432       0.00
    36.34027863    38.48583221       0.00     -0.101    -9.77897644    41.53480530       0.00
    36.76694489    38.48583221       0.00     -0.182    -9.51591492    43.55602646       0.00
    37.19361115    38.48583221       0.00     -0.313    -9.25372314    45.49477768       0.00

1.4.16 InSAR数据线性改正参数文件格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移量数据格式包括文件名（File_Name）、经度（Long）、纬度（Lati）、大地经度参数（Param_L）、大地纬度参数（Param_B）、常量（Constant），文件后缀为 .lcp ，格式请参考 `InSAR数据线性项改正参数文件.lcp <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E6%95%B0%E6%8D%AE%E7%BA%BF%E6%80%A7%E9%A1%B9%E6%94%B9%E6%AD%A3%E5%8F%82%E6%95%B0%E6%96%87%E4%BB%B6.lcp>`_ ，下面是一个简单的示例。（注：第一列占40个字符）

.. code-block:: go

      File_Name                                  Long(deg)     Lati(deg)     Param_L       Param_B       Constant
      aoff_20220916_20230217.phs-DS-AI            37.676       37.426        0.0             0.0             0.0
      aoff_20230128-20230229-Clipped-DS-AI        36.676       37.151        0.0             0.0             0.0
      aoff_20230129-20230210-Clipped-DS-AI        37.322       37.278        0.0             0.0             0.0


1.4.17 折中曲线数据文件格式
~~~~~~~~~~~~~~~~~~~~

折中曲线数据格式包括平滑因子（S-Factor）、粗糙度（Roughness）、均方根误差（RMSE），文件后缀为 .toc ，格式请参考 `Trade-off曲线数据格式.toc <https://github.com/wanghai1988/qtgahelp/blob/main/files/Trade-off%E6%9B%B2%E7%BA%BF%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.toc>`_ ，下面是一个简单的示例。

.. code-block:: go

  S-Factor   Roughness   RMSE(cm)                                                 
     10.00      0.0075    0.5446
      8.00      0.0101    0.5345
      6.00      0.0147    0.5188
      4.00      0.0229    0.4961
      2.00      0.0489    0.4451


1.4.18 断层应力变化数据文件格式
~~~~~~~~~~~~~~~~~~~~

断层应力变化数据格式包括经度（Long）、纬度（Lati）、深度（Depth）、断层宽度（Width）、长度（Length）、走向角（Strike）、倾角（Dip）、滑动角（Rake）、库伦破坏应力（CFS）、标准差（Sig）、拉梅常数（Lambda、Mu）、摩擦系数（F），文件后缀为.cfsr ，格式请参考 `断层应力变化数据格式.cfsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%96%AD%E5%B1%82%E5%BA%94%E5%8A%9B%E5%8F%98%E5%8C%96%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.cfsr>`_ ，下面是一个简单的示例。

.. code-block:: go

     Long(deg)      Lati(deg)  Depth(m)   Width(m)  Length(m) Strike(deg)   Dip(deg)  Rake(deg)      CFS(Pa)     Sig(Pa)      Lambda          Mu    F
  105.31203951   29.27487069   -669.13   1000.000   1000.000  132.364334    42.0000    90.0000   1.2413E+04   0.0000E+00  3.0000E+10  3.0000E+10  0.4
  105.30688218   29.26992042  -1338.26   1000.000   1000.000  132.364334    42.0000    90.0000   9.8236E+03   0.0000E+00  3.0000E+10  3.0000E+10  0.4
  105.30172535   29.26496994  -2007.39   1000.000   1000.000  132.364334    42.0000    90.0000   9.2805E+03   0.0000E+00  3.0000E+10  3.0000E+10  0.4
  105.29656902   29.26001926  -2676.52   1000.000   1000.000  132.364334    42.0000    90.0000   7.5787E+03   0.0000E+00  3.0000E+10  3.0000E+10  0.4


1.4.19 活动块体运动和应变参数文件格式
~~~~~~~~~~~~~~~~~~~~


活动块体运动和应变参数数据格式包括块体名称（Name）、块体质心经纬度（Long、Lati）、东西向旋转矢量及对应标准差（R_X、Sig1）、南北向旋转矢量及对应标准差（R_Y、Sig2）、垂直向旋转矢量及对应标准差（R_Z、Sig3）、东西向线应变率及标准差（S_X、Sig4）、南北向线应变率及标准差（S_Y、Sig5）、剪应变率及标准差（S_XY、Sig6），文件后缀为.blc ，格式请参考 `活动块体运动和应变参数数据格式.blc <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%B4%BB%E5%8A%A8%E5%9D%97%E4%BD%93%E8%BF%90%E5%8A%A8%E5%92%8C%E5%BA%94%E5%8F%98%E5%8F%82%E6%95%B0%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.blc>`_ ，下面是一个简单的示例。

.. code-block:: go

   Name      Long(deg)    Lati(deg)  R_X(nanorad/yr)  Sig1(nanorad/yr)  R_Y(nanorad/yr)  Sig2(nanorad/yr)  R_Z(nanorad/yr)  Sig3(nanorad/yr)  S_X(nanorad/yr)  Sig4(nanorad/yr)  S_Y(nanorad/yr)  Sig5(nanorad/yr) S_XY(nanorad/yr)   Sig6(nanorad/yr)
  huanan            103.699       27.794         -0.3899     0        0.896         0       0.6872        0       -0.0788        0        0.0262        0       0.1541       0
  chuandian         101.349       27.873        -1.5409      0        2.0235        0       1.7521        0       -0.0039        0        -0.1018       0       0.2024       0   


1.4.20 地震目录数据文件格式
~~~~~~~~~~~~~~~~~~~~
地震目录数据格式包括发震震源的经度（Long）、纬度（Lati）、深度（Depth）、震源标度类型（M_Type）、震级（Mag）、发震日期（Datetime），文件后缀为.etc ，格式请参考 `地震目录数据.etc
<https://github.com/wanghai1988/qtgahelp/blob/main/files/%E5%9C%B0%E9%9C%87%E7%9B%AE%E5%BD%95%E6%95%B0%E6%8D%AE.etc>`_ ，下面是一个简单的示例。

.. code-block:: go

     Long(deg)    Lati(deg)	 Depth(km)	 M_Type      Mag	         Datetime
     -116.3493     37.1320	    -17.6	    Mw	     5.6	    2023-08-06T02:33:59
     -116.3679     37.1689	    -21.8	    Mw	     1.2	    2023-08-06T02:38:40
     -116.3846     37.1715	    -18.6	    Mw	     2.0	    2023-08-06T02:39:15
     -116.3778     37.1613	     -9.0	    Mw	     2.1	    2023-08-06T02:40:59


1.4.21 二进制数据说明文件
~~~~~~~~~~~~~~~~~~~~~~~~

二进制文件主要用于存储栅格数据，如InSAR干涉图和DEM数据等，每个二进制数据都要求有一个对应的头文件。GAMMA等 SAR软件处理获取的地面形变信息以二进制形式存储。要将形变信息在地图上显示，需要将其转换为软件支持的栅格格式。二进制文件不包含任何范围、分辨率等信息，因此在使用时需要搭配记录了必要信息的头文件。二进制数据后缀为 .bin，头文件后缀为 .rsc。头文件记录了二进制数据起始点（左上角像元）的经纬度、最大灰度值、最小灰度值、经向步长、纬向步长、像元行数、像元列数以及像元格式。像元格式包括16位整形、 32位浮点型或 64位浮点型3种，分别使用“int16”、 “float”、“double”标记。输入格式请参考 `栅格头文件输入格式.rsc <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%A0%85%E6%A0%BC%E5%A4%B4%E6%96%87%E4%BB%B6%E8%BE%93%E5%85%A5%E6%A0%BC%E5%BC%8F.rsc>`_ ，下面是一个简单的示例。

.. code-block:: go

    ROW		5400
    COLUMN		4950
    TOPLEFT_X	103.000
    X_STEP		0.000277777777777778
    TOPLEFT_Y	33.900
    Y_STEP		-0.000277777777777778
    DATA_FORMAT	float



1.5 Coordinate Systems (坐标系统)
------------------------------------

软件使用的地理坐标系统（Geographic Coordinate System）为World Geodetic System 1984（简称WGS84）,其EPSG编码为4326。软件使用的投影坐标系统（Projected Coordinate System）为高斯克吕格投影（Gauss-Kruger projection）。在加载数据时，如果数据本身带有坐标系统，软件会采用动态投影自动转换至当前坐标系统下，也可采用系统提供的坐标转换工具进行转换，如：`Gauss Projection:EN2XY（高斯投影:经纬度转投影坐标） <https://qtgahelpdoc.readthedocs.io/en/latest/2%20Menus%20%28%E8%8F%9C%E5%8D%95%29.html#gauss-projection-en2xy>`_、`Gauss Projection:XY2EN（高斯投影:投影坐标转经纬度） <https://qtgahelpdoc.readthedocs.io/en/latest/2%20Menus%20%28%E8%8F%9C%E5%8D%95%29.html#gauss-projection-xy2en>`_ 和 `Reference Frame Conversion（参考框架转换） <https://qtgahelpdoc.readthedocs.io/en/latest/2%20Menus%20%28%E8%8F%9C%E5%8D%95%29.html#reference-frame-conversion>`_。


1.6 Version Update History (版本更新历史)
------------------------------------

==========  =============  ====== 
 版本号      更新时间       更新内容 
==========  =============  ====== 
 v1.0        2024年1月1日  1. 修改已知BUG 
                           2. 添加功能1
 v1.1        2024年3月1日  1. 修改已知BUG 
                           2. 添加功能2 
==========  =============  ======
