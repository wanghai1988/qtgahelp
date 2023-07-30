====================
3 GUI (窗体界面)
====================

.. image:: ../images/GUI_image/img_gui.png
    :align: center  
    
3.1 Layers (图层列表)
---------------
.. image:: ../images/GUI_image/img_layers.png
    :align: center
图层列表是加载数据的关键控件，用户添加的栅格数据、矢量数据、在线数据都会列在图层列表中，用户可以通过右键菜单对图层进行控制。

3.1.1 Layers Toolbar（图层工具栏）
~~~~~~~~~~~~~~~~~~
.. image:: ../images/GUI_image/img_layersToolbar.png
    :align: center  
图层工具栏包括：Add Group（添加分组）、Control Layer Display（控制图层显示）、Expand All（展开全部）、Collapse All（折叠全部）、Remove Layer（移除图层）工具按钮

    (1) |Add Group| Add Group（添加分组）按钮：点击该按钮可以在图层列表中，新建一个分组文件夹，可以将图层拖拽进该分组文件夹中，方便在图层数量较多时对图层进行分组管理

    (2) |Control Layer Display| Control Layer Display（控制图层显示）下拉按钮：点击该按钮后会弹出一个控制菜单，包括Show All Layers（显示所有图层）、Hide All Layers（隐藏所有图层）、Show Selected Layers（显示选中图层）、Hide Selected Layers（隐藏选中图层）、Hide Deselected Layers（隐藏未选中图层），用户可以通过该菜单控制图层的显示和隐藏

    .. image:: ../images/GUI_image/menu_controlLayerDisplay.png
        :align: center

    (3) |Expand All| Expand All（展开全部）按钮：点击该按钮后，可以将分组折叠的图层、以及图层折叠的样式全部展开显示
    (4) |Collapse All| Collapse All（折叠全部）按钮：点击该按钮后，可以将图层全部折叠
    (5) |Remove Layer| Remove Layer（移除图层）按钮：点击该按钮后，可以移除当前选中的图层

3.1.2 Context Menu（右键菜单）
~~~~~~~~~~~~~~~~~~
右键菜单是用户设置图层重要的控制组件，不同的图层类型所对应的右键菜单也不尽相同
    (1) 栅格数据右键菜单



3.2 Overview (缩略图)
---------------

    .. image:: ../images/GUI_image/img_overview.png
        :align: center

缩略图也称鹰眼图，用于显示地图的整体范围，Map View主窗体的视图范围在缩略图中以红框表示并联动。当用户在地图主窗体中调整了视图范围，缩略图的红框也随之变化，同样如果在缩略图中调整红框位置也会造成地图主窗体视图的变化。


3.3 Toolbar (工具栏)
---------------


.. |Add Group|                  image:: ../images/GUI_image/btn_addGroup.png
.. |Control Layer Display|      image:: ../images/GUI_image/btn_controlLayerDisplay.png
.. |Expand All|                 image:: ../images/GUI_image/btn_ExpandAll.png
.. |Collapse All|               image:: ../images/GUI_image/btn_CollapseAll.png
.. |Remove Layer|               image:: ../images/GUI_image/btn_RemoveLayer.png
