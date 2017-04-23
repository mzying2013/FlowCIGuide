# iOS自动构建套件 - flow.ci + fir.im + Coding

> 2017.04.23

### 前言

相信很多最开始接触自动构建都是从[**Jenkins**](https://jenkins.io/)开始的。都是纯手工搭建，本地代码创库也是[**Gitblit**](http://gitblit.com/)搭建的。基本上每次换工作，都需要重新搭建一遍，实在心累。期间踩坑无数，暂且不表。接触到[**flow.ci**](https://flow.ci/)还是因为之前一直在用他们的APP发布平台服务[**fir.im**](https://fir.im/)。本文是我对[**flow.ci**](https://flow.ci/)的一些体验，期望可以帮助iOSer快速上手。


### 准备工作

1. 项目的Git仓库（什么？还在用SVN！恨铁不成钢的表情，[SVN转Git可以看这里](http://leeiio.me/convert-subversion-to-git/)）
2. 注册[Coding](https://coding.net)账号，创建[Coding](https://coding.net)私有创库（免费的哦）。
> 如果之前有Git仓库，也可以新建一个专门用于自动构建的分支
3. 注册[**flow.ci**](https://flow.ci/)账号(不收费，不过要手机号码接收短信验证码)
4. 注册[**fir.im**](https://fir.im/)账号，生成并获取**API Token**（不收费，不过要手机号码接收短信验证码）![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/10_fir_APITOKEN.png)
5. 绑定Coding账户。在[dashboard](https://dashboard.flow.ci)页面点击**用户头像 - Git仓库**或**创建项目**都可以绑定Coding账户。（GitHub，Bitbucket，Coding，GitLab，码云都是支持的）
6. 证书和描述文件。引用一下flow.ci自己的[详细导出证书和描述文件教程](https://docs.flow.ci/zh/upload_certificate_and_provisioning_profiles.html)
> （企业证书请忽略）切记在描述文件里面添加要安装设备的UDID，否则会出现从fir.im下载的时候，提示“无法安装该应用”。到时候需要重新在描述文件添加UDID，然后重新上传描述文件并再次构建。


### 开工

##### 项目配置

1. 在flow.ci的[dashboard](https://dashboard.flow.ci)页面直接点击**创建项目**。
2. 选择Coding并选择对应的代码仓库。
3. 项目基础配置。选择苹果图标，Xcode版本，仓库分支。点击**创建**![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/1_project_base_config%402x.png)
4. 工作流配置。这是个精细化的配置，指定构建分支。你还可以设置定时任务。每天下班的时候构建一次。如果你有多个Scheme（比如APP有iPhone和iPad版本，免费和收费版本），这个时候可以在**编译 - Scheme**指定特定的Scheme。**完成后**可以配置一些构建失败和成功的通知（添加构建成功邮箱地址，小心邮件爆炸哦）。
5. 添加成员。输入你的组员和测试人员的Email地址，点击邀请。他们会收到标题为**Project invitation**的邮件。按照提示操作，就可加入你的团队了。
6. 设置。找到上传证书 & Provisioning Profile，上传**准备工作6**准备的描述文件和证书。



##### 构建
1. 自动构建。选择"构建列表"，一般等几秒钟就会出现你配置的分支信息了
   ![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/6_auto_build.png)

2. 手动构建。如果你嫌自动构建读取分支信息慢，点击手动构建，选择自己想构建的分支。
   ![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/7_manual_select_branch.png)

3. 构建过程。点击构建当前构建条目（如果状态是**准备资源**，则需要等待几秒钟。然后自动会变为**运行中**。），即可看到如下图的构建流程。通常编译阶段会比较容易发生错误信息。按照错误提示修改项目，然后提交到Coding。**flow.ci**会自动同步代码库并运行构建。![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/8_build_error.png)

4. 构建后。发布构建的APP到fir.im平台。首先需要点击**工作流**中左边的"+"号并搜索fir，添加**fir.im上传插件**。在**FIR_API_TOKEN**框中填入**准备工作4**获取的**API Token**。如果一切顺利的话，你会在**fir.im - 我的应用**里面看到构建成功的APP包了。赶紧分享你的APP下载二维码吧。
> 后面两个选项可以选填。**$FIR_CHANGELOG**用于显示在fir.im下载页面的更新日志。一般我会填“flow.ci build”。用于区分手动上传和flow.ci自动构建。![](https://raw.githubusercontent.com/mzying2013/FlowCIGuide/master/9_flow_update.png)



#### 总结
总体感觉下来，就是流畅，无缝衔接。作为一个被**Jenkins**折磨过多个版本的人，实在感慨。**flow.ci**目前可以免费创建5个项目。在**flow.ci**的**dashboard**页面右上角有个**电池**一样的图标。可以看到你当前的使用情况。还有比较直观的**数据分析**。这只是**flow.ci**的初体验。期待以后挖掘更多有趣的功能。




