2018.11.21
# MacBook SSD Replacement

## 前言
本教程纯手工打制，也仅在本机所处环境下测试通过，并不具有完全通用性。
苹果原装1T SSD几乎8000元左右，而nvme的顶级1T SSD一般在2000-2500左右，通过转接头可以完美实现SSD替换操作，节省预算，速度更快。
## 前期准备
### 硬件准备
+ #### 电脑
MacBook Pro with Retina，13寸，2015年初款。
理论上只要是2015年末之前的MacBook，不论型号，都可以进行硬盘替换，目前已知2017款后均采取内存、硬盘焊死操作，不允许进行第三方改装。
检测方法：背面苹果LOGO能亮灯一般就是可以改装。
+ #### 两个U盘
作为启动盘引导改装过程。
U盘A用来预装macOS，U盘B用来预装Ubuntu系统。需要注意的是，U盘A必须有，否则无法启动；在新盘挂载时，可能会出现无法识别的情况，需要利用U盘B的Ubuntu系统进行新盘检测+格式化，所以B并非是必须，建议提前准备好，人品好请无视此条并跳过所有U盘B的操作部分。
+ #### 外部存储介质
如移动硬盘等,用来备份当前macOS内的所有数据，后期更换硬盘后进行恢复。
+ #### 新SSD
理论上nvme接口的都可以,本教程选用三星的970EVO 1T固态硬盘，读取3500mb/s，写入2500mb/s，接口类型类似的理论上都可以进行改装。
+ #### M.2 ngff转nvme转换接头
淘宝，15元一个,转换接头+新SSD=旧SSD。
+ #### 五星螺丝刀等常用拆装机设备
淘宝，6元左右两把,用于拆装MacBook。





### 软件准备
+ #### MAC+引导
本教程所在系统是macOS High Sierra 10.13.3，不能低于10.13，尽量不要选用新的Mojave。可以在mac的app store里下到相关系统。   

  点击下载地址[https://support.apple.com/zh-cn/HT208969](https://support.apple.com/zh-cn/HT208969)，步骤四中点击“获取macOS High Sierra”即可跳转至mac的app store进行下载。

 链接自动跳转到app store里，点击“下载”即可下载到本地文件夹，大约5.6GB。

 引导部分使用Disk Maker x7 for High Sierra，[http://diskmakerx.com/whats-this/](http://diskmakerx.com/whats-this/)，选择“Download DiskMaker X 7.0.1”进行下载。


+ #### Ubuntu+引导
建议官网进行下载，版本不限，[https://www.ubuntu.com/download/alternative-downloads](https://www.ubuntu.com/download/alternative-downloads)，



























































































































































































# final line
