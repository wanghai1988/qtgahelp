================================
 1 Getting Started (软件介绍)
================================

.. image:: ../images/mainform2.png
    :align: center  

1.1 Overview (概述)
------------------------

构造大地测量软件（Tectonic Geodesy Applications, TGA）为64位应用程序，其前身为2009年开发的32位活动断层地震危险性评估系统。该32位软件集绘图、数据分析、格林函数计算和大地测量反演为一体，其中绘图功能基于美国ESRI公司的ArcObjects组件开发实现。在2016年前该软件称为活动断层地震危险性评估系统，随着功能的不断增加和完善，软件现更名为构造大地测量应用软件。

目前32位软件已获得国家发明专利和软件著作权登记各一项（软件著作权登记号：2010SR056240；发明专利号：ZL 2016 1 0975859.3），并在期刊测绘学报上发表了该软件系统的主要功能（2012，41（5），661-669）。但是，由于ArcObjects只支持32位运行模式，导致软件的反演和模型分析能力受到制约。为此，自2018年开始基于开源的QGIS软件研发64位版本。

这套软件主要面向地震、科研院所和高校等系统中从事大地测量、地质和地球物理等方面工作的专业人员，目前软件主要功能包括：

(1) 实现基础 GIS数据浏览功能，包括栅格和矢量数据浏览、渲染，属性表查看，支持多种地图投影。
(2) 数据兼容：提供广泛的数据格式支持，包括常用GIS数据，以及GIS中很少用到但构造大地测量工作者非常熟悉的GMT数据格式。
(3) 快速成图：实现活动断层、形变场、主应变率、块体旋转率、震源机制解和地震目录数据的快速绘制，提供制图过程必需的地图符号，提供比例尺、图例、指北针等必需的布局元素、
(4) 绘图准确：绘图过程中的数据处理结果准确，符号标注、图例、比例尺、坐标注记的信息正确无误。
(5) 可以指定格式输出：在地图制作完成后，可以将结果输出为矢量格式或指定分辨率的栅格格式。

1.2 Download (软件下载)
------------------------------------------------------------------------
:download:`TGA下载 <https://github.com/wanghai1988/TGA_Publish/releases/download/TGA4/QTGA.zip>`

1.3 Runtime Environment (运行环境)
------------------------------------------------------------------------

(1) 操作系统：软件目前支持Windows 7/10/11 64位操作系统
(2) 依赖环境：

    * 软件运行需依赖 MATLAB R2020a，因此需要安装MATLAB R2020a软件或安装R2020a版本对应的MATLAB Runtime（:download:`下载地址 <https://ww2.mathworks.cn/products/compiler/matlab-runtime.html>`）
    * 软件同时依赖VC++ Runtime，如果出现“找不到VCRUNTIME140_1.dll”类似错误，请参考下列解决方案：`解决方案1 <https://zhuanlan.zhihu.com/p/520529084>`_、`解决方案2 <https://www.bilibili.com/read/cv14363122/>`_

1.4 Data Files (数据格式)
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


1.4.4 站点数据格式
~~~~~~~~~~~~~~~~~~

站点数据支持.nll和.nxy两种格式。
其中，.nll格式结构包括点位的站号（Name1）、别名（Name2）、经度（Long）与纬度（Lat），格式请参考 `站点数据格式.nll <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%AB%99%E7%82%B9%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.nll>`_ ，下面是一个简单的示例。

.. code-block:: go

     Name1  Name2  Long(deg)  Lat(deg)                                                 
       0      0     100.735    31.304 
       1      1     100.825    31.229  
       2      2     101.130    31.100  
       3      3     101.201    30.988  
       4      4     101.113    30.962   
       5      5     101.169    30.938

其次，.nxy格式结构包括点位的站号（Name1）、别名（Name2）、X坐标（X）与Y坐标（Y），其中XY为相对某点的相对坐标偏移量，格式请参考 `站点数据格式.nxy <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%AB%99%E7%82%B9%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.nxy>`_ ，下面是一个简单的示例。

.. code-block:: go

     Name1    Name2       X(m)              Y(m)  Relative to Well 82 (-115.535169E, 32.712321N)
     A-33      A-33       1084.11505761    -3646.41292
     S-1225    S-1225     3322.39191767     3409.499403
     1-A-4     1-A-4      73.97556776      -352.770468
     1-A-3     1-A-3      900.92929580     -380.454743
     C-31      C-31       3332.36216476     1627.343375

1.4.5 GNSS形变数据格式
~~~~~~~~~~~~~~~~~~

GNSS形变场（或速度场）的数据结构包括站点名（Site）、经度（Long）、纬度（Lat）、高程（H）、东方向形变（DisE）、北方向形变（DisN）、高程形变（DisH）、东方向误差（SigE）、北方向误差（SigN）、高程误差（SigH）、误差相关系数（Corr）、以及站点的观测时间（Date）。文件后缀为 .gps格式，示例格式请参考 `GNSS形变数据格式.gps <https://github.com/wanghai1988/qtgahelp/blob/main/files/GNSS%E5%BD%A2%E5%8F%98%E6%A0%BC%E5%BC%8F%E7%A4%BA%E4%BE%8B.gps>`_。时间格式为YYYY/MM/DD-YYYY/MM/DD，下面是一个简单的示例 。

.. code-block:: go

 Site          Long(deg)      Lat(deg)       H(m)    DisE(cm)  DisN(cm)  DisH(cm)  SigE(cm) SigN(cm) SigH(cm)   Corr       Date
 BESI        84.38000000    28.22900000      0.000     0.170    -0.090     1.360    0.300    0.220    1.080   -0.0150     2010/04/17-2010/11/03
 BNDP        84.39510000    27.94950000      0.000     0.160    -0.050     0.320    0.300    0.230    0.770    0.0460     2010/04/17-2010/11/03
 CHLM        85.31410000    28.20720000      0.000    -0.130    -1.970     0.290    0.170    0.160    0.490   -0.0280     2010/04/17-2010/11/03
 CHWN        84.38540000    27.66830000      0.000     0.040    -0.040     0.550    0.240    0.250    0.810    0.0300     2010/04/17-2010/11/03
 DMAU        84.26500000    27.97300000      0.000     0.370    -0.050     0.750    0.250    0.220    0.740    0.0330     2010/04/17-2010/11/03

1.4.6 水准形变场格式
~~~~~~~~~~~~~~~~~~~~

水准形变场数据格式包括站点名（Site）、经度（Long）、纬度（Lati）、高程（H）、垂向形变（Val）、形变精度（Sig）与观测时间（Date）。文件后缀为 .lev，格式请参考 `水准形变数据输入格式.lev <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%B0%B4%E5%87%86%E8%A7%82%E6%B5%8B%E6%95%B0%E6%8D%AE%E8%BE%93%E5%85%A5%E6%A0%BC%E5%BC%8F.lev>`_   。形变量与精度的单位不做要求，时间格式为YYYY/MM/DD-YYYY/MM/DD，下面是一个简单的示例。

.. code-block:: go

    Site	 Long(deg)	 Lati(deg)	 H(m)	 	 Val(cm)	 Sig(cm)	 Date
    SITEA	 96.153	 	 33.795	 	 11.866	 	 -2.632	 	 1.00	 	 2010/04/17-2010/11/03
    SITEB	 96.154	 	 33.770	 	 12.481	 	 -2.711	 	 1.00	 	 2010/04/17-2010/11/03
    SITEC	 96.155	 	 33.746	 	 13.140	 	 -2.794	 	 1.00	 	 2010/04/17-2010/11/03
    SITED	 96.156	 	 33.722	 	 13.845	 	 -2.884	 	 1.00	 	 2010/04/17-2010/11/03
    SITEE	 96.157	 	 33.697	 	 14.601	 	 -2.982	 	 1.00	 	 2010/04/17-2010/11/03

1.4.7 主应变率-旋转率场格式
~~~~~~~~~~~~~~~~~~~~

主应变率-旋转率场数据格式包括格网点的经纬度（Long、Lati）、最大应变率（E1）、最大应变率中误差（Sig1）、最小应变率（E1）、最小应变率其误差（Sig2）、最小应变率中误差（E2）、方位角（Azi）、方位角中误差（Sig3）、旋转率值域（R）和旋转率中误差（Sig4），文件后缀为 .rsr，格式请参考 `主应变率-旋转率场数据输入格式.rsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E4%B8%BB%E5%BA%94%E5%8F%98%E7%8E%87-%E6%97%8B%E8%BD%AC%E7%8E%87%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rsr>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long(deg) Lati(deg) E1(nanostr/yr) Sig1(nanostr/yr) E2(nanostr/yr) Sig2(nanostr/yr) Azi(deg) Sig3(deg) R(nanorad/yr) Sig4(nanorad/yr)
    96.2403     23.7896      -2.24          0.69             16.55         0.34            99.64    1.12        22.3         0.3630

1.4.8 震源机制解格式
~~~~~~~~~~~~~~~~~~~~

震源机制解数据格式包括地震名称（Name）、震中经度（Long）、震中纬度（Lati）、深度（Depth）、地震矩震级（Mw）、两个P波初动节面的走向角（Strike1、Strike2）、倾角（Dip1、Dip2）和滑动角（Rake1、Rake2），以及发震的日期和时间（Datetime），文件后缀为 .fms，格式请参考 `震源机制解数据输入格式.fms <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E9%9C%87%E6%BA%90%E6%9C%BA%E5%88%B6%E8%A7%A3%E6%95%B0%E6%8D%AE%E8%BE%93%E5%85%A5%E6%A0%BC%E5%BC%8F.fms>`_ ，下面是一个简单的示例。

.. code-block:: go

    Name      Long(deg)  Lati(deg)  Depth(km)  Mw   Strike1(deg)  Dip1(deg)  Rake1(deg)  Strike2(deg)  Dip2(deg)  Rake2(deg)  Datetime
    Ludian    103.3400   27.0994    11.0       6.1  165           87           6            74         84         177         2014/8/3T00:00:00
    Jinggu    100.5000   23.3000     6.0       5.9  161           74         171           253         81          16         2014/12/6T18:20:00
    Kangding  101.7000   30.3000    18.0       6.3  140           82          -9           231         81        -172         2014/11/22T00:00:00

1.4.9 地壳分层模型格式
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

1.4.10 断层分段参数格式
~~~~~~~~~~~~~~~~~~~~

断层分段参数数据格式包括起点经纬度（Long1、Lati1）、终点经纬度（Long2、Lati2）、深度（Depth）、走向（Strike）、宽度（Width）、顶层倾角（TopDip）、底层倾角（BotDip）、滑移（Slip）、滑移角（Rake）、张量（Tens）、HWBlock、FWBlock，文件后缀为 .flt，格式请参考 `断层分段参数数据格式.flt <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%96%AD%E5%B1%82%E5%88%86%E6%AE%B5%E5%8F%82%E6%95%B0%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.flt>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long1(deg)    Lati1(deg)    Long2(deg)    Lati2(deg) Depth(km) Strike(deg) Width(km) TopDip(deg) BotDip(deg) Slip(m) Rake(deg) Tens(cm)      HWBlock      FWBlock
   87.36489159   26.56198134   83.80978174   27.84850670   4.06267     292     58.0000       7.000       7.000    0.00     0.000     0.00      Unknown      Unknown
   87.59000719   27.04039405   84.02205743   28.33249466  11.13109     292     12.0000       8.000      10.000    0.00     0.000     0.00      Unknown      Unknown
   87.63660082   27.13881977   84.06598377   28.43209409  13.00811     292    140.0000      11.000      11.000    0.00     0.000     0.00      Unknown      Unknown
  

1.4.11 矩形位错模型格式
~~~~~~~~~~~~~~~~~~~~

矩形位错模型数据格式包括经度（Long）、纬度（Lati）、高度（Z）、宽度（Width）、长度（Length）、走向（Strike）、倾角（Dip）、相对走滑分量（U1）、相对倾滑分量（U2）、相对张性错动分量（U3）、分段（Seg）、行（Row）、列（Col），文件后缀为 .rec，格式请参考 `矩形位错模型数据格式.rec <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%9F%A9%E5%BD%A2%E4%BD%8D%E9%94%99%E6%A8%A1%E5%9E%8B%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rec>`_ ，下面是一个简单的示例。

.. code-block:: go

     Long(deg)     Lati(deg)        Z(m)   Width(m)  Length(m) Strike(deg)   Dip(deg)   U1(cm)   U2(cm)   U3(cm)  Seg  Row  Col
  105.83200000   32.90600000  -2800.0000   2973.734   4005.421  220.006210  70.318103     0.00     0.00     0.00    0    0    0
  105.79900000   32.88300000  -2800.0000   2973.781   3936.298  218.735962  70.315615     0.00     9.00     0.00    0    0    0
  105.76600000   32.86000000  -2800.0000   2950.988   4006.567  219.955457  71.592503     0.00    27.00     0.00    0    0    0
  105.73300000   32.83800000  -2800.0000   2973.871   4007.155  219.929958  70.310744     0.00    14.00     0.00    0    0    0
  105.70000000   32.81500000  -2800.0000   2973.917   4007.743  219.904489  70.308248     0.00     6.00     0.00    0    0    0 
  
1.4.12 三角位错模型格式
~~~~~~~~~~~~~~~~~~~~

三角位错模型数据格式包括三个顶点经纬度和高度（Long1、Lati1、Z1、Long2、Lati2、Z2、Long3、Lati3、Z3）、相对走滑分量（U1）、相对倾滑分量（U2）、相对张性错动分量（U3）、Adj1、Adj2、Adj3，文件后缀为 .tri，格式请参考 `三角位错模型数据格式.tri <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E7%9F%A9%E5%BD%A2%E4%BD%8D%E9%94%99%E6%A8%A1%E5%9E%8B%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rec>`_ ，下面是一个简单的示例。

.. code-block:: go

    Long1(deg)    Lati1(deg)        Z1(m)    Long2(deg)    Lati2(deg)        Z2(m)    Long3(deg)    Lati3(deg)        Z3(m)   U1(cm)   U2(cm)   U3(cm)  Adj1  Adj2  Adj3
   96.28032985   33.29127015       0.0000   96.29874568   33.28819664       0.0000   96.27967682   33.28850310   -1975.3767     2.30     1.97     0.00     0     0    49
   96.29874568   33.28819664       0.0000   96.31716005   33.28516345       0.0000   96.29806497   33.28543415   -1975.3767     0.06     2.39     0.00    49     0    50
   96.31716005   33.28516345       0.0000   96.33557420   33.28188167       0.0000   96.31645166   33.28240573   -1975.3767     0.00     3.03     0.00    50     0    51
   96.33557420   33.28188167       0.0000   96.35399779   33.27585936       0.0000   96.33483814   33.27912848   -1975.3767     2.16     2.64     0.00    51     0    52

1.4.13 InSAR LOS形变格式
~~~~~~~~~~~~~~~~~~~~

InSAR LOS形变数据格式包括经度（Long）、纬度（Lati）、高度（H）、视线方向形变（LOS）、 方位角（Azi）、入射角（Inc）、均方根误差（RMSE），文件后缀为 .los，格式请参考 `InSAR LOS形变数据.los <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%20LOS%E5%BD%A2%E5%8F%98%E6%95%B0%E6%8D%AE.los>`_ ，下面是一个简单的示例。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)     RMSE(cm)
    36.16833496    39.70527649       0.00    -19.727  -171.21905518    48.28219604       0.00
    36.59500122    39.70527649       0.00    -12.799  -170.94995117    46.37073517       0.00
    36.91500092    39.59860992       0.00      1.063  -170.72946167    44.77532578       0.00
    37.12833405    39.59860992       0.00    -18.749  -170.59454346    43.73011398       0.00
    
1.4.14 InSAR方位向偏移量格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移量数据格式包括经度（Long）、纬度（Lati）、高度（H）、视线方向形变（LOS）、 方位角（Azi）、入射角（Inc）、均方根误差（RMSE），文件后缀为 .aos ，格式请参考 `InSAR方位向偏移量数据.aos <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E6%96%B9%E4%BD%8D%E5%90%91%E5%81%8F%E7%A7%BB%E9%87%8F%E6%95%B0%E6%8D%AE.aos>`_ ，下面是一个简单的示例。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)     RMSE(cm)
    35.91361237    38.48583221       0.00      0.224   -10.04328918    39.39117432       0.00
    36.34027863    38.48583221       0.00      0.389    -9.77897644    41.53480530       0.00
    36.76694489    38.48583221       0.00      0.405    -9.51591492    43.55602646       0.00
    37.19361115    38.48583221       0.00      0.169    -9.25372314    45.49477768       0.00
    
1.4.15 InSAR距离向偏移量格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移量数据格式包括经度（Long）、纬度（Lati）、高度（H）、视线方向形变（LOS）、 方位角（Azi）、入射角（Inc）、均方根误差（RMSE），文件后缀为 .ros ，格式请参考 `InSAR距离向偏移量数据.ros <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E8%B7%9D%E7%A6%BB%E5%90%91%E5%81%8F%E7%A7%BB%E9%87%8F%E6%95%B0%E6%8D%AE.ros>`_ ，下面是一个简单的示例。

.. code-block:: go

      Long(deg)      Lati(deg)       H(m)    LOS(cm)      Azi(deg)       Inc(deg)     RMSE(cm)
    35.91361237    38.48583221       0.00     -0.050   -10.04328918    39.39117432       0.00
    36.34027863    38.48583221       0.00     -0.101    -9.77897644    41.53480530       0.00
    36.76694489    38.48583221       0.00     -0.182    -9.51591492    43.55602646       0.00
    37.19361115    38.48583221       0.00     -0.313    -9.25372314    45.49477768       0.00

1.4.16 InSAR数据线性项改正参数格式
~~~~~~~~~~~~~~~~~~~~

InSAR方位向偏移量数据格式包括文件名（File_Name）、经度（Long）、纬度（Lati）、大地经度参数（Param_L）、大地纬度参数（Param_B）、常量（Constant），文件后缀为 .lct ，格式请参考 `InSAR数据线性项改正参数文件.lct <https://github.com/wanghai1988/qtgahelp/blob/main/files/InSAR%E6%95%B0%E6%8D%AE%E7%BA%BF%E6%80%A7%E9%A1%B9%E6%94%B9%E6%AD%A3%E5%8F%82%E6%95%B0%E6%96%87%E4%BB%B6.lct>`_ ，下面是一个简单的示例。（注：第一列占40个字符）

.. code-block:: go

      File_Name                                  Long(deg)     Lati(deg)     Param_L       Param_B       Constant
      aoff_20220916_20230217.phs-DS-AI            37.676       37.426        0.0             0.0             0.0
      aoff_20230128-20230229-Clipped-DS-AI        36.676       37.151        0.0             0.0             0.0
      aoff_20230129-20230210-Clipped-DS-AI        37.322       37.278        0.0             0.0             0.0


1.4.17 Trade-off曲线数据格式
~~~~~~~~~~~~~~~~~~~~

Trade-off曲线数据格式包括S因子（S-Factor）、粗糙度（Roughness）、均方根误差（RMSE），文件后缀为 .toc ，格式请参考 `Trade-off曲线数据格式.toc <https://github.com/wanghai1988/qtgahelp/blob/main/files/Trade-off%E6%9B%B2%E7%BA%BF%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.toc>`_ ，下面是一个简单的示例。

.. code-block:: go

  S-Factor   Roughness   RMSE(cm)                                                 
     10.00      0.0075    0.5446
      8.00      0.0101    0.5345
      6.00      0.0147    0.5188
      4.00      0.0229    0.4961
      2.00      0.0489    0.4451


  
1.4.17 二进制文件
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

软件使用的地理坐标系统（Geographic Coordinate System）为World Geodetic System 1984（简称WGS84）,其EPSG编码为4326。软件使用的投影坐标系统（Projected Coordinate System）为高斯克吕格投影（Gauss-Kruger projection）。在加载数据时，如果数据本身带有坐标系统，软件会采用动态投影自动转换至当前坐标系统下。

