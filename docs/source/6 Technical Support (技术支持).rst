=================================
6 Technical Support (技术支持)
=================================

6.1 Training Materials (培训资料)
------------------

1. `64位地震大地测量软件介绍 <https://dx.doi.org/10.12351/ks.2307.2351>`_

2. `64位地震大地测量软件功能演示 <https://dx.doi.org/10.12351/ks.2307.2352>`_

3. `基于“微块体”模型反演地壳应变率与64位地震大地测量软件研发 <https://www.koushare.com/live/details/36796>`_

4. `2024年全国地壳形变资料分析与预报应用培训资料 <https://github.com/wanghai1988/qtgahelp/releases/download/2024Documents/2024.zip>`_

5. `2025年第二届InSAR理论与实践暑期课程培训资料 <https://github.com/wanghai1988/qtgahelp/releases/download/2025Documents/2rdInSARDocument.rar>`_ 



6.2 User Community (用户社区)
-------------------

1. QQ群：252716902（入群请备注：姓名-单位）
2. `GitHub参与讨论 <https://github.com/LongxiangSun/TGA_Publish/discussions>`_

6.3 Customization Service (软件功能定制)
-------------------
如果您有功能定制需求，请通过邮件联系武汉大学 `江国焰 <http://gyjiang.users.sgg.whu.edu.cn/>`_ 老师。

6.4 Training Support (培训支持)
-------------------

6.4.1 在linux下安装windows的虚拟机
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

基于平台：WMware

提供文件：WMware 17.6.3 安装包， `下载地址 <https://github.com/wanghai1988/qtgahelp/releases/download/untagged-99e8f86a979ae1d46ae2/Linux-Windows.zip>`_、 `百度网盘下载地址 <https://pan.baidu.com/s/1IlcgbhRsDcgI_A7aer6GUQ?pwd=irqq>`_

linux 安装 WMware 教程：

1.将VMware安装包复制到指定目录

``sudo cp VMware-Workstation-*.bundle /download/vmware``

1. 为安装包添加执行权限

``sudo chmod +x VMware-Workstation-Full-16.1.0-17198959.x86_64.bundle``

3. 运行安装包

``sudo ./VMware-Workstation-Full-16.1.0-17198959.x86_64.bundle``

WMware 安装 Windows 11 教程：
https://blog.csdn.net/xiaogengtongxu/article/details/136523373


Windows 11 iso 映像文件下载地址：
https://www.microsoft.com/zh-cn/software-download/windows11
选择“适用于X64设备的多版本ISO”

Windows 11 pro 版激活码：VK7JG-NPHTM-C97JM-9MPGT-3V66T


可能遇到的问题：

打开Windows虚拟机时报错：
Unable to change virtual machine power state: VMware Workstation cannot run on hosts with 5-level paging enabled. Failed to start the virtual machine.


解决方案：

编辑 /etc/default/grub ⽂件，⽐如 sudo vim /etc/default/grub ，找到GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" 这⼀⾏，在末尾加上 no5lvl ，即
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash no5lvl" ，保存后运⾏ sudo update-grub ，重启系统后修改⽣效。


6.4.2 在Mac下安装windows的虚拟机
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

基于平台：WMware Fusion

提供文件：WMware Fusion 13.6.3 安装包， `下载地址 <https://github.com/wanghai1988/qtgahelp/releases/download/untagged-99e8f86a979ae1d46ae2/Mac-Windows.zip>`_、 `百度网盘下载地址 <https://pan.baidu.com/s/1xGaJ0bK_BhqZLpeOjuKO2Q?pwd=adcf>`_

Mac 安装 WMware 和 Windows 11 教程：
https://blog.csdn.net/qq_57356551/article/details/135654951?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522f1c33e3e920f38b3b4aacae11e07ae86%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=f1c33e3e920f38b3b4aacae11e07ae86&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-135654951-null-null.142^v102^pc_search_result_base6&utm_term=mac%E5%AE%89%E8%A3%85windows%E8%99%9A%E6%8B%9F%E6%9C%BA&spm=1018.2226.3001.4187


Windows 11 iso 映像文件下载地址：
https://www.microsoft.com/zh-cn/software-download/windows11arm64
选择“适用于Arm64的多版本ISO”

Windows 11 pro 版激活码：VK7JG-NPHTM-C97JM-9MPGT-3V66T


可能遇到的问题：
安装Windows虚拟机时，提示“让我们为你连接到网络”，且无法点击下一步。


解决方案：
https://zhuanlan.zhihu.com/p/609039991
