## Android 自动化测试
#### Google
- [Google 测试支持库 ： AndroidJUnitRunner、Espresso、UI Automator](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#features)
- [Testing Apps on Android](https://developer.android.google.cn/training/testing/index.html)

### 常用工具：money、EasyMonkey、MonkeyRunner、Mockito、powermock、UIAutomator(2)、Roboletric、Robotium、Espresso、Selendroid、Appium、Calabash、Athrun

### 分类：

| 白盒        | 黑盒   |
| :--------:   | :-----:  |
|[AndroidJUnitRunner](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#AndroidJUnitRunner)<br/>[Mockito](http://mockito.org/)<br/>  [powermock](https://github.com/powermock/powermock<br/>)<br/>[Roboletric](http://robolectric.org/)<br/> [Robotium](https://github.com/RobotiumTech/robotium)<br/>[Espresso](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#Espresso)<br/>[Selendroid](http://selendroid.io/) | [money](https://developer.android.google.cn/studio/test/monkey.html)<br/>[MonkeyRunner](https://developer.android.google.cn/studio/test/monkeyrunner/index.html)<br/>[UIAutomator](https://developer.android.google.cn/topic/libraries/testing-support-library/index.html#UIAutomator)<br/>[Appium](http://appium.io/)<br/>[Calabash](http://calaba.sh/)<br/>[Athrun](http://code.taobao.org/p/athrun/wiki/index/)|

#### 实践
 - https://blog.desmondyao.com/mockito-roboletric-test/

#### 各工具差异
- Robotium、Espresso、robolectric、Selendroid ：需要source code，与被测App在同一进程。执行速度快。
- MonkeyRunner：不需要源码、对google官方工具money的封装。
- UIAutomator:不需要source code、google提供的黑盒测试工具与APP在不同进程,但不支持WebView。
- Appium、Calabash：不需要source code，与被App在不同进程，支持WebWiew 和多种语言编写测试脚本，但执行速度慢。
- Athrun：淘宝提供的自动化测试工具，包括自动化测试框架，持续集成体系。

#### [Android测试驱动开发(TDD)](https://blog.desmondyao.com/android-test/)
<center>
<img src="https://blog.desmondyao.com/image/test/tdd-magento.gif" width="50%" height="50%" />
TDD
</center>

#### [代码覆盖率](https://baike.baidu.com/item/%E4%BB%A3%E7%A0%81%E8%A6%86%E7%9B%96%E6%B5%8B%E8%AF%95/8642107?fr=aladdin)
| Java        | JavaScript  |.Net|C/C++|Ruby|
| :--------:   | :-----:  |:-----:  |:-----:  |:-----:  |
| [JaCoCo](http://www.jacoco.org/jacoco/)<br/>[Emma](http://emma.sourceforge.net/)<br/>[Coverlipse](https://sourceforge.net/projects/coverlipse/)<br/>[Cobrertura](http://cobertura.github.io/cobertura/)|[JSCoverage](http://siliconforks.com/jscoverage/)| [ColverNET](http://www.cenqua.com/clover.net/)<br/>[NCover](http://ncover.org/)<br/>[PartCover](https://github.com/sawilde/partcover.net4)<br/>[AQtime](https://support.smartbear.com/viewarticle/42954/)|[Bullseye Coverage](http://www.bullseye.com/)|[rcov](https://github.com/relevance/rcov)|
