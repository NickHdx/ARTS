## Algorithm
[String to Integer \(atoi\)](https://leetcode.com/problems/string-to-integer-atoi/)

题目描述：从字符串提取整数并转换成整数

解题思路：遍历字符串，当遇到第一个非空格时，判断这个字符是否是非数字非加号非减号，是则返回0，否则开始提取并转换数字，直到遇到下一个非数字的字符为止。由于结果可能会超过int 32的范围，所以先用long变量暂存。

源代码：https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_8.java
## Review
[Machine Learning is Fun Part 7: Abusing Generative Adversarial Networks to Make 8-bit Pixel Art](https://medium.com/@ageitgey/abusing-generative-adversarial-networks-to-make-8-bit-pixel-art-e45d9b96cee7)，第七部分，这个系列的最后一部分，介绍了生产式模型（Generative model）以及算法DCGANs（Deep Convolutional Generative Adversarial Networks）。

生产式模型是为了让计算机自己去理解一些概念，并去创造一些数据，比如照片，电影，或者音乐。

DCGANs是如何工作的？

为了建立DCGANs，需要创建两个深度神经网络模型，一个是鉴别器（
Discriminator），用于识别数据的真伪，另一个是生产者（
Generator），用于创造数据。鉴别器尽可能地准确识别数据的真伪，而生产者尽可能地创造让鉴别器难以辨认真伪的数据，两者相互博弈。鉴别器使用的是卷积神经网络算法，而生产者使用反向卷积神经网络算法。

## Tip
Spring boot项目的数据源配置可以写在application.properties配置文件中，但是，如果并不希望把像数据库连接密码这样的敏感信息放在配置文件中，可以先把密码加密保存在某台服务器上，然后实现ApplicationListener接口并重写onApplicationEvent方法，从服务器上将密码取下来，动态加载配置。

参考: [Spring boot application properties load process change programatically to improve security](https://stackoverflow.com/questions/52853647/spring-boot-application-properties-load-process-change-programatically-to-improv#comment92660006_52854064)
## Share
[关于高可用的系统](https://coolshell.cn/articles/17459.html)

延伸阅读：[容错，高可用和灾备](http://www.ruanyifeng.com/blog/2019/11/fault-tolerance.html)
