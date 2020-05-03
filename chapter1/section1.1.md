# 1.1 Flutter跨平台开发环境搭建




### Xcode 安装

#### AppStore 下载  Xcode 11.04

####  Xcode 配置

##### Xcode - Preferences - Location
* 将 Command Line Tools 配置为需要的 Xcode 版本

#####  Xcode - Preferences - Components

* 下载所需要模拟器iOS 系统版本


### Cocoapod 安装

####查看当前 ruby 与 gem 版本
```
MacBook-Pro:coo$ ruby -v
ruby 2.2.6p396 (2016-11-15 revision 56800) [x86_64-darwin17]
MacBook-Pro:coo$ gem -v
2.7.7
```
#### ruby 与 gem需要更新到最新 切换源路径或者使用VPN

* sudo gem update --system:更新gem
* brew install ruby ：更新ruby
* 更换源（因为Ruby的软件源rubygems.org被屏蔽了，需要来修改更换源，把源切换至ruby-china；网上大多数是使用的https://ruby.taobao.org的，这里不再建议使用的了，这是因为taobao Gems 源已停止维护，现由 ruby-china 提供镜像服务）

更换源命令 ：

```
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/

```
接下来查看源路径是否替换成功，执行命令：

```
gem sources -l

```

#### 执行安装命令

* 注意不要安装 最新版 cocoapods 如果已安装 执行 `` sudo gem uninstall cocoapods``

```
sudo gem install cocoapods -v 1.7.5
```

#### cocoapods 初始化

```
pod setup

```

* 如果觉得过程太慢 可以在终端命令配置VPN网络代理临时环境变量


###  Android studio

#### 官网下载 安装包

* 安装细节一 安装过程需要配置 Android SDK Location  需要创建符合安装要求的物理文件夹

```
/Users/docter/Library/Android/sdk
```

#### Preferences 安装配置

##### Appearance & Behavior System Setting 

* Http Proxy  可以选择当前 公司网络代理 
* Android SDK ：SDK Platfroms 下载需要的安卓sdk版本
*  Android SDK ：SDK Tools 安装 Android SDK Command-line Tools: Android Emulator: Android SDK Platfrom-Tools


#### Plugins 

* 安装 Dart Flutter 插件



###  Flutter SDK 安装

在Mac上要安装并运行Flutter要满足以下最低要求:

* 操作系统: macOS (64-bit)
* 磁盘空间: 700 MB (不包括Xcode或Android Studio的磁盘空间）.
* 工具: Flutter 依赖下面这些命令行工具：```bash curl git 2.x mkdir rm unzip which```


#### 设置FLutter镜像(非必须)

由于在国内访问Flutter可能会受到限制，Flutter官方为中国开发者搭建了临时镜像，大家可以将如下环境变量加入到用户环境变量中：

```
//Macintosh HD⁩ ▸ ⁨Users⁩ ▸ ⁨你的用户名 ▸ ⁨.bash_profile
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn

```

注意：此镜像为临时镜像，并不能保证一直可用，大家可以从[ Using Flutter in China ](https://flutter.dev/community/china)上获得有关镜像服务器的最新动态。

#### 获取Flutter SDK

##### 点Flutter官网下载其最新可用的安装包。

##### 解压安装包到你想安装的目录，如：

```
$ cd ~/development
$ unzip ~/Downloads/flutter_macos_v1.2.1-stable.zip

```

##### 添加flutter相关工具到path中：

```
export PATH="$PATH:`pwd`/flutter/bin"

```

此代码只能暂时针对当前命令行窗口设置PATH环境变量，要想永久将Flutter添加到PATH中请参考下面做法：


```
$ cd ~
$ vim .bash_profile

```

然后添加：

```
export PATH=/Users/你电脑当前用户名/Documents/flutter/bin:$PATH

```


#### 运行 flutter doctor

上面path配置完成之后，需要关闭终端重新打开，然后运行：

```
$ flutter doctor

```

一般的错误会是XCode或Android Studio版本太低、或者没有ANDROID_HOME环境变量等，可参考一下环境变量的配置来检查你的环境变量：

```
//Macintosh HD⁩ ▸ ⁨Users⁩ ▸ ⁨你的用户名 ▸ ⁨.bash_profile
#Android 环境变量
export ANDROID_HOME=/Users/你的用户名/Library/Android/sdk
#Android 模拟器路径
export PATH=${PATH}:${ANDROID_HOME}/emulator
#Android tools 路径
export PATH=${PATH}:${ANDROID_HOME}/tools
#Android 平台工具路径
export PATH=${PATH}:${ANDROID_HOME}/platform-tools
#Android NDK路径
ANDROID_NDK_HOME=/Users/你的用户名/Library/Android/ndk/android-ndk-r10e
#FLutter镜像
export PUB_HOSTED_URL=https://pub.flutter-io.cn
export FLUTTER_STORAGE_BASE_URL=https://storage.flutter-io.cn
#Flutter环境变量
export PATH=/Users/你的用户名/Documents/flutter/bin:$PATH

```

#### Flutter 下 xocde 配置

* 配置Xcode命令行工具以使用新安装的Xcode版本 ```sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer``` 对于大多数情况，当您想要使用最新版本的Xcode时，这是正确的路径。如果您需要使用不同的版本，请指定相应路径。

* 保Xcode许可协议是通过打开一次Xcode或通过命令``sudo xcodebuild -license``同意过了.

#### 安装到iOS设备

要将您的Flutter应用安装到iOS真机设备，您需要一些额外的工具和一个Apple帐户，您还需要在Xcode中进行设置。

* 安装 [homebrew](https://brew.sh/)（如果已经安装了brew,跳过此步骤）.

* 打开终端并运行这些命令来安装用于将Flutter应用安装到iOS设备的工具

```
brew update
brew install --HEAD libimobiledevice
brew install ideviceinstaller ios-deploy 

```

### Visual Studio Code 

#### 安装

官网下载地址：[https://code.visualstudio.com](https://code.visualstudio.com)


#### 配置

#####  打开VSCode   找到  Extensions 

*  左上角 View -   Extensions 

* 操作界面最左边 田 字型按钮


#####  安装插件

*  安装  Dart 插件

*  安装 Flutter 插件

*  安装 Awesome Flutter  Snippets 插件



### 参考资料

[Flutter中文网](https://flutterchina.club/)


