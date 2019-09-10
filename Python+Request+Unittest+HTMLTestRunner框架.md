# Python+Requests+Unittest+HTMLTestRunner自动化测试框架

> dept：成研测试部
> 
> author：秦磊
>
> date：2019-9-10

## 前言
在最近几个月的省级综合平台的测试中，省级平台的首页已经趋于完善，在此基础上，尝试搭建以下省级平台的自动化框架，以便于回归测试，同时记录一下使用部署的全过程。

##环境配置
### 1.配置开发环境，安装Visual Stuio Code
之前编写Python更多的是使用pycharm作为编译器进行开发，但是个人感觉用起来比较笨重，而且还收费的，需要进行破解才能使用。但是有一个非常好用的工具，**Visual Studio Code**，简称**VS code**。这也是我比较喜欢的编译工具，，他主要有以下几大特点：

- 开源，免费；
- 自定义配置
- 集成git
- 智能提示强大
- 支持各种文件格式（html/jade/css/less/sass/xml）
- 调试功能强大
- 各种方便的快捷键
- 强大的插件扩展

安装方式也极其简单，直接点击安装文件，然后一致点击next就可以了。

附上下载官网：[https://code.visualstudio.com/](https://code.visualstudio.com/ "Visual Studio Code（VScode ）官网　") 


### 2.安装Python，并在VS code中配置
Python安装教程网络上很多，这里不再介绍，这里重点介绍**VS code**配置Python，我这里用的是3.7.4版本。也可自行选择下载

Python3.7.3下载链接：[https://www.python.org/downloads/](https://www.python.org/downloads/ "Python3.7.3下载链接")

VS code 配置Python可参考以下链接：[https://www.cnblogs.com/shine-lee/p/10234378.html](https://www.cnblogs.com/shine-lee/p/10234378.html)


其中主要要步骤如下图，打开软件，点击左边最下面的图标，搜索Python，选择列表的第一个插件并点击install安装程序（我这里显示已安装）。
>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/f5587bee308b4c2792a79e10bc628bfe.gif)

验证环境配置是否成功，最简单的方式是使用Python写一条简单的命令
> ```print ('Hello Word')```



### 3.创建项目

在github上创建一个项目：sjzhpt_port（如下图）

>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/c11f7818860445449083e9ce829c669a.png)

通过地址clone到本地（如下图）
>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/73ca91e0b5324ad19e2801db02a67e7f.png)

然后再VSCode中打开项目，添加文件，尝试第一次提交
>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/1e570092302c442aa08b21230d07548e.gif)

>这里就出现了一个问题，发现github仓库中并没有提交的代码，排查可能是之前git clone时出现的警告，所以做了如下操作：
>
    cd sjzhpt_port/  
    git remote add origin git@github.com:miaoqikong/sjzhpt_port.git
    git push -u origin master

>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/d7761124346f45e2aeb9a3bfa710a21d.png)
>
>然后再次刷新页面，就看到了提交的文件
>![](http://bed.thunisoft.com:9000/ibed/2019/09/10/86dfd483b55d4624a579667b70481f72.png)


## 框架搭建
