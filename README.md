# CocoaPodsTest
CocoaPods的使用教程
### 更换源
```
因为Ruby的软件源rubygems.org被屏蔽了，国内那无形之墙，我们需要来修改更换源，把源切换至ruby-china；
网上大多数是使用的https://ruby.taobao.org的，这里不再建议使用的了，这是因为taobao Gems 源已停止维护，现由 ruby-china 提供镜像服务

输入：gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
```
### 更新ruby

```
1.查看源路径
输入：gem sources -l

2.如果存在2个镜像：
http://rubygems.org
https://gems.ruby-china.org/

则需要仅保存gems.ruby-china.org
输入：gem sources --remove http://rubygems.org //删除多余的

3.在确保只有gems.ruby-china.org后，才能开始更新
输入：sudo gem update --system
```
### 开始安装Cocoapods

```
1.安装
输入：sudo gem install cocoapods

2.设置
输入：pod setup（当出现Setup completed的时候说明已经完成了）
```
### Cocoapods的使用

```
1.首先验证cocoapods是否可以使用
输入：pod search AFNetworking
```
![image](https://upload-images.jianshu.io/upload_images/4120931-231e05733cb54b6a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

```
1.1出现上面的图片则表示已经搜索成功了
1.2上图中pod 'AFNetworking', '~> 3.1.0'是添加第三方库的关键字段
1.3.如何退出当前界面：直接英文键盘状态下按‘q’就可以了


2.在工程中创建一个Podfile文件
2.1需要进入到该工程目录下
输入：cd /Users/xxx/Desktop/CocoaPodsTest
2.2创建Podfile文件
输入：touch Podfile（然后工程目录下就可以看到多了一个Podfile文件）

3.编辑想要导入的第三方库的名称及版本，使用vim
输入：vim Podfile
```
![image](https://upload-images.jianshu.io/upload_images/4120931-2810f4c1f0c8dc51.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

```
3.1按下英文’i‘键，进入编辑模式
3.2输入：
platform :ios, '7.0'
target '工程名' do
pod 'AFNetworking', '~> 3.1.0'
end
3.3保存并退出，先按’esc‘键，再按’：‘，再输入wq后回车就可以保存并退出了

说明:
1.platform :ios, '7.0'代表当前AFNetworking支持的iOS最低版本是iOS 7.0,
2.'MyApp'就是你自己的工程名字，
3.pod 'AFNetworking', '~> 3.1.0'代表要下载的AFNetworking版本是3.1.0及以上版本，还可以去掉后面的'~> 3.1.0'，直接写pod 'AFNetworking'，这样代表下载的AFNetworking是最新版

4.把该库下载到Xcode中
输入：pod install（耐心等待出现如下图所示之后，即代表完成）
```
![image](http://a3.qpic.cn/psb?/V10Ra4TS1frb6f/qHmzY4*O6oOiszyFCUQAD*IPeoIWULQf7NbDCjSjsc4!/c/dA4AAAAAAAAA&ek=1&kp=1&pt=0&bo=ZgTGAgAAAAARF4Y!&tl=1&vuin=2540942304&tm=1530169200&sce=60-2-2&rf=0-0)
### 使用

```
1.将所有的Xcode窗口关闭
2.打开.xcworkspace文件而不是打开.xcodeproj文件
3.在需要引用第三方库的地方导入头文件：
输入：#import <AFNetworking.h>而不是#import "AFNetworking.h"




```
持续更新中......(参考链接：https://blog.csdn.net/longshihua/article/details/53217511)
