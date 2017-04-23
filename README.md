# iOS自动构建套件 - flow.ci + Coding + Git

> 2017.04.23

### 前言

相信很多最开始接触自动构建都是从[**Jenkins**](https://jenkins.io/)开始的。都是纯手工搭建，本地代码创库也是[**Gitblit**](http://gitblit.com/)搭建的。基本上每次换工作，都需要重新搭建一遍，实在心累。期间踩坑无数，暂且不表。接触到[**flow.ci**](https://flow.ci/)还是因为之前一直在用他们的APP测试平台服务[**fir.im**](https://fir.im/)。本文是我对[**flow.ci**](https://flow.ci/)的一些体验，期望可以帮助iOSer快速上手。


### 准备工作

1. 项目的Git仓库（什么？还在用SVN！恨铁不成钢的表情，[SVN转Git可以看这里](http://leeiio.me/convert-subversion-to-git/)）
2. 注册[Coding](https://coding.net)账号，创建[Coding](https://coding.net)私有创库（免费的哦）。如果之前有Git仓库，也可以新建一个专门用于自动构建的分支
3. 注册[**flow.ci**](https://flow.ci/)账号(不收费，不过要手机号码接收短信验证码)
4. 绑定Coding账户。在[dashboard](https://dashboard.flow.ci)页面点击**用户头像 - Git仓库**或**创建项目**都可以绑定Coding账户。（GitHub，Bitbucket，Coding，GitLab，码云都是支持的）
5. 证书和描述文件。引用一下flow.ci自己的[详细导出证书和描述文件教程](https://docs.flow.ci/zh/upload_certificate_and_provisioning_profiles.html)。


### 开工

##### 项目配置

1. 在flow.ci的[dashboard](https://dashboard.flow.ci)页面直接点击**创建项目**。
2. 选择Coding并选择对应的代码创库。
3. 项目基础配置。选择苹果图标，Xcode版本，仓库分支。点击**开始构建**![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/1_project_base_config%402x.png)
4. fd
5. 工作流配置。这是个精细化的配置，编译和完成后
6. Provisioning Profile（.mobileprovision文件） 和 证书（.p12文件）。



##### 构建
1. 自动构建。选择"构建列表"，一般等几秒钟就会出现你配置的分支信息了
![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/6_auto_build.png)

2. 手动构建。如果你嫌自动构建读取分支信息慢，点击手动构建，选择自己想构建的分支。
![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/7_manual_select_branch.png)

3. 构建过程。点击构建当前构建条目（如果状态**准备资源**，则需要等待几秒钟。然后自动会变为**运行中**。），即可看到如下图的构建流程。通常编译会比较容易发生错误信息。按照错误提示修改项目，然后提交到Coding。**flow.ci**会自动同步并运行构建。




#### 总结





