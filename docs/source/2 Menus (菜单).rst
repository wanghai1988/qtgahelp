================
2 Menus (菜单)
================


    
2.1 File (文件)
---------------
.. image:: ../images/menu_image/File/menu_file_new.png
    :align: center  

File菜单下包括下列功能：

2.1.1 Open Map（打开地图工程）
~~~~~~~~~~~~~~~~~~

该菜单会打开文件打开对话框，用来打开已经存在的地图工程（后缀为.qgs/.qgz/.QGS/.QGZ），界面如下：

    .. image:: ../images/menu_image/File/dialog_openproject.png
        :align: center
    
2.1.2 Save（保存）
~~~~~~~~~~~~~~~~~~

该菜单用于保存当前地图工程（后缀为.qgs/.qgz/.QGS/.QGZ），如果当前为新建地图工程时，会弹出地图工程保存对话框，界面如下：

    .. image:: ../images/menu_image/File/dialog_saveproject.png
        :align: center
        
2.1.3 Save as（另存为）
~~~~~~~~~~~~~~~~~~

该菜单用于另存当前工程为新的地图工程（后缀为.qgs/.qgz/.QGS/.QGZ），点击后会弹出地图工程另存对话框，界面如下：

    .. image:: ../images/menu_image/File/dialog_saveas.png
        :align: center

2.1.4 Close Map（关闭地图工程）
~~~~~~~~~~~~~~~~~~

该菜单用于关闭当前地图工程

2.1.5 Open Recent（最近工程）
~~~~~~~~~~~~~~~~~~

该菜单用于显示用户最近打开过的地图工程列表

2.1.6 Add Raster Layer（添加栅格图层）
~~~~~~~~~~~~~~~~~~

该菜单用于添加栅格类型地图数据（后缀为.tif/.img/.grd等），点击后会弹出添加栅格数据对话框，界面如下：

    .. image:: ../images/menu_image/File/dailog_addRasterLayer.png
        :align: center
        
2.1.7 Add Vector Layer（添加矢量图层）
~~~~~~~~~~~~~~~~~~

该菜单用于添加矢量类型地图数据（后缀为.shp/.geojson/.kml等），点击后会弹出添加矢量数据对话框，界面如下：

    .. image:: ../images/menu_image/File/dailog_addVectorLayer.png
        :align: center
        
2.1.8 Add Online Map（添加在线地图）
~~~~~~~~~~~~~~~~~~

该菜单用于添加在线地图服务图层如天地图、谷歌地图、ERSI等在线地图服务，界面如下：

    .. image:: ../images/menu_image/File/menu_onlineMap_new.png
        :align: center
        
2.1.9 Export（输出）
~~~~~~~~~~~~~~~~~~

该菜单用于输出当前地图视图，包含2个子菜单，界面如下：

    .. image:: ../images/menu_image/File/menu_export.png
        :align: center
    
  1. 点击Export Map View（输出地图视图），会弹出输出地图视图对话框，用于保存并输出当前地图视图的屏幕效果。
    
    .. image:: ../images/menu_image/File/dailog_exportMapView.png
        :align: center
    参数说明：
    
    * Extent（范围）通过当前地图视图自动进行确定，用户也可以通过手动输入、Calculate from Layer（由图层计算）、Map Canvas Extent（地图画布范围）或Draw on Canvas（手动绘制）自行确定输出的视图范围。
        
    * Scale（比例尺）通常由视图范围自动确定，也可以通过手动输入进行调整。
        
    * Resolution（分辨率）默认为96dpi，用户也可根据自身需要进行调整。
        
    * Output Width（输出宽度）和Output Height（输出高度）用来确定输出图片的尺寸。
        
    * 点击按钮Export（输出）后，会弹出图片保存对话框，用户可自行设置保存路径与格式。
        
  2. 点击Export Layout View（输出布局视图），会弹出布局操作窗口，用于编辑并保存通过布局视图美化后的地图布局效果，详细操作请参考 `2.8 Cartography (制图)`_。
  
    .. image:: ../images/menu_image/File/dialog_setLayoutView.png
        :align: center
    
    

    
2.1.10 Exit（退出）
~~~~~~~~~~~~~~~~~~

2.2 Plot (绘制)
----------------

Plot (绘制)菜单主要包括Focal Mechanism（震源机制）、 GNSS Displacement（GNSS形变场）、Leveling Displacement（水准形变场）等15项绘制功能，如图所示：

.. image:: ../images/menu_image/Plot/menu_plot.png
    :align: center

具体包括下列功能：

2.2.1 Focal Mechanism（震源机制）
~~~~~~~~~~~~~~~~~~

    震源机制对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_FocalMechanism.png
        :align: center
    
    使用步骤：
    
    STEP 1：选择或输入 `震源机制解数据（后缀为.fms） <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#id6>`_ 路径 
 
    STEP 2：设置Sytle（样式）和Scale（比例）。其中Style用于设置图标绘制方式，可选项为ALL（全部）、Strike Slip（走滑断层）、Thrust（冲断层）、Normal（正断层）；Scale用于设置图标比例，设置范围为0.01-99
    
    STEP 3：点击Preview（预览）按钮，即可在地图界面查看显示效果
    
    STEP 4：设置输出文件路径（文件格式为geojson），点击Export（输出）按钮即可输出结果文件，勾选Add File To Current Project（添加文件到当前工程）则会将结果文件添加到当前地图工程内。
    
    .. image:: ../images/menu_image/Plot/result_FocalMechanism.png
        :align: center


2.2.2 GNSS Displacement（GNSS形变场）
~~~~~~~~~~~~~~~~~~

    GNSS形变场对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_GNSSDisplacement.png
        :align: center
    
    使用步骤：
    
    STEP 1：选择或输入 `GNSS形变数据（后缀为.gps） <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#gnss>`_ 路径 
 
    STEP 2：设置Draw Error Ellipse（绘制误差椭圆）、Ellipse Scale（椭圆比例）和Arrow Scale（箭头比例）
      * Draw Error Ellipse（绘制误差椭圆）用于设置是否绘制误差椭圆
      * Ellipse Scale（椭圆比例）用于设置绘制误差椭圆的比例，设置范围为0.01-99.99（注：该选项仅在Draw Error Ellipse勾选时起效）
      * Arrow Scale（箭头比例）其中Style用于设置绘制箭头的比例，设置范围为0.01-99.99
    
    STEP 3：点击Preview（预览）按钮，即可在地图界面查看显示效果
    
    STEP 4：设置输出文件路径（文件格式为geojson），点击Export（输出）按钮即可输出结果文件，勾选Add File To Current Project（添加文件到当前工程）则会将结果文件添加到当前地图工程内。
    
    .. image:: ../images/menu_image/Plot/result_GNSSDisplacement.png
        :align: center


2.2.3 Leveling Displacement（水准形变场）
~~~~~~~~~~~~~~~~~~
    水准形变场对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_LevelingDisplacement.png
        :align: center

    使用步骤：
    
    STEP 1：选择或输入 `水准形变场数据（后缀为.lev） <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#id3>`_ 路径 
 
    STEP 2：设置Draw Error Circle（绘制误差圆）和Scale（比例）
      * 勾选Draw Error Circle（绘制误差圆）后可绘制绘制误差圆
      * Scale用于设置绘制比例，设置范围为0.01-99.99
    
    STEP 3：点击Preview（预览）按钮，即可在地图界面查看显示效果
    
    STEP 4：设置输出文件路径（文件格式为geojson），点击Export（输出）按钮即可输出结果文件，勾选Add File To Current Project（添加文件到当前工程）则会将结果文件添加到当前地图工程内。
    
    .. image:: ../images/menu_image/Plot/result_LevelingDisplacement.png
        :align: center


2.2.4 Ratation Rate（旋转率场）
~~~~~~~~~~~~~~~~~~
    旋转率场对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_RotationRate2.png
        :align: center

    使用步骤：
    
    STEP 1：选择或输入 `主应变率-旋转率场数据输入格式.rsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E4%B8%BB%E5%BA%94%E5%8F%98%E7%8E%87-%E6%97%8B%E8%BD%AC%E7%8E%87%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rsr>`_ 路径 
 
    STEP 2：设置Radius（半径）、Radius Scale（半径比例）、Angle Unit（角度单位）、Stroke Color（划线颜色）、Fill Color（填充颜色）
      * Angle Scale（角度比例），设置范围为0.01-99.99
      * Radius（半径），设置范围为0.01-99.99
      * Angle Unit（角度单位），设置范围为0.01-99.99
      * Radius Scale（半径比例），设置范围为0.01-99.99
      * Stroke Color（划线颜色），默认设置为黑色
      * Fill Color（填充颜色），默认设置为透明
    
    STEP 3：点击Preview（预览）按钮，即可在地图界面查看显示效果
    
    STEP 4：设置输出文件路径（文件格式为geojson），点击Export（输出）按钮即可输出结果文件，勾选Add File To Current Project（添加文件到当前工程）则会将结果文件添加到当前地图工程内。
    
    .. image:: ../images/menu_image/Plot/result_RotationRate2.png
        :align: center


2.2.5 Principal Strain Rate（主应变率）
~~~~~~~~~~~~~~~~~~
    主应变率对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_PrincipalStrainRate2.png
        :align: center
    
    使用步骤：
    
    STEP 1：选择或输入 `主应变率-旋转率场数据输入格式.rsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E4%B8%BB%E5%BA%94%E5%8F%98%E7%8E%87-%E6%97%8B%E8%BD%AC%E7%8E%87%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.rsr>`_ 路径 
 
    STEP 2：设置Scale（比例）、Line Width（线宽）、Head Length（箭头长度）、Head Width（箭头宽度）、Fill Color（填充颜色）
      * Scale（比例），用于设置绘制比例，设置范围为0.01-99.99
      * Line Width（线宽）用于设置箭头后的线段长度，设置范围为0.01-99.99
      * Head Length（箭头长度），用于设置箭头长度，设置范围为0.01-99.99
      * Head Width（箭头宽度），用于设置箭头宽度，设置范围为0.01-99.99    
      * Fill Color（填充颜色），用于设置箭头填充颜色，默认设置为黑色
    
    STEP 3：点击Preview（预览）按钮，即可在地图界面查看显示效果
    
    STEP 4：设置输出文件路径（文件格式为geojson），点击Export（输出）按钮即可输出结果文件，勾选Add File To Current Project（添加文件到当前工程）则会将结果文件添加到当前地图工程内。
    
    .. image:: ../images/menu_image/Plot/result_PrincipalStrainRate2.png
        :align: center

2.2.6 Raster Data Profile（栅格数据剖面分析）
~~~~~~~~~~~~~~~~~~
    点击 Raster Data Profile（栅格数据剖面分析）按钮后，主界面添加一个数据展示面板，左侧为剖面图，右侧为数据表格，效果如下：
    
    .. image:: ../images/menu_image/Plot/panel_RasterDataProfile.png
        :align: center
    
    使用步骤：
    
    STEP 1：通过File（文件）菜单的Add Raster Layer（添加栅格图层）按钮，添加栅格数据
 
    STEP 2：在面板中Layer（图层）下拉列表中选择需要进行剖面分析的栅格图层
    
    STEP 3：点击下拉列表旁的分析按钮，此时鼠标会变为十字状，即可在地图视图中的栅格数据上绘制出剖面线（鼠标左键画线，右键结束），如图所示：
    
    .. image:: ../images/menu_image/Plot/reault_RasterDataProfile1.png
        :align: center
    
    STEP 4：当剖面线绘制结束后，系统自动绘制出剖面图和对应数据列表，如图所示：
    
    .. image:: ../images/menu_image/Plot/reault_RasterDataProfile2.png
        :align: center

2.2.7 GNSS Velocity Profile（GNSS速度场剖面分析）
~~~~~~~~~~~~~~~~~~
    GNSS速度场剖面分析对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_GNSSVelocityProfile.png
        :align: center
    
    使用步骤：
    
    STEP 1：选择或输入 `GNSS速度场格式（后缀为.gps） <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#gnss>`_ 路径 
 
    STEP 2：设置Reference Ellipsoid（参考椭球）、L0（研究区中央经线）、Azimuth（方位角）、Original E（初值东方向）、Original N（初始北方向）、Unit（单位）、Component（构成方向）
      * Reference Ellipsoid（参考椭球），可设置为WGS-84（默认）、Krassovsky Ellipsoid、International Ellipsoid 1975椭球
      * L0（研究区中央经线），设置范围为0.00-360
      * Azimuth（方位角）,设置范围为0.00-99.99
      * Original E（初值东方向）,设置范围为0.00-360.00
      * Original N（初始北方向）,设置范围为0.00-360.00
      * Unit（单位）,可根据数据自行设置，默认为mm
      * Component（构成方向）,可设置为parallel（横向）、vertical（竖向）
    
    STEP 3：点击Plot（绘制）按钮，即可在新弹出的图表窗口中看到效果
    
    STEP 4：点击Export（输出）按钮，设置输出文件路径后，即可输出结果文件（文件格式为.gvp）。
    
    .. image:: ../images/menu_image/Plot/reault_GNSSVelocityProfile.png
        :align: center

2.2.8 Leveling Displacement Profile（水准形变场剖面分析）
~~~~~~~~~~~~~~~~~~

    暂缺

2.2.9 L/U Curve（L/U曲线）
~~~~~~~~~~~~~~~~~~
    L/U曲线绘制对话框界面如下：
    
    .. image:: ../images/menu_image/Plot/dialog_LUCurve.png
        :align: center
    
    使用步骤：
    
    STEP 1：选择或输入 `Trade-off曲线数据格式.toc <https://github.com/wanghai1988/qtgahelp/blob/main/files/Trade-off%E6%9B%B2%E7%BA%BF%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.toc>`_ 路径 
 
    STEP 2：点击Plot（绘制）按钮，即可在新弹出的图表窗口中看到效果
    
    .. image:: ../images/menu_image/Plot/reault_LUCurve.png
        :align: center


2.2.10 GNSS Time Series（GNSS时间序列）
~~~~~~~~~~~~~~~~~~
    GNSS时间序列对话框界面如下：
    
     .. image:: ../images/menu_image/Plot/dialog_GNSSTimeSeries.png
        :align: center   

    **使用步骤：**

    STEP 1：选择或输入 `TMS数据（后缀为.tms）暂缺 <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#gnss>`_ 路径 
 
    STEP 2：设置Unit（单位）、Start Date（起始日期）、Axis Unit（坐标轴单位）
        * Unit（单位），可根据数据自行设置，默认为mm
        * Start Date（起始日期），该参数由系统从数据自动读取，用户也可手动设置
        * Axis Unit（坐标轴单位），可设置为Day或Year，默认为Day
    
        STEP 3：点击Plot（绘制）按钮，即可在新弹出的图表窗口中看到效果

    .. image:: ../images/menu_image/Plot/result_GNSSTimeSeries.png
        :align: center

2.2.11 Stress Change on Fault（断层应力变化）
~~~~~~~~~~~~~~~~~~

    断层应力变化对话框界面如下：
    
     .. image:: ../images/menu_image/Plot/dailog_StressChangeonFault.png
        :align: center   

    **使用步骤：**

    STEP 1：选择或输入 `断层应力变化数据格式.cfsr <https://github.com/wanghai1988/qtgahelp/blob/main/files/%E6%96%AD%E5%B1%82%E5%BA%94%E5%8A%9B%E5%8F%98%E5%8C%96%E6%95%B0%E6%8D%AE%E6%A0%BC%E5%BC%8F.cfsr>`_ 路径 
 
    STEP 2：设置Reference Ellipsoid（参考椭球）、L0（研究区中央经线）、Unit（单位）
      * Reference Ellipsoid（参考椭球），可设置为WGS-84（默认）、Krassovsky Ellipsoid、International Ellipsoid 1975椭球
      * L0（研究区中央经线），设置范围为0.00-360
      * Unit（单位），可自行设置，默认为KPa/yr
    
    STEP 3：点击Plot（绘制）按钮，即可在新弹出的图表窗口中看到效果（暂缺）

    .. image:: ../images/menu_image/Plot/reault_StressChangeonFault.png
        :align: center

2.2.12 Slip Distribution（滑动分布）
~~~~~~~~~~~~~~~~~~

    滑动分布对话框界面如下：
    
     .. image:: ../images/menu_image/Plot/dailog_SlipDistribution.png
        :align: center   

    **使用步骤：**

    STEP 1：选择或输入 `位错模型数据格式（后缀为.rec或.tri）暂缺 <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#gnss>`_ 路径 
 
    STEP 2：设置Reference Ellipsoid（参考椭球）、L0（研究区中央经线）、Scale（比例）、Draw Allow（绘制箭头）
      * Reference Ellipsoid（参考椭球），可设置为WGS-84（默认）、Krassovsky Ellipsoid、International Ellipsoid 1975椭球
      * L0（研究区中央经线），设置范围为0.00-360
      * Scale用于设置绘制比例，设置范围为0.01-99.99
      * Draw Allow（绘制箭头）用于设置是否绘制箭头
    
    STEP 3：点击Draw（绘制）按钮，即可在新弹出的图表窗口中看到效果

    .. image:: ../images/menu_image/Plot/result_SlipDistribution.png
        :align: center



2.2.13 Interseismic Coupling Model（震间耦合模型）
~~~~~~~~~~~~~~~~~~

    暂缺

2.2.14 Depth Profile of Earthquakes（地震深度剖面）
~~~~~~~~~~~~~~~~~~

    地震深度剖面对话框界面如下：
    
     .. image:: ../images/menu_image/Plot/dailog_SlipDistribution.png
        :align: center   


2.2.15 Temporal Variation of Earthquakes（地震时间变化）
~~~~~~~~~~~~~~~~~~

    地震时间变化对话框界面如下：
    
     .. image:: ../images/menu_image/Plot/dialog_TemporVariationofEarthquakes.png
        :align: center
        

    **使用步骤：**

    STEP 1：选择或输入 `地震目录数据格式（后缀为.etc）暂缺 <https://qtgahelpdoc.readthedocs.io/en/latest/1%20Getting%20Started%20%28%E8%BD%AF%E4%BB%B6%E4%BB%8B%E7%BB%8D%29.html#gnss>`_ 路径 
 
    STEP 2：设置Start Time（起始时间）、End Time（结束时间）、Unit（单位）
      * 根据数据设置对应的时间区间
      * 单位（Unit）可以设置为Hour（小时）、Day（日）、Year（年）
    
    STEP 3：点击Plot（绘制）按钮，即可在新弹出的图表窗口中看到效果

     .. image:: ../images/menu_image/Plot/reault_TemporVariationofEarthquakes.png
        :align: center

2.3 Tools (工具)
-----------------
Tools (工具)菜单主要包括Data Extract（数据提取）、Construct Fault Geometry（构造断层几何）、Construct Checkboard Test Model（构造棋盘测试模型）等15项功能，如图所示。

.. image:: ../images/menu_image/Tools/menu_tools.png
   :align: center

具体包括下列功能：

2.3.1 Data Extract（数据提取）
~~~~~~~~~~~~~~~~~~

    Data Extract（数据提取）菜单包括了：Extract Elevation Data（提取高程数据）、Extract Incidence/Azimuth Angle（提取入射角/方位角）、Extract Fault Segment Parameters（提取断层段参数）等8个子菜单，如图所示。

    .. image:: ../images/menu_image/Tools/btnMenu_DataExtract.png
       :align: center

  1. Extract Elevation Data（提取高程数据）

    该功能通过DEM栅格数据和InSAR偏移量栅格数据提取范围内的高程点

     .. image:: ../images/menu_image/Tools/dailog_ExtractElevationData.png
        :align: center

    **使用步骤：**

    STEP 1：选择或输入DEM栅格数据和InSAR偏移量栅格数据路径

     .. image:: ../images/menu_image/Tools/dialog_ExtractElevationData2.png
        :align: center

    STEP 2：点击Extract（提取）按钮，弹出成功提示框后，再点击Export（输出）按钮即可导出结果

     .. image:: ../images/menu_image/Tools/result_ExtractElevationData1.png
        :align: center

  2. Extract Incidence/Azimuth Angle（提取入射角/方位角）

    该功能通过入射角栅格数据、方位角栅格数据、数据误差、InSAR数据提取范围内的提取入射角/方位角点数据

     .. image:: ../images/menu_image/Tools/dailog_IncidenceAzimuthAngle.png
        :align: center

    **使用步骤：**

    STEP 1：选择或输入Inc Angle（入射角）栅格数据、Azi Angle（方位角）栅格数据、Data Error（数据误差）文件、InSAR数据路径以及导出文件路径

     .. image:: ../images/menu_image/Tools/dialog_IncidenceAzimuthAngle2.png
        :align: center

    STEP 2：点击Extract（提取）按钮，弹出成功提示框后，即可保存结果

     .. image:: ../images/menu_image/Tools/result_IncidenceAzimuthAngle.png
        :align: center


  #. Extract Fault Segment Parameters（提取断层分段参数）

    该功能通过设置提取断层分段参数

     .. image:: ../images/menu_image/Tools/dailog_ExtractFaultSegmentParameters.png
        :align: center

  #. Extract GNSS Coseismic Displacement（提取GNSS等震线位移）

    该功能通过设置时间范围提取GNSS等震线位移数据

     .. image:: ../images/menu_image/Tools/dailog_ExtractGNSSCoseismicDisplacement.png
        :align: center

    **使用步骤：**

    STEP 1：选择或输入GNSS时序数据（.tms）路径，输入合适的时间范围，DateTime1和DateTime2

    STEP 2：点击OK，即可计算输出结果：N±dN、E±dE、U±dU，再点击Export即可导出计算结果

     .. image:: ../images/menu_image/Tools/dialog_ExtractGNSSCoseismicDisplacement2.png
        :align: center

  #. Extract Leveling Data within Block（提取范围内的水准数据）

     该功能用于提取多边形范围内的水准数据

     .. image:: ../images/menu_image/Tools/dailog_ExtractLevelingDatawithinBlock.png
        :align: center

    **使用步骤：**

    STEP 1：先通过Map View工具栏中的Create Polygon（新建多边形）工具绘制一个多边形范围

     .. image:: ../images/menu_image/Tools/tool_CreatePolygon.png
        :align: center

    STEP 2：点击按钮打开Extract Leveling Data within Block对话框，设置待提取的基础水准数据（.lev）路径和提取后数据的保存路径，选择之前绘制的多边形范围，点击Extract（提取）按钮，弹出成功提示框后，即可保存结果

     .. image:: ../images/menu_image/Tools/dialog_ExtractLevelingDataWithBlock2.png
        :align: center

  #. Extract GNSS Data within Block（提取范围内的GNSS数据）

      该功能用于提取多边形范围内的GNSS数据

     .. image:: ../images/menu_image/Tools/dailog_ExtractGNSSDatawithinBlock.png
        :align: center

    **使用步骤：**

    STEP 1：先通过Map View工具栏中的Create Polygon（新建多边形）工具绘制一个多边形范围

     .. image:: ../images/menu_image/Tools/tool_CreatePolygon.png
        :align: center

    STEP 2：点击按钮打开Extract GNSS Data within Block对话框，设置待提取的基础GNSS数据（.gps）路径和提取后数据的保存路径，选择之前绘制的多边形范围，点击Extract（提取）按钮，弹出成功提示框后，即可保存结果

     .. image:: ../images/menu_image/Tools/dialog_ExtractGNSSWithinBlock2.png
        :align: center

  #. Extract InSAR Data within Block（提取范围内的InSar数据）

      该功能用于提取多边形范围内的InSar数据

     .. image:: ../images/menu_image/Tools/dailog_ExtractInSARDatawithinBlock.png
        :align: center

    **使用步骤：**

    STEP 1：先通过Map View工具栏中的Create Polygon（新建多边形）工具绘制一个多边形范围

     .. image:: ../images/menu_image/Tools/tool_CreatePolygon.png
        :align: center

    STEP 2：点击按钮打开Extract InSAR Data within Block对话框，设置待提取的基础InSAR数据（.sar）路径和提取后数据的保存路径，选择之前绘制的多边形范围，点击Extract（提取）按钮，弹出成功提示框后，即可保存结果

     .. image:: ../images/menu_image/Tools/dialog_ExtractInSARDataWithinBlock2.png
        :align: center

  #. Extract Earthquakes within Block（提取范围内的地震数据）

      该功能用于提取多边形范围内的地震数据

     .. image:: ../images/menu_image/Tools/dailog_ExtractEarthquakeswithinBlock.png
        :align: center

    **使用步骤：**

    STEP 1：先通过Map View工具栏中的Create Polygon（新建多边形）工具绘制一个多边形范围

     .. image:: ../images/menu_image/Tools/tool_CreatePolygon.png
        :align: center

    STEP 2：点击按钮打开Extract Earthquakes within Block对话框，设置待提取的基础地震数据（.etc）路径和提取后数据的保存路径，选择之前绘制的多边形范围，点击Extract（提取）按钮，弹出成功提示框后，即可保存结果

     .. image:: ../images/menu_image/Tools/dialog_ExtractEarthquakesWithinBlock2.png
        :align: center

2.3.2 Construct Fault Geometry（构造断层几何）
~~~~~~~~~~~~~~~~~~

    该功能可根据断层分段参数数据计算矩形或三角位错模型数据，菜单包括了：Varying Strikes（不同走向）、Varying Dips（不同倾角）2个子菜单，如图所示。

    .. image:: ../images/menu_image/Tools/btnMenu_ConstructFaultGeometry.png
       :align: center

(#) Construct Fault Geo Model Varying Strikes（不同走向的构造断层地质模型）菜单的界面如下：

    .. image:: ../images/menu_image/Tools/dailog_ConstructFaultGeoModelVaryingStrikes.png
       :align: center

    **使用步骤：**

    STEP 1：先输入或选择 Fault Params Files（断层参数文件）

    STEP 2：根据数据依次配置Reference Ellipsoid（参考椭球体）、L0（中央子午线）、Dislocation Shape（错位形状）、Length和Width矩形错位要素的长宽尺寸

    STEP 3：点击OK进行计算，点击Export（导出）按钮，弹出成功提示框后，即可保存结果

    .. image:: ../images/menu_image/Tools/WithSegmentsAlong.png
        :align: center  

(#) Construct Fault Geo Model Varying Dips（不同倾角的构造断层地质模型）菜单的界面如下：

    .. image:: ../images/menu_image/Tools/dialog_ConstructFaultGeoModelVaryingDips.png
       :align: center

    .. image:: ../images/menu_image/Tools/WithSegmentsDip.png
        :align: center


2.3.3 Construct Checkboard Test Model（构造断层网格测试）
~~~~~~~~~~~~~~~~~~

    该功能可基于断层几何模型根据用户设定尺寸生成构造断层网格

    .. image:: ../images/menu_image/Tools/CreateCheckboardTestModel.png
       :align: center

2.3.4 Construct Deep Slip Model（构造深部滑移模型）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dailog_ConstructDeepSlipModel.png
       :align: center

2.3.5 Gauss Projection:EN2XY（高斯投影:经纬度转投影坐标）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dailog_GaussProjectionEN2XY.png
       :align: center

2.3.6 Gauss Projection:XY2EN（高斯投影:投影坐标转经纬度）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dailog_GaussProjectionXY2EN.png
       :align: center

2.3.7 Reference Frame Conversion（参考框架转换）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dailog_ReferenceFrameConversion.png
       :align: center

2.3.8 Data Format Conversion（数据格式转换）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/btnMenu_DataFormatConversion.png
       :align: center

2.3.9 Clip Image（图像裁切）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dialog_ClipImage.png
       :align: center

2.3.10 Superimpose Image（图像叠加）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dialog_SuperimposeImage.png
       :align: center

2.3.11 Merge Image（图像合并）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dialog_MergeImages.png
       :align: center

2.3.12 Compress Image（图像压缩）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/btnMenu_CompressImage.png
       :align: center

2.3.13 Generate Fringe Pattern（生成干涉条纹）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dialog_GenerateFringePattern.png
       :align: center

2.3.14 Synthesize LOS Displacement（合成LOS位移）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/dialog_SynthesizeLOSDisplacement.png
       :align: center

2.3.15 Correct Data（数据校正）
~~~~~~~~~~~~~~~~~~

    .. image:: ../images/menu_image/Tools/btnMenu_CorrectData.png
       :align: center


2.4 Analysis (分析)
---------------------

Analysis菜单包括下列功能：

(1) Calculate Min/Max Values，该菜单界面如下： 

    .. image:: ../images/menu_image/Analysis/minmax.png
        :align: center  

(#) Calculate Total Seismic Moment
(#) Compare GNSS/InSAR Displacement，该菜单界面如下： 

.. image:: ../images/menu_image/Analysis/CompareGNSSInSARDisplacement.png
    :align: center  

(#) Estimate Observation Standard Deviation
(#) Correlation between Seismicity and Faults
(#) Correlation between Seismicity and Stressing Rates
(#) Correlation between Aftershocks and CFS Change
(#) Fit Interseismic GNSS Time Series，该菜单界面如下： 

.. image:: ../images/menu_image/Analysis/FitInterseismicGNSSTimeSeries.png
    :align: center  

(#) Correct Postseimic GNSS Time Series，该菜单界面如下： 

.. image:: ../images/menu_image/Analysis/CorrectPostseimicGNSSTimeSeries.png
    :align: center  

(#) Fit Postseimic GNSS Time Series，该菜单界面如下： 

.. image:: ../images/menu_image/Analysis/FitInterseismicGNSSTimeSeries.png
    :align: center  

(#) Fit Temporal Distribution Of Aftershocks，该菜单界面如下：

    .. image:: ../images/menu_image/Analysis/FitTemporalDistributionOfAftershocks.png
       :align: center 

(#) Fit GNSS Velocities


2.5 Forward (正演)
-------------------

Forward菜单包括下列功能：

(1) Forward CoGrnd displacement
(#) Forward CoRegn Sts Change
(#) Forward Fault Co Sts Perturb
(#) Forward Post Ground displacement
(#) Forward Post Regn Sts Change
(#) Forward Fault Post Sts Perturb
(#) Forward Post Dis Poroelastic Rebound
(#) Forward Post Stress Poroelastic Rebound
(#) Forward Inter Grnd Dis
(#) Forward Inter Sts Accumulation
(#) Forward Tectonic Loading NS
(#) Forward Tectonic Loadind DS
(#) Forward Lyr Grn Function


2.6 Invert (反演)
------------------

Invert菜单包括下列功能：

(1) InvertFlt
(#) Invert CoSlip Distribution
(#) Invert Blc Motion And Stn
(#) Invert Reg Tec Stn
(#) Invert Reg Tec Stn LSC
(#) Invert Back Slip Rate
(#) Invert Back Slip Rate 3DEM
(#) Invert Back Slip Rate 3DVM
(#) Invert Stressing Rate
(#) Slip Distribution


2.7 Evaluate (评估)
--------------------

Evaluate菜单包括下列功能：

(1) Count Seismic Moment
(#) Ocurrence Possibility
(#) After shock Duration
(#) Assess Earthquake OccurTime
(#) Stress Disturb Time


2.8 Cartography (制图)
---------------
.. image:: ../images/menu_image/File/dialog_setLayoutView.png
    :align: center
功能说明：

    * |Layout List| Layout List（布局列表）下拉列表：该下拉列表用于显示当前布局视图，点击该下拉列表后，可切换所需的布局。
    * |New Layout| New Layout（新建布局）按钮：点击该按钮后，会弹出New Print Layout（新建打印布局）对话框，要求输入新的唯一布局标题，点击确定后即可生成新布局。
    * |Delete Layout| Delete Layout（删除布局）按钮：点击该按钮后，可删除当前布局。
    * |Save Layout| Save Layout（保存布局）按钮：点击该按钮后，可保存布局的当前状态。
    * |Add Map| Add Map（添加地图）按钮：点击该按钮后，可在当前布局中添加一个新的地图框。
    * |Add Legend| Add Legend（添加图例）按钮：点击该按钮后，可在当前布局中添加一个新的图例。
    * |Add GNSS Legend| Add GNSS Legend（添加GNSS图例）按钮：点击该按钮后，可在当前布局中添加一个新的GNSS图例。
    * |Add Lev Legend| Add Lev Legend（添加水准图例）按钮：点击该按钮后，可在当前布局中添加一个新的水准图例。
    * |Add Rotation Rate Legend| Add Rotation Rate Legend（添加旋转率图例）按钮：点击该按钮后，可在当前布局中添加一个新的旋转率图例。
    * |Add Principal Strain Rate Legend| Add Principal Strain Rate Legend（添加主应变率图例）按钮：点击该按钮后，可在当前布局中添加一个新的主应变率图例。
    * |Add Color Ramp| Add Color Ramp（添加色带）按钮：点击该按钮后，可在当前布局中添加一个新的色带。
    * |Add Label| Add Label（添加标签）按钮：点击该按钮后，可在当前布局中添加一个新的文字标签。
    * |Add Scale Bar| Add Scale Bar（添加比例尺）按钮：点击该按钮后，可在当前布局中添加一个新的比例尺。
    * |Pan| Pan（平移）按钮：点击该按钮后，可通过鼠标平移当前布局视图。
    * |Zoom In| Zoom In（放大）按钮：点击该按钮后，可放大当前布局视图。
    * |Zoom Out| Zoom Out（缩小）按钮：点击该按钮后，可缩小当前布局视图。
    * |Zoom| Zoom（缩放）按钮：点击该按钮后，可通过鼠标控制缩放当前布局视图。
    * |Zoom Actual| Zoom Actual（缩放实际）按钮：点击该按钮后，可缩放当前布局视图到实际位置。
    * |Zoom All| Zoom All（缩放全部）按钮：点击该按钮后，可缩放当前布局视图到包含全部内容。
    * |Refresh| Refresh（刷新）按钮：点击该按钮后，可刷新当前布局视图。
    * |Select/Move Item| Select/Move Item（选择/移动图面要素）按钮：点击该按钮后，可将鼠标切换至选择状态，用于选择图例或图面要素。并可按住鼠标左键拖动图例或图面要素至合适位置。
    * |Move Content| Move Content（移动内容）按钮：点击该按钮后，可操作地图框内的视图范围，移动地图框内的显示内容。
    * |Overview Setting| Overview Setting（缩略图设置）按钮：当布局视图内有2个及以上地图框时，选中一个地图框后，点击该按钮后可将该地图框地图视图设置到全图范围
    * |Grid Setting| Grid Setting（网格设置）按钮：该按钮用于设置地图框相关参数，具体设置参数请参阅 `2.8.1 Grid Setting（网格设置）`_。
    * |Text Setting| Text Setting（文本设置）按钮：该按钮用于设置标签的文本属性，具体设置参数请参阅 `2.8.2 Text Setting（文本设置）`_。
    * |Legend Setting| Legend Setting（图例设置）按钮：该按钮用于设置图例相关参数，具体设置参数请参阅 `2.8.3 Legend Setting（图例设置）`_。
    * |Scalebar Setting| Scalebar Setting（比例尺设置）按钮：该按钮用于设置比例尺相关参数，具体设置参数请参阅 `2.8.4 Scalebar Setting（比例尺设置）`_。
    * |GNSS Setting| GNSS Setting（GNSS图例设置）按钮：该按钮用于设置GNSS图例相关参数，具体设置参数请参阅 `2.8.5 GNSS Setting（GNSS图例设置）`_。
    * |Lev Setting| Lev Setting（水准图例设置）按钮：该按钮用于设置水准图例相关参数，具体设置参数请参阅 `2.8.6 Lev Setting（水准图例设置）`_。
    * |Rotation Rate Setting| Rotation Rate Setting（旋转率图例设置）按钮：该按钮用于设置旋转率图例相关参数，具体设置参数请参阅 `2.8.7 Rotation Rate Setting（旋转率图例设置）`_。
    * |Principal Strain Rate Setting| Principal Strain Rate Setting（主应变率图例设置）按钮：该按钮用于设置主应变率图例相关参数，具体设置参数请参阅 `2.8.8 Principal Strain Rate Setting（主应变率图例设置）`_。
    * |Color Ramp Setting| Color Ramp Setting（色带设置）按钮：该按钮用于设置色带相关参数，具体设置参数请参阅 `2.8.9 Color Ramp Setting（色带设置）`_。
    * |Delete Item| Delete Item（删除部件）按钮：该按钮用于删除当前布局视图内被选中的图饰部件
    * |Raise Select Items| Raise Select Items（提升选择部件）按钮：当图饰部件出现压盖时，该按钮用于提升当前布局视图内被选中的部件的图层顺序
    * |Lower Select Items| Lower Select Items（降低选择部件）按钮：当图饰部件出现压盖时，该按钮用于降低当前布局视图内被选中的部件的图层顺序
    * |Print| Print（打印）按钮：该按钮用于打开打印控制对话框，选择合适的打印机及其设置打印当前布局视图
    * |Export As Image| Export As Image（导出图片）按钮：该按钮用于打开图片保存对话框将当前布局视图导出为图片格式，支持.BMP、.JPG、.PNG、.TIF、Webp等图片格式
    * |Export As PDF| Export As PDF（导出PDF）按钮：该按钮用于打开PDF保存对话框将当前布局视图导出为PDF格式
    
    
    .. |Layout List|      image:: ../images/menu_image/File/select_Layout.png
    .. |New Layout|       image:: ../images/menu_image/File/btn_newLayout.png
    .. |Delete Layout|    image:: ../images/menu_image/File/btn_deleteLayout.png
    .. |Save Layout|      image:: ../images/menu_image/File/btn_saveLayout.png
    .. |Add Map|          image:: ../images/menu_image/File/btn_addMap.png
    .. |Add Legend|       image:: ../images/menu_image/File/btn_addLegend.png
    .. |Add GNSS Legend|  image:: ../images/menu_image/File/btn_addGNSSLegend.png
    .. |Add Lev Legend|   image:: ../images/menu_image/File/btn_addLevLegend.png
    .. |Add Rotation Rate Legend|   image:: ../images/menu_image/File/btn_addRotationRateLegend.png
    .. |Add Principal Strain Rate Legend|   image:: ../images/menu_image/File/btn_addPrincipalStrainLegend.png
    .. |Add Color Ramp|   image:: ../images/menu_image/File/btn_addColorRamp.png
    .. |Add Label|        image:: ../images/menu_image/File/btn_addLabel.png
    .. |Add Scale Bar|    image:: ../images/menu_image/File/btn_addScaleBar.png
    .. |Pan|              image:: ../images/menu_image/File/btn_pan.png
    .. |Zoom In|          image:: ../images/menu_image/File/btn_zoomIn.png
    .. |Zoom Out|         image:: ../images/menu_image/File/btn_zoomOut.png
    .. |Zoom|             image:: ../images/menu_image/File/btn_zoom.png
    .. |Zoom Actual|      image:: ../images/menu_image/File/btn_zoomActual.png
    .. |Zoom All|         image:: ../images/menu_image/File/btn_zoomAll.png
    .. |Refresh|          image:: ../images/menu_image/File/btn_refresh.png
    .. |Select/Move Item| image:: ../images/menu_image/File/btn_selectMoveItem.png
    .. |Move Content|     image:: ../images/menu_image/File/btn_moveContent.png
    .. |Grid Setting|     image:: ../images/menu_image/File/btn_gridSetting.png
    .. |Text Setting|     image:: ../images/menu_image/File/btn_textSetting.png
    .. |Overview Setting| image:: ../images/menu_image/File/btn_overviewSetting.png
    .. |Legend Setting|   image:: ../images/menu_image/File/btn_legendSetting.png
    .. |Add Layer|        image:: ../images/menu_image/File/btn_add.png
    .. |Delete Layer|     image:: ../images/menu_image/File/btn_delete.png
    .. |Edit Layer Name|  image:: ../images/menu_image/File/btn_edit.png
    .. |Scalebar Setting| image:: ../images/menu_image/File/btn_scalebarSetting.png
    .. |GNSS Setting|     image:: ../images/menu_image/File/btn_GNSSSetting.png
    .. |Lev Setting|      image:: ../images/menu_image/File/btn_levSetting.png
    .. |Rotation Rate Setting|    image:: ../images/menu_image/File/btn_RotationRateSetting.png
    .. |Principal Strain Rate Setting|    image:: ../images/menu_image/File/btn_PrincipalStrainRateSetting.png
    .. |Color Ramp Setting|       image:: ../images/menu_image/File/btn_ColorRampSetting.png
    .. |Delete Item|      image:: ../images/menu_image/File/btn_DeleteItem.png
    .. |Raise Select Items|       image:: ../images/menu_image/File/btn_RaiseSelectItems.png
    .. |Lower Select Items|       image:: ../images/menu_image/File/btn_LowerSelectItems.png
    .. |Print|            image:: ../images/menu_image/File/btn_Print.png
    .. |Export As Image|  image:: ../images/menu_image/File/btn_ExportAsImage.png
    .. |Export As PDF|    image:: ../images/menu_image/File/btn_ExportAsPDF.png
    
2.8.1 Grid Setting（网格设置）
~~~~~~~~~~~~~~~~~~
(1) 选择地图框，如果没有请点击 |Add Map| Add Map（添加地图）按钮添加地图框，激活Grid Setting（网格设置）按钮
(#) 点击该按钮，弹出Map Item Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_mapItemSetting.png
    :align: center

参数说明：
      * Left Top Lng（左上经度）、Right Bottom Lng（右下经度）、Left Top Lat（左上纬度）、Right Bottom Lat（右下纬度）用于设置地图视图的经纬度范围
      * Interval X（X方向间隔）、Interval Y（Y方向间隔）用于设置坐标轴的刻度间隔
      * Font（字体）、Font Size（字号）、Format（格式）、Precision（有效位数）用于设置坐标刻度值的文字样式
      * Frame Width（边框宽度）用于设置地图框的边框宽度
      * Coordinate Visible中的Left Side、Right Side、Top Side、Bottom Side用于设置边框上下左右是否显示
      * OverView（缩略图）只有在Layout View（布局视图）内有2个及以上地图框时才会激活，Linked Map（连接地图）用于指定对应的缩略图地图框，Fill Color（填充色）和Frame Color（边框颜色）用于设置缩略图中对应地图范围的填充色和边框的颜色
      * Visible Layers（显示图层）中会列出当前地图视图中应用的图层列表

(3) 根据出图需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.2 Text Setting（文本设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个文本标签，如果没有请点击 |Add Label| Add Label（添加标签）按钮添加一个文本标签，激活Text Setting（文本设置）按钮
(2) 点击该按钮，弹出Label Edit对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_labelEdit.png
    :align: center
    
参数说明：
      * Font（字体）、Font Color（字体颜色）用于设置标签文字的字号、字体、颜色等效果
      * Horizontal Margin（水平边距）、Vertical Margin（垂直边距）用于设置文本与标签框之间在水平方向和垂直方向上的距离
      * Horizontal Alignment（水平对齐）、Vertical Alignment（垂直对齐）用于设置文本在标签框内的对齐方式
      * Rotation（旋转）用于设置文本的旋转角度
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.3 Legend Setting（图例设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个图例，如果没有请点击 |Add Legend| Add Legend（添加图例）按钮添加一个图例，激活Legend Setting（图例设置）按钮
(2) 点击该按钮，弹出Legend Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_legendSetting.png
    :align: center
    
参数说明：
      * 点击图层列表下方的 |Add Layer| “+”号按钮可以添加视图中未加入的图层， |Delete Layer| “-”号按钮可以删除视图中不需要的图层， |Edit Layer Name| 编辑按钮可以编辑图层名称
      * Legend Width（图例宽度）、Legend Height（图例高度）用于设置整个图例的宽度和高度
      * Legend Direction（图例方向）用于设置图例中项目的排列方向为横向或纵向
      * Legend Font（图例字体）、Font Color（字体颜色）用于设置图例中文本的字体、字号、颜色等样式
      * Item Background（背景色）如果勾选Transparent则图例背景透明，否则为白色背景
      * Item Columns（项目）用于设置图例中条目排列的列数
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.4 Scalebar Setting（比例尺设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个比例尺，如果没有请点击 |Add Scale Bar| Add Scale Bar（添加比例尺）按钮添加一个比例尺，激活Scalebar Setting（比例尺设置）按钮
(2) 点击该按钮，弹出Scalebar Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_ScaleBarSetting.png
    :align: center
    
参数说明：
      * Scalebar Style（比例尺样式）用于设置比例尺的显示样式，可选包括Single Box（单盒式）、Double Box（双盒式）、Line Ticks Middle（中线段式）、Line Ticks Down（下线段式）、Line Ticks Up（上线段式）、Stepped Line（折线式）、Hollow（空心式）、Numeric（数字式）
      * Scalebar Height（比例尺高度）、Scalebar Width（比例尺宽度）用于设置比例尺高宽
      * Rotation（角度）用于设置比例尺旋转角度
      * Frame Width（边框宽度）用于设置比例尺边框宽度
      * Unit Label（单位标签）用于设置比例尺显示的标签单位，默认为km
      * Label Margin（标签间距）用于设置标签与比例尺之间的距离
      * Label Font（标签字体）用于设置比例尺标签的字体、字号、颜色等样式
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.5 GNSS Setting（GNSS图例设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个GNSS图例，如果没有请点击 |Add GNSS Legend| Add GNSS Legend（添加GNSS图例）按钮添加一个GNSS图例，激活GNSS Setting（GNSS图例设置）按钮
(2) 点击该按钮，弹出GNSS Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_GNSSSetting.png
    :align: center
    
参数说明：
      * Map Scale（地图比例尺）用于设置图例采用的地图比例尺，默认为布局视图中当前的地图比例尺
      * Displacement Length（位移长度）用于设置图例中GNSS Arrow（GNSS箭头）的位移长度尺寸
      * Arrow Scale（箭头比例）用于设置图例中GNSS Arrow（GNSS箭头）的箭头比例大小
      * Error Radius（误差半径）用于设置图例中GNSS Error Ellipse（GNSS误差椭圆）的椭圆半径
      * Ellipse Scale（椭圆比例）用于设置图例中GNSS Error Ellipse（GNSS误差椭圆）中椭圆的比例
      * Text（文字）、Font（字体）、Font Size（字号）、Font Color（颜色）用于设置图例中GNSS Text（GNSS文字标注）的文字内容、字体字族、字号大小和文字颜色
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.6 Lev Setting（水准图例设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个水准图例，如果没有请点击 |Add Lev Legend| Add Lev Legend（添加水准图例）按钮添加一个水准图例，激活Lev Setting（水准图例设置）按钮
(2) 点击该按钮，弹出Lev Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_LevSetting.png
    :align: center
    
参数说明：
      * Map Scale（地图比例尺）用于设置图例采用的地图比例尺，默认为布局视图中当前的地图比例尺
      * Displacement Length（位移长度）用于设置图例中Lev Arrow（水准箭头）的位移长度尺寸
      * Arrow Scale（箭头比例）用于设置图例中Lev Arrow（水准箭头）的箭头比例大小
      * Error Radius（误差半径）用于设置图例中Lev Error Ellipse（水准误差椭圆）的椭圆半径
      * Ellipse Scale（椭圆比例）用于设置图例中Lev Error Ellipse（水准误差椭圆）中椭圆的比例
      * Text（文字）、Font（字体）、Font Size（字号）、Font Color（颜色）用于设置图例中Lev Text（Lev文字标注）的文字内容、字体字族、字号大小和文字颜色
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.7 Rotation Rate Setting（旋转率图例设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个旋转率图例，如果没有请点击 |Add Rotation Rate Legend| Add Rotation Rate Legend（添加旋转率图例）按钮添加一个旋转率图例，激活|Rotation Rate Setting| Rotation Rate Setting（旋转率图例设置）按钮
(2) 点击该按钮，弹出Rotation Rate Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_RotationRateSetting.png
    :align: center
    
参数说明：
      * Map Scale（地图比例尺）用于设置图例采用的地图比例尺，默认为布局视图中当前的地图比例尺
      * AngleUnit（角度单位）用于设置Rotation Rate（旋转率）扇形的角度间隔（单位：弧度）
      * Raduis（半径）用于设置Rotation Rate（旋转率）扇形的半径（单位：弧度）
      * Rotation（旋转）用于设置Rotation Rate（旋转率）扇形的角度（单位：弧度）
      * AngleScale（角度比例）用于设置Rotation Rate（旋转率）扇形的缩放比例
      * Text（文字）、Font（字体）、Font Size（字号）、Font Color（颜色）用于设置图例中Rotation Rate Text（旋转率标注）的文字内容、字体字族、字号大小和文字颜色
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.8 Principal Strain Rate Setting（主应变率图例设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个主应变率图例，如果没有请点击 |Add Principal Strain Rate Legend| Add Principal Strain Rate Legend（添加主应变率图例）按钮添加一个旋转率图例，激活|Principal Strain Rate Setting| Principal Strain Rate Setting（主应变率图例设置）按钮
(2) 点击该按钮，弹出Principal Strain Rate Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_PrincipalStrainRateSetting.png
    :align: center
    
参数说明：
      * Map Scale（地图比例尺）用于设置图例采用的地图比例尺，默认为布局视图中当前的地图比例尺
      * E1用于设置Principal Strain Rate（主应变率）图例中的最大主应变方向的尺寸
      * E2用于设置Principal Strain Rate（主应变率）图例中的最小主应变方向的尺寸
      * Azi用于设置Principal Strain Rate（主应变率）图例中主应变方向的角度
      * Scale用于设置Principal Strain Rate（主应变率）图例的比例
      * Text（文字）、Font（字体）、Font Size（字号）、Font Color（颜色）用于设置图例中Principal Strain Rate（主应变率标注）的文字内容、字体字族、字号大小和文字颜色
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果

2.8.9 Color Ramp Setting（色带设置）
~~~~~~~~~~~~~~~~~~
(1) 选择一个色带，如果没有请点击 |Add Color Ramp| Add Color Ramp（添加色带）按钮添加一个色带图例，激活Color Ramp Setting（色带设置）按钮
(2) 点击该按钮，弹出Color Ramp Setting对话框，如下图所示：

.. image:: ../images/menu_image/File/dialog_ColorRampSetting.png
    :align: center
    
参数说明：
      * Color Ramp（色带）用于选择当前使用的色带，在色带下拉列表中，可以选择、新建、修改、保存相应的色带参数
      * Ramp Orientation（色带方向）用于设置色带的方向，可选Horizontal（水平）和Vertical（垂直）两种方式
      * Min Value（最小值）和Max Value（最大值）用于设置色带旁标注的数值范围
      * Font（字体）、Font Size（字号）、Font Color（颜色）用于设置图例中Lev Text（Lev文字标注）的字体字族、字号大小和文字颜色
(3) 根据需要设置完相关参数后，点击“Apply”按钮即可保存并预览设置效果
