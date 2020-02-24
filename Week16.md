## Algorithm
[933. Number of Recent Calls](https://leetcode.com/problems/number-of-recent-calls/)

题目描述：题目比较难理解，特别是题目给出了比较奇怪的样例，有点被误导了。写一个类RecentCounter，类中只包含一个方法ping，该方法有整数参数t，代表某一刻的毫秒数时间。外部会循环调用ping方法，而且每次调用的t值会比上一次调用的t值要大。每次调用ping方法时，要求计算出，之前调用的ping方法的t值，在当前t值指定范围[t-3000, t]之内的调用次数(当前调用也需要计算在内)。

解题思路：这是一个累计的操作，u每次调用ping时需要把t值存储下来，供本次和下次调用做计算。创建一个队列，每次调用ping时，将队列中小于t - 3000的元素出队，将当前t入队，最后返回队列的大小即可。

源代码：[No_933](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_933.java)

## Review & Tip
[An Introduction to Terraform](https://blog.gruntwork.io/an-introduction-to-terraform-f17df9c6d180)
文章介绍了如何使用Terraform来部署AWS资源。

Terraform代码使用的是HCL声明式语言，代码文件以.tf为拓展名，大部分的云计算平台都支持Terraform。

基本命令：
```
terraform init #扫描代码，根据代码中的指定的provider下载相关代码

terraform plan #输出即将要做的一些操作，让你可以review，+表示资源创建，-表示资源删除，~表示资源修改，-+表示资源替换

terraform apply #会先输出即将要做的一些操作，让你可以review。如果没有问题，输入yes，便开始执行操作。

```

<<-EOF和EOF是Terraform中的三小引号的语法，允许你创建多行的字符创而不需要换行符'\n'
```
user_data = <<-EOF#!/bin/bashecho
"Hello, World" > index.htmlnohup busybox
httpd -f -p 8080 &EOF
```

"${...}" 是插入表达式(interpolation)，允许你在字符串中插入变量
```
user_data = <<-EOF#!/bin/bashecho "Hello, World" > index.htmlnohup busybox httpd -f -p "${var.server_port}" &EOF
```

Terraform会在最后把输出(output)变量输出到命令行
```
output "public_ip" {
value = aws_instance.example.public_ipdescription = "The public IP of the web server"}
```

此外文章还大概介绍了AWS的EC2，CLB，ASG这些服务。

这文章是一系列的，共6篇，[A Comprehensive Guide to Terraform](https://blog.gruntwork.io/a-comprehensive-guide-to-terraform-b3d32832baca)。

## Share
[从CODE REVIEW 谈如何做技术](https://coolshell.cn/articles/11432.html)

皓叔还是一如既往的高标准。现在所在的团队只进行过一两次CR，没有能坚持，部分原因可归咎于工期问题，而更多的是因为团队没有找到合适CR方法，人员的CR意识也不高。文章中提到的因没有CR而存在的问题也经常遇到，团队人员有时候得过且过，各扫门前雪，的确应该反思。这篇文章也算是一种激励，团队没有CR也要有自己的CR，多学习，提高自己的代码质量。
