# 深入浅出Android 自动化测试

## 测试金字塔
 ![](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1502641261098&di=ec19f8be72c5985cb8430410a29f7979&imgtype=0&src=http%3A%2F%2Fwww.myexception.cn%2Fimg%2F2012%2F09%2F23%2F105333355.jpg)

## 一、常用工具
 - monkey、EasyMonkey、MonkeyRunner、Mockito、powermock、AssertJ、UIAutomator(2)、Roboletric、Robotium、Espresso、Selendroid、Appium、Calabash、Athrun
 - Google
 - [Google 测试支持库 ：[AndroidJUnitRunner、Espresso、UI Automator](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#features)
  - Google官网培训课程[Testing Apps on Android](https://developer.android.google.cn/training/testing/index.html)

-----

## 二、分类
### 1、黑/白 分类
- 有些工具是介于黑/白盒之间的`灰盒`，不单独划分，归纳到更偏重的一方中。

<center>

| 白盒        | 黑盒  |
| :--------:  | :-----:  |
|[JUnit](https://baike.baidu.com/item/junit/1211849?fr=aladdin)<br/>[AndroidJUnitRunner](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#AndroidJUnitRunner)<br/>[Mockito](http://mockito.org/)<br/>  [powermock](https://github.com/powermock/powermock<br/>)<br/>[Roboletric](http://robolectric.org/)<br/>| [money](https://developer.android.google.cn/studio/test/monkey.html)<br/>[MonkeyRunner](https://developer.android.google.cn/studio/test/monkeyrunner/index.html)<br/>[UIAutomator](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#UIAutomator)<br/>[Robotium](https://github.com/RobotiumTech/robotium)<br/>[Espresso](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#Espresso)<br/>[Selendroid](http://selendroid.io/architecture.html) <br/>[Appium](http://appium.io/)<br/>[Calabash](http://calaba.sh/)<br/>[Athrun](http://code.taobao.org/p/athrun/wiki/index/)<br/>人肉、硬件辅助测试|
</center>

###  2、根据具体实现分类

###  2.1、基于Android Java Instrumentation框架

`Instrumentation框架`通过将主程序和测试程序运行在`同一个进程`来实现这些功能。Google针对Android的环境，扩展了业内标准的JUnit测试框架。
- Robotium
- Espresso（google）
- Selendroid(资料较少，社区活跃度也不大)
- Athrun（淘宝）

###  2.2 、基于Android lib层的各种命令(sendevent,getevent, monkey, service)，然后用各种语言封装
 - MonkeyRunner
 - EasyMonkey
 - UiAutomator(抓去App页面上的控件属性,不支持Hybird App、WebApp)
 - Appium(目前最火的框架)

### 3、单元测试
 - JUnit
 -  [AssertJ](http://joel-costigliola.github.io/assertj/assertj-core.html): 断言神器，用于替换JUnit的Assert API 拓展库
 - [Assert语法的拓展库](http://hamcrest.org/JavaHamcrest/):开源的Assert语法拓展库，它提供了方便、强大的情景匹配API，不仅支持Java，也支持其他多种语言。
 - [AssertJ-Android](https://github.com/square/assertj-android):Square针对AssertJ的一个拓展，提供了对Android各类控件的情景检查。
 - Robolectric：通过实现一套JVM能运行的Android代码，从而做到脱离Android环境运行测试
 - RoboSpock 合并了 Robolectric 和 Spock （适合行为驱动开发<BDD>）

### 4、性能测试小工具
- Emmagee 监控指定被测应用在使用过程中CPU、内存、流量资源消耗的性能测试小工具

### 5、`人肉`、硬件辅助测试
 - `人肉`：测试人员通过手动点击、肉眼观察测试结果。
 - 硬件辅助测试：硬件辅助视频录像、机械手臂点击（xx抢红包）等。

----

## 三 、工具差异
 ####  * 主流黑盒工具差异
<center>
<img src="http://upload-images.jianshu.io/upload_images/2951233-42d9cc071fbbd3a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240" width="70%" height="70%" />
</center>
<br/>

- Robotium、Espresso、robolectric、Selendroid ：基于Android instrumentation框架，与被测App在同一进程。执行速度快。
- 据统计Espresso的速度是Robotium的5.7倍，很大程度上替代了Robotium。
- `Robolectric`: 只在Java虚拟机中运行，速度很快，在API上无法和Espresso相比，但速度有很大优势，适合单元测试，更适合`TDD`。
- MonkeyRunner：不需要源码、对google官方工具money的封装。
- UIAutomator:不需要source code、google提供的黑盒测试工具与APP在不同进程,但不支持WebView。
- `Appium`、Calabash：`Appium`目前黑盒测试中应用最多的框架。不需要source code，跨平台（ios/andorid），支持WebWiew 和多种语言编写测试脚本，但因为与被App在不同进程，执行速度慢。
- Athrun：淘宝提供的自动化测试工具,跨平台（ios/andorid)，包括自动化测试框架，持续集成体系。

## 四、实践
 - [World-Class Testing Development Pipeline for Android ](http://blog.karumi.com/world-class-testing-development-pipeline-for-android/) ([中文翻译-世界级的Android测试开发流程](https://juejin.im/entry/56cd878d6be3ff005e506d43))
 - [Mockito和Roboletric进行Android单元测试](https://blog.desmondyao.com/mockito-roboletric-test/)
 - [Espresso和UIAutomator - 完美的结合](https://zhuanlan.zhihu.com/p/24717655)
 - [Google+ 团队的 Android UI 测试](http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2015/0401/2675.html)
 - [Android测试驱动开发(TDD)](https://blog.desmondyao.com/android-test/) <br/><br/>
<center>
<img src="https://blog.desmondyao.com/image/test/tdd-magento.gif" width="50%" height="50%" />
TDD
</center>
<br/>

 - 通过mock来减少模块依赖（意味着需要定义大量接口，`面向接口编程`）

----

## 五、[代码覆盖率](https://baike.baidu.com/item/%E4%BB%A3%E7%A0%81%E8%A6%86%E7%9B%96%E6%B5%8B%E8%AF%95/8642107?fr=aladdin)
代码覆盖（`Code coverage`）是软件测试中的一种度量，描述程式中源代码被测试的比例和程度，所得比例称为代码覆盖率。

| Java        | JavaScript  |.Net|C/C++|Ruby|
| :--------:   | :-----:  |:-----:  |:-----:  |:-----:  |
| [JaCoCo](http://www.jacoco.org/jacoco/)<br/>[Emma](http://emma.sourceforge.net/)<br/>[Coverlipse](https://sourceforge.net/projects/coverlipse/)<br/>[Cobrertura](http://cobertura.github.io/cobertura/)|[JSCoverage](http://siliconforks.com/jscoverage/)| [ColverNET](http://www.cenqua.com/clover.net/)<br/>[NCover](http://ncover.org/)<br/>[PartCover](https://github.com/sawilde/partcover.net4)<br/>[AQtime](https://support.smartbear.com/viewarticle/42954/)|[Bullseye Coverage](http://www.bullseye.com/)|[rcov](https://github.com/relevance/rcov)|

-  [JaCoco 配置Demo](https://github.com/chenxiruanhai/Devops/tree/master/JaCoco-config-template)
- AndroidStudio自带覆盖率检测工具使用：
 - <img src="http://o8wshxdfk.bkt.clouddn.com/1.png" width="300" height="300" /> -->
 <img src="http://o8wshxdfk.bkt.clouddn.com/2.png" width="300" height="300" /><br />
  - <center><img src="http://o8wshxdfk.bkt.clouddn.com/3.png" width="50%" height="50%" /></center><br/>
 - ![](https://segmentfault.com/img/remote/1460000006767411)

---

## 六、自动化
 - [Android Unit Testing in Android Studio and CI Environments](http://futurice.com/blog/android-unit-testing-in-android-studio-and-ci-environments)
 - 所有测试应以自动化为主，无法自动化的测试用例，要人工完成。本人认为命令行工具的使用是自动化的基础，推荐阅读[为什么优秀的程序员喜欢命令行](http://www.jianshu.com/p/2a2e387ad268)。
 - 持续集成CI，保证代码集成到主干或发布到测试人员手中之前，必须通过自动化测试。只要有一个测试用例失败，就不能集成。
  - [Jenkins](https://jenkins.io/doc/)
  - [Travis](https://travis-ci.com/)
  - [Codeship](https://www.codeship.io/)
  - [Strider](http://stridercd.com/)

- ![](http://on-img.com/chart_image/598bd70ae4b020989e5b2681.png)

## 七、总结
 - 单元测试，所有测试方法中最接近源码实现的一种，但因Android系统的复杂性，不能完全的覆盖所有真实的case,需要结合其它测试方法共同协作提升软件质量。
 - `TDD`的核心思想是测试先来，实现后来。但如何测试并没有规定非要用代码，所以应根据实际情况，选择最佳的测试手段。
 - 实际测试时应该结合多个框架使用，单元测试 + 集成测试 + UI测试。
- 各种测试方法都有一个共同的目标，保证最终的软件质量。
- 测试的深度和产品业务需求之间需要平衡。不能因为过渡追求完美的测试而阻碍业务的发展，但也不能因为遗漏重要的代码分支逻辑，给最最终的产品带来重大线上bug。

---

<center>
 author: 程涛涛<br/>
 date: 2017-8-10<br/>
 email: taotao.cheng@56qq.com
</center>
<br/>
