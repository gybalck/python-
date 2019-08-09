1.元字符

\b 元字符，代表单词的开头或结尾，也就是单词的分界处

.元字符，表示出了换行符意外的任何字符

*元字符，指定前边的内容可以连续重复使用任意次以使整个表达式得到匹配（可以是0次）

+元字符，匹配一个或多个（至少一个）

\d，匹配一位数字，\d{2}，\d须重复匹配2次

\s匹配任意的空白符，包括空格，制表符(Tab)，换行符，中文全角空格等。\w匹配字母或数字或下划线或汉字

^匹配字符串的开始

$匹配字符串的结束

![1563435053524](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563435053524.png)

2.转义字符

/

3.重复

![1563435110661](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563435110661.png)

4.字符类

中括号[],像[aeiou]就匹配任何一个英文元音字母，[.?!]匹配标点符号(.或?或!

5.分支条件

|

6.分组

小括号()

7.反义

![1563435557937](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563435557937.png)

8.后向引用

**后向引用**用于重复搜索前面某个分组匹配的文本。例如，\1代表分组1匹配的文本。

![1563435799031](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563435799031.png)

9.贪婪与懒惰

贪婪匹配：a.*b，它将会匹配最长的以a开始，以b结束的字符串

懒惰匹配：.*?就意味着匹配任意数量的重复，但是在能使整个匹配成功的前提下使用最少的重复

![1563436588137](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563436588137.png)

10.处理选项

![1563436640382](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563436640382.png)

11.Python提供了re模块来支持正则表达式相关操作，下面是re模块中的核心函数

![1563438344314](C:\Users\gaoyu.lc\AppData\Roaming\Typora\typora-user-images\1563438344314.png)

```
import re


def main():
    username = input('请输入用户名: ')
    qq = input('请输入QQ号: ')
    # match函数的第一个参数是正则表达式字符串或正则表达式对象
    # 第二个参数是要跟正则表达式做匹配的字符串对象
    m1 = re.match(r'^[0-9a-zA-Z_]{6,20}$', username)
    if not m1:
        print('请输入有效的用户名.')
    m2 = re.match(r'^[1-9]\d{4,11}$', qq)
    if not m2:
        print('请输入有效的QQ号.')
    if m1 and m2:
        print('你输入的信息是有效的!')


if __name__ == '__main__':
    main()
```

在字符串前面加上r表示原始字符串，即字符串中不包含转义字符。