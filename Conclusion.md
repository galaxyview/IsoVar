# Problem

## 1.适配

### 1.1源程序中的适配
- IsoVar程序中需要对几个path进行配置，其针对不同系统对用户输入的path进行了修正，但其中只包含了linux和windows，由于我的电脑是Macos，所以需要补写一个函数。
- IsoVar是一个maven工程，在idea中打开时，需要先配置好maven。

### 1.2JDK版本
- 在测试中，我的电脑安装了JDK19，导致工程无法正常运行，之后转而尝试17 15等，直到JDK11时，程序才得以正常运行。
- 对于defects4j而言，其签出的工程往往设定版本为1.5或1.4，需要对设置文件进行重新配置，与本机环境相匹配。
- 对于可以正常运行的JDK版本，其运行效果也不一致，例如对于Time项目的analyze phase而言，其在JDK11下可以正确执行，而在JDK1.8.0_u352下就会超时。
  
### 1.3系统环境
- 测试了不同系统下的运行情况，当Linux，Windows，Macos均使用同一版本JDK的情况下，运行效果也存在较大差异，例如Time项目的analyze phase，在Macos和Linux下就会超时，在windows上可以正常运行。
- 测试了不同电脑下的运行情况，使用另一台windows电脑时，和本机相比，运行情况也不一致，相同项目在一台上可以完成analyze phase而另一台上则超时。

进一步计划先就已经分析并导出的数据做一些工作，运行适配问题再逐步解决。

I've downloaded the source code of IsoVar, however. when running the analyze phase on some datasets, overtime error usually  occurs unexpectedly, even on the dataset that had been executed successfully.

***Environment I have used***
- Windows11 Java11.0.17
- Windows11 Java1.8.0_352
- Ubuntu 22.03 Java11.0.17
- MacOS13.0.1 Java11.0.17