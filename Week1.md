## Algorithm
这是做ARTS的第一周，在leetcode上按照题目序号顺序，做了两道比较简单的算法题，AC之后，再看官方给的Solution，相当的简洁且高效率，自己再接再厉吧 ; ) 以下是源码。
1. [Two Sum](https://leetcode.com/problems/two-sum/)
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] {i, j};
                }
            }
        }
        return null;
    }
}
```
2. [add-two-numbers](https://leetcode.com/problems/add-two-numbers/)
```
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        return addTwoNumbers(l1, l2, 0);
    }

    private ListNode addTwoNumbers(ListNode l1, ListNode l2, int carry) {
        ListNode list = null;
        if (l1 != null && l2 != null) {
            int sum = l1.val + l2.val + carry;
            if (sum < 10) {
                list = new ListNode(sum);
                carry = 0;
            } else {
                list = new ListNode(sum % 10);
                carry = sum / 10;
            }
            list.next = addTwoNumbers(l1.next, l2.next, carry);
        } else if (l1 == null && l2 != null) {
            int sum = l2.val + carry;
            if (sum < 10) {
                list = new ListNode(sum);
                carry = 0;
            } else {
                list = new ListNode(sum % 10);
                carry = sum / 10;
            }
            list.next = addTwoNumbers(null, l2.next, carry);
        } else if (l1 != null) {
            int sum = l1.val + carry;
            if (sum < 10) {
                list = new ListNode(sum);
                carry = 0;
            } else {
                list = new ListNode(sum % 10);
                carry = sum / 10;
            }
            list.next = addTwoNumbers(l1.next, null, carry);
        } else if (carry != 0) {
            list = new ListNode(carry);
        }
        return list;
    }
}
```
## Review
因为最近正在看自然语言处理的书，所以根据浩叔的推荐，在Medium上找了篇机器学习相关的文章来阅读，加深理解。
[Machine Learning is Fun!](https://medium.com/@ageitgey/machine-learning-is-fun-80ea3ec3c471)，文章很浅显易懂，作者也旨在让没有机器学习知识背景的人容易了解或者入门机器学习。
## Tip
目前项目中用到了nginx，这周花时间阅读了下nginx的相关介绍，并在本地搭建和测试了ngix的一些功能。之前对正向代理和反向代理一知半解，现在基本理解了，之后会尝试搭一下梯子。
>**正向代理**是一个位于客户端和目标服务器之间的代理服务器(中间服务器)。为了从原始服务器取得内容，客户端向代理服务器发送一个请求，并且指定目标服务器，之后代理向目标服务器转交并且将获得的内容返回给客户端。正向代理的情况下客户端必须要进行一些特别的设置才能使用。

>**反向代理**正好相反。对于客户端来说，反向代理就好像目标服务器。并且客户端不需要进行任何设置。客户端向反向代理发送请求，接着反向代理判断请求走向何处，并将请求转交给客户端，使得这些内容就好似他自己一样，一次客户端并不会感知到反向代理后面的服务，也因此不需要客户端做任何设置，只需要把反向代理服务器当成真正的服务器就好了。

>ref: [https://www.tuicool.com/articles/M7bAnqy](https://www.tuicool.com/articles/M7bAnqy)
## Share
浩叔专栏中的第72篇《程序员练级攻略：程序员修养》，罗列了很多知识点和书籍，再看一眼底下的评论
>读者：我就问一句：罗列的这些书您都看完了吗?

>作者回复：是的，我都看过。

嗯......我还在新手村，骨灰级，等我。
