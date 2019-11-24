## Algorithm
[Longest Palindromic Substring](https://leetcode.com/problems/longest-palindromic-substring/)，找字符串中最长的回文子串

字符串最长才1000，最暴力的方式也AC了，源码如下。之后看了官方给的solution，涵盖了一些需要回顾的知识点：最长公共子串问题，通用后缀树，后缀树，前缀树，动态规划以及Manacher解决此问题的有趣算法。
```
public String longestPalindrome(String s) {
	if (s == null || s.length() == 0) {
		return "";
	}
	char[] chars = s.toCharArray();
	int maxBegin = 0;
	int maxEnd = 0;
	int len = chars.length;
	boolean isPalindromic;
	for (int begin = 0; begin < len; begin++){
		for (int end = 0; end < len; end++) {
			isPalindromic = true;
			for (int i = 0; (begin + i) <= (begin + end) / 2; i++) {
				if (chars[begin + i] != chars[end - i]) {
					isPalindromic = false;
					break;
				}
			}
			if (isPalindromic && (end - begin + 1) > (maxEnd - maxBegin + 1)) {
				maxEnd = end;
				maxBegin = begin;
			}
		}
	}
	return s.substring(maxBegin, maxEnd + 1);
}
```
## Review
[Machine Learning is Fun! Part 4: Modern Face Recognition with Deep Learning](https://medium.com/@ageitgey/machine-learning-is-fun-part-4-modern-face-recognition-with-deep-learning-c3cffc121d78)，第四部分讲述如何用深度学习进行人脸识别。步骤大体如下：
1. 检测图像中的人脸 （HOG算法）
2. 摆正并居中检测到的人脸（Face landmark estimation算法）
3. 对人脸进行编码，即量化（CNN算法）
4. 训练分类模型，预测人脸是谁的（SVM算法）

文章结尾还给出了实际样例，可下载下来跑跑。
## Tip
关于java的日历类Calender，有一个需要注意的地方：
调用Calender.getInstance方法获取实例时，Calender默认使用当前日期初始化了，Calendar.MILLISECOND（当前日期毫秒值）的值已经不为0，所以当对实例进行设置时，记得将Calendar.MILLISECOND的值已设置成0，否则对日期进行比较时(after,before,compareTo)，会出现bug，因为日期比较的方法是利用毫秒值进行比较的。

例如，以下日期同样表示'2012-06-30'，但因为毫秒值不一样，比较的结果不尽如人意：
```
SimpleDateFormat dft = new SimpleDateFormat("yyyy-MM-dd");
Date date = dft.parse("2012-06-30");
System.out.println(date.getTime());
System.out.println(dft.format(date));

Calendar calendar1 = Calendar.getInstance();
calendar1.set(2012, Calendar.JUNE, 30, 0, 0, 0);
System.out.println(calendar1.getTimeInMillis());
System.out.println(dft.format(calendar1.getTime()));

Thread.sleep(500);
Calendar calendar2 = Calendar.getInstance();
calendar2.set(2012, Calendar.JUNE, 30, 0, 0, 0);
System.out.println(calendar2.getTimeInMillis());
System.out.println(dft.format(calendar2.getTime()));

System.out.println(calendar1.getTime().compareTo(calendar2.getTime()) == 0);
```
输出：
```
1340985600000
2012-06-30
1340985600035
2012-06-30
1340985600536
2012-06-30
false
```
将Calendar.MILLISECOND毫秒值设置成0，结果才是正确的：
```
SimpleDateFormat dft = new SimpleDateFormat("yyyy-MM-dd");
Date date = dft.parse("2012-06-30");
System.out.println(date.getTime());
System.out.println(dft.format(date));

Calendar calendar1 = Calendar.getInstance();
calendar1.set(2012, Calendar.JUNE, 30, 0, 0, 0);
calendar1.set(Calendar.MILLISECOND, 0);
System.out.println(calendar1.getTimeInMillis());
System.out.println(dft.format(calendar1.getTime()));

Thread.sleep(500);
Calendar calendar2 = Calendar.getInstance();
calendar2.set(2012, Calendar.JUNE, 30, 0, 0, 0);
calendar2.set(Calendar.MILLISECOND, 0);
System.out.println(calendar2.getTimeInMillis());
System.out.println(dft.format(calendar2.getTime()));

System.out.println(calendar1.getTime().compareTo(calendar2.getTime()) == 0);
```
输出：
```
1340985600000
2012-06-30
1340985600000
2012-06-30
1340985600000
2012-06-30
true
```
## Share
[如何降低软件的复杂性？](http://www.ruanyifeng.com/blog/2018/09/complexity.html)
>1. 复杂性的隔离
>2. 接口和实现：好的 class 应该是"小接口，大功能"，糟糕的 class 是"大接口，小功能"。好的设计是，大量的功能隐藏在简单接口之下，对用户不可见，用户感觉不到这是一个复杂的 class。
>3. 减少抛错
