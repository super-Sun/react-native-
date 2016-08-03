# react-native 环境配置

#一、环境需求
1.1  安装Homebrew
       Homebrew是OS X的套件(包)管理器，我们可以通过它获取并且安装很多组件
安装方式:
      ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
  
  注意：在Max OS X 10.11（El Capitan)版本中，homebrew在安装软件时可能会碰到/usr/local目录不可写的权限问题。可以使用下面的命令修复：
  sudo chown -R `whoami` /usr/local
  
1.2  安装npm 和 Node.js
      Node.js最好安装4.0及其以上更高版本，node安装成功后npm自动也就有了，直接下载安装Node.js，网址：https://nodejs.org/en/download/ （资料中已有）。
1.3  安装WatchMan
该插件用于监控bug文件和文件变化 ，并且可以触发指定的操作
安装方式
      brew install watchman
1.4  安装Flow
       flow是一个 JavaScript 的静态类型检查器，建议安装它，以方便找出代码中可能存在的类型错误
安装方式
brew install flow
(注意：如果提示command not found,请加上sudo获得最高权限)

#二、React Native安装
2.1 安装React Native
        npm install -g react-native-cli
        
#三、 ios开发环境需求
Xcode 7 及其以上更高版本

#四、 Android开发环境需求
      安装最新版的JDK:

      下载安装地址：http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
      可以安装Android studio省略以下步骤，建议安装Android studio。

4.1  安装Genymotion
       Genymotion是一个第三方模拟器，它比Google官方的模拟器更易设置且性能更好。但是，它只针对个人用户免费。
1）下载并安装Genymotion
      https://www.genymotion.com/
2）打开Genymotion,如果你尚未安装VirtualBox,它有可能会提示你安装
3）创建一个模拟器并启动
4）按下⌘+M可以打开开发者菜单(在安装并启动了React Native应用之后)

#五、 React Native的第一个应用
5.1 执行命令,生成一个工程
     react-native init 项目名称
      注意:由于众所周知的网络原因，需要等待一段时间（具体视网络情况而定）。react-native命令行从npm官方源拖代码时会遇上麻烦，可以将npm仓库源替换为国内镜像：
     npm config set registry https://registry.npm.taobao.org
     npm config set disturl https://npm.taobao.org/dist        
5.2目录结构分析:
a）默认生成android和ios两个平台的原生项目；
b）其中，index.android.js和index.ios.js文件为Android和iOS的空壳应用文件；
c）此外，node_modules文件夹，是为Node.js存放和管理npm包资源，也包含React Native框架文件。

#六、运行工程文件
      不管是 iOS 还是 Android，在开发调试阶段，都需要在 Mac 上启动一个 HTTP 服务，称为Debug Server，默认运行在 8081 端口，APP 通 Debug Server 加载 js。
6.1 打开Xcode，运行你的第一个React Native创建的iOS应用
6.2 把React Native创建的应用跑在Android上
a) 命令行执行cd SeeMyGoProduct,路径切换到项目主目录
b) 命令行执行react-native run-android进行加载运行android 应用。
c) 使用编辑器进行打开和修改index.android.js文件，接着通过菜单按钮选择Reload JS来进行刷新修改
七、管理React Native库的版本
       在开发中，会经常的去控制React Native的版本库，得以适配各种条件下的开发，那该如何查看、控制ReactNative的版本呢？

7.1 查看本地的React Native的版本
  命令行输入
   react-native --version

7.2 更新本地的React Native的版本
    命令行输入
    npm update -g react-native-cli

7.3 查询react-native的npm包最新版本
     NPM的全称是Node Package Manager ，是一个NodeJS包管理和分发工具，已经成为了非官方的发布Node模块（包）的标准。
    npm包地址 ：
     https://www.npmjs.com/package/react-native
    命令行查询
      npm info react-native
      7.4 升级或者降级npm包的版本
    npm install --save react-native@0.18

7.5 更新项目templates文件（可选）
       新的npm包会包含更新在运行react-native init命令生成的一些动态文件，例如init创建项目的时候会生成iOS和Android的子项目，我们可以通过以下的命令进行获取最新的代码
     命令行查询
      react-native upgrade
#八、WebStom设置React Native代码提示
    8.1  从gitHub上下载xml插件
     git clone https://github.com/virtoolswebplayer/ReactNative-LiveTemplate  

     8.2  安装
     将ReactNative.xml复制到 ~/Library/Preferences/WebStorm10/templates ，然后重启 WebStrom
