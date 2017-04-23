# iOS自动构建套件 - flow.ci + Coding + Git

> 2017.04.23

### 前言

相信很多最开始接触自动构建都是从[**Jenkins**](https://jenkins.io/)开始的。都是纯手工搭建，本地代码创库也是[**Gitblit**](http://gitblit.com/)搭建的。基本上每次换工作，都需要重新搭建一遍，实在心累。期间踩坑无数，暂且不表。接触到[**flow.ci**](https://flow.ci/)还是因为之前一直在用他们的APP测试平台服务[**fir.im**](https://fir.im/)。本文是我对[**flow.ci**](https://flow.ci/)的一些体验，期望可以帮助iOSer快速上手。


###准备工作

1. Git仓库（什么？还在用SVN！恨铁不成钢的表情）
2. 注册[Coding](https://coding.net)账号，创建[Coding](https://coding.net)私有创库（免费的哦）。如果之前有Git仓库，也可以新建一个专门用于自动构建的分支
3. 注册[**flow.ci**](https://flow.ci/)账号(不收费，不过要手机号码接收短信验证码)
4. 绑定Coding账户。在[dashboard](https://dashboard.flow.ci)页面点击**用户头像 - Git仓库**或**创建项目**都可以绑定Coding账户。（GitHub，Bitbucket，Coding，GitLab，码云都是支持的）


### 开工

##### 项目配置

1. 在flow.ci的[dashboard](https://dashboard.flow.ci)页面直接点击**创建项目**。
2. 选择Coding并选择对应的代码创库。（不会？！这么简单易用，还需要贴图...鄙视）
3. 项目基础配置。选择苹果图标，Xcode版本，仓库分支。点击**开始构建**
4. 工作流配置。这是个精细化的配置，编译和完成后
5. Provisioning Profile 和 证书



##### 构建







#### 走两步





