2018.11.21
# MacBook SSD Replacement
[![NPM version](https://img.shields.io/npm/v/markdown-toc.svg?style=flat)](https://www.npmjs.com/package/markdown-toc)   
[![NPM monthly downloads](https://img.shields.io/npm/dm/markdown-toc.svg?style=flat)](https://npmjs.org/package/markdown-toc)  
[![NPM total downloads](https://img.shields.io/npm/dt/markdown-toc.svg?style=flat)](https://npmjs.org/package/markdown-toc)  
[![Linux Build Status](https://img.shields.io/travis/jonschlinkert/markdown-toc.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/markdown-toc)   
[![Windows Build Status](https://img.shields.io/appveyor/ci/jonschlinkert/markdown-toc.svg?style=flat&label=AppVeyor)]()   
[![macOS Build Status](https://api.travis-ci.org/naokazuterada/MarkdownTOC.svg?branch=master&label=macOS+build "macOS Build Status")](https://travis-ci.org/naokazuterada/MarkdownTOC)
>MacBook SSD Replacement.

# 目录
<details>
  <summary>点击打开目录</summary>
    <!-- MarkdownTOC autolink="true" levels="1,2,3,4,5,6" bracket="round" style="unordered" indent="    " autoanchor="false" markdown_preview="github" -->

+ [1 前言](#1 前言)
+ [2 前期准备](#2 前期准备)
  * [2.1 硬件准备](#2.1 硬件准备)
    * [2.1.1 电脑](#2.1.1 电脑)
    * [2.1.2 两个U盘](#2.1.2 两个U盘)
    * [2.1.3 外部存储介质](#2.1.3 外部存储介质)
    * [2.1.4 新SSD](#2.1.4 新SSD)
    * [2.1.5 M.2 ngff转nvme转换接头](#2.1.5 M.2 ngff转nvme转换接头)
    * [2.1.6 五星螺丝刀等常用拆装机设备](#2.1.6 五星螺丝刀等常用拆装机设备)
  * [2.2 软件准备](#2.2 软件准备)
    * [2.2.1 macOS+引导](#2.2.1 macOS+引导)
    * [2.2.2 Ubuntu+引导](#2.2.2 Ubuntu+引导)
+ [3 启动盘烧录&备份](#3 启动盘烧录&备份)
  * [3.1 macOS烧录](#3.1 macOS烧录)
  * [3.2 Ubuntu烧录](#3.2 Ubuntu烧录)
  * [3.3 Time Machine备份](#3.3 Time Machine备份)
+ [4 拆机&硬件更换](#4 拆机&硬件更换)
  * [4.1 拆机](#4.1 拆机)
  * [4.2 新旧SSD更换](#4.2 新旧SSD更换)
+ [5 系统引导&数据恢复](#5 系统引导&数据恢复)
    <!-- /MarkdownTOC -->
</details>

## 1 前言
+ 本教程纯手工打制，也仅在本机所处环境下测试通过，并不具有完全通用性。
+ 苹果原装1T SSD几乎8000元左右，而nvme的顶级1T SSD一般在2000-2500左右，通过转接头可以完美实现SSD替换操作，节省预算，速度更快。

---

## 2 前期准备
### 2.1 硬件准备
#### 2.1.1 电脑
+ MacBook Pro with Retina，13寸，2015年初款。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-115807%402x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 理论上只要是2015年末之前的MacBook，不论型号，都可以进行硬盘替换，目前已知2017款后均采取内存、硬盘焊死操作，不允许进行第三方改装。

+ 检测方法：背面苹果LOGO能亮灯一般就是可以改装。
#### 2.1.2 两个U盘
+ 作为启动盘引导改装过程。
+ U盘A用来预装macOS，U盘B用来预装Ubuntu系统。需要注意的是，**U盘A必须有**，否则无法启动；在新盘挂载时，可能会出现无法识别的情况，需要利用U盘B的Ubuntu系统进行新盘检测+格式化，所以**B并非是必须**，建议提前准备好，人品好请无视此条并跳过所有U盘B的操作部分。
#### 2.1.3 外部存储介质
+ 如移动硬盘等,用来备份当前macOS内的所有数据，后期更换硬盘后进行恢复。
#### 2.1.4 新SSD
+ 理论上nvme接口的都可以,本教程选用三星的970EVO 1T固态硬盘，读取3500mb/s，写入2500mb/s，接口类型类似的理论上都可以进行改装。
#### 2.1.5 M.2 ngff转nvme转换接头
+ 淘宝，15元一个,转换接头+新SSD=旧SSD。
#### 2.1.6 五星螺丝刀等常用拆装机设备
+ 淘宝，6元左右两把,用于拆装MacBook。

### 2.2 软件准备
#### 2.2.1 macOS+引导
+ 本教程所在系统是macOS High Sierra 10.13.3，不能低于10.13，尽量不要选用新的Mojave。可以在mac的app store里下到相关系统。
+ 点击[下载地址](https://support.apple.com/zh-cn/HT208969)，步骤四中点击“获取macOS High Sierra”即可跳转至mac的app store进行下载。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-115908@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 链接自动跳转到app store里，点击“下载”即可下载到本地文件夹，大约5.6GB。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-115909@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 引导部分使用[Disk Maker x7 for High Sierra](http://diskmakerx.com/whats-this/)，选择“Download DiskMaker X 7.0.1”进行下载。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-115910@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

#### 2.2.2 Ubuntu+引导
+ 建议[官网进行下载](https://www.ubuntu.com/download/alternative-downloads)，版本不限，

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-225227@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 本次教程选用的是Ubuntu 16.04.5 Desktop (64bit)，下载完成大约1.6GB，格式为ISO。

+ 引导部分使用[Belena Etcher](https://www.balena.io/etcher/)，选择“Etcher for macOS”进行下载。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-225212@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

---

## 3 启动盘烧录&备份
### 3.1 macOS烧录
+ 使用已经下载下来的**Disk Maker**进行macOS的启动盘烧录，插入U盘后，打开Disk Maker后会执行自动检测。

+ 选择正确的macOS下载路径。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201223@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 选择是“格式化部分分区”还是“格式化当前U盘”。建议使用提前清理好的U盘，“格式化当前U盘”。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201324@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 选择已经插入的U盘。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201330@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 确认清空当前U盘并创建引导盘。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201339@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 确认清空当前U盘并创建引导盘。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201346@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 右上角通知栏将会显示烧录进度。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201435@2x.png" alt="Pic"  width="300">
    <p align="center">
        <em></em>
    </p>
</p>

+ 等待烧录完成，会弹出提示框，关闭即可。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-201945@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 到此，macOS启动盘烧录完成。

---

### 3.2 Ubuntu烧录
+ 使用已经下载下来的**Etcher**进行ubuntu的启动盘烧录，由于Etcher并不具有格式化功能，所以需要提前进行U盘B的格式化。

+ 打开系统自带的“Disk Utility”（磁盘工具），选择正确的U盘，进行U盘B的擦除，格式化的格式无所谓，擦除完毕即可。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-120606@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 打开“Etcher”软件。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-120958@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 选择下载好的镜像，选择正确的U盘B，点击“烧录”即可进行Ubuntu的启动盘烧录和验证过程。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-120507@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-120743@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 烧录完成将会弹出“U盘无法识别”的通知，点击“弹出”即可完成烧录过程。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181121-120926@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 到此，Ubuntu启动盘烧录完成。

---

### 3.3 Time Machine备份
+ 本教程使用Mac自带的Time Machine进行系统和数据的备份，视系统数据大小需要一定容量的外置移动硬盘。

+ 打开左上角苹果-系统偏好设置-Time Machine。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181122-174004@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 在Time Machine偏好设置面板里进行相关备份设置。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181122-174025@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 选择备份输出的外置移动硬盘，此处需要注意：作为备份数据存储中心的移动硬盘必须进行**格式化**，所以一定要提前准备好一块空的移动硬盘。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181122-174033@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 勾选“自动备份”和“在任务栏显示Time Machine”。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181122-174130@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 在“Option”中选择需要剔除的文件夹路径，方便系统和数据的快速备份。

<p align="center">
    <img src="https://github.com/fei7yang/mac_ssd_replace/blob/master/assets/WX20181122-174158@2x.png" alt="Pic"  width="700">
    <p align="center">
        <em></em>
    </p>
</p>

+ 在打开Time Machine的情况下，插入外置移动硬盘，将会自动进行系统及数据备份，等待备份完成即可。

---

## 4 拆机&硬件更换
### 4.1 拆机
+ 拆机需要使用Mac专用的螺丝刀，在章节2.1.6中有具体介绍。其余常见拆机设备如静电手环、无尘工作桌等配置越多越好。
+ **注意：拆机有风险！误操作可能会导致元器件损坏报废！**
+ **注意：拆机有风险！误操作可能会导致元器件损坏报废！**
+ **注意：拆机有风险！误操作可能会导致元器件损坏报废！**
+ 如下图所示，MacBook的背板一共10颗螺丝钉，需要注意的是，上下的两颗并排的螺丝钉，和两侧竖着的三颗螺丝钉并不是同一种型号的，长短并不一致不要通用。这里100%建议**从哪里卸下来的就装回原来的地方去**。
+ 拆卸完成后，建议从**上侧通风口**轻轻抬起背壳，沿着四周方向缓缓抬动，在背板中央偏下的位置有两个卡扣，大概注意下位置，可以使用一个软质卡片从抬起处轻轻翘起，注意**不要划伤电脑背壳，很脆弱！！**
+ 拆开以后，可以看到如下的界面。
+ 按照图中红圈的提示，将集成主板上的电源排线拔掉，这一步很重要，因为主板中的电子元器件都是精密仪器，如果不断电操作，很容易引起静电击穿，造成元器件损坏。（此处有条件的可以使用防静电手环、无尘工作环境等先进设施）

### 4.2 新旧SSD更换
+ 断掉电源排线后，按照图中绿圈的提示，将图示SSD区域的螺丝钉先卸掉并保存好，然后轻轻拔掉旧SSD保存好。
+ 然后**先将转接头对准接口安装上**，需要用点力气，此处建议不要拼接“转接头+新SSD”再安装，要先安装转接头，然后将新SSD接到转接头上，否则很难安装，动手能力差的就不用尝试了，按照教程即可。
+ 转接头+新SSD都插好后，此处尾部螺丝钉口应该完美对接，如果出现不能对接的情况，**一定是没插紧**，拔掉重新插即可。
+ 插好安装上尾部螺丝钉进行固定，盖上背板，接上刚才拔掉的电源排线，但是不要上背板螺丝钉，先进检测操作以免硬盘有问题还得再次拆掉螺丝钉。


## 5 系统引导&数据恢复
### 5.1 macOS系统引导
+ 本步骤应当遵循的过程是：  
mermaid
graph LR
    start[开始] --> input[输入A,B,C]
    input --> conditionA{A是否大于B}
    conditionA -- YES --> conditionC{A是否大于C}
    conditionA -- NO --> conditionB{B是否大于C}
    conditionC -- YES --> printA[输出A]
    conditionC -- NO --> printC[输出C]
    conditionB -- YES --> printB[输出B]
    conditionB -- NO --> printC[输出C]
    printA --> stop[结束]
    printC --> stop
    printB --> stop

+
+



































































































































































# final line
