1.字符串的操作

```
    str1 = 'hello, world!'
    # 通过len函数计算字符串的长度
    print(len(str1))  # 13
    # 获得字符串首字母大写的拷贝
    print(str1.capitalize())  # Hello, world!
    # 获得字符串变大写后的拷贝
    print(str1.upper())  # HELLO, WORLD!
    # 从字符串中查找子串所在位置
    print(str1.find('or'))  # 8
    print(str1.find('shit'))  # -1
    # 与find类似但找不到子串时会引发异常
    # print(str1.index('or'))
    # print(str1.index('shit'))
    # 检查字符串是否以指定的字符串开头
    print(str1.startswith('He'))  # False
    print(str1.startswith('hel'))  # True
    # 检查字符串是否以指定的字符串结尾
    print(str1.endswith('!'))  # True
    # 将字符串以指定的宽度居中并在两侧填充指定的字符
    print(str1.center(50, '*'))
    # 将字符串以指定的宽度靠右放置左侧填充指定的字符
    print(str1.rjust(50, ' '))
    str2 = 'abc123456'
    # 从字符串中取出指定位置的字符(下标运算)
    print(str2[2])  # c
    # 字符串切片(从指定的开始索引到指定的结束索引)
    print(str2[2:5])  # c12
    print(str2[2:])  # c123456
    print(str2[2::2])  # c246
    print(str2[::2])  # ac246
    print(str2[::-1])  # 654321cba
    print(str2[-3:-1])  # 45
    # 检查字符串是否由数字构成
    print(str2.isdigit())  # False
    # 检查字符串是否以字母构成
    print(str2.isalpha())  # False
    # 检查字符串是否以数字和字母构成
    print(str2.isalnum())  # True
    str3 = '  jackfrued@126.com '
    print(str3)
    # 获得字符串修剪左右两侧空格的拷贝
    print(str3.strip())
```

2. 列表的操作

   ```
       list1 = [1, 3, 5, 7, 100]
       print(list1)
       list2 = ['hello'] * 5
       print(list2)
       # 计算列表长度(元素个数)
       print(len(list1))
       # 下标(索引)运算
       print(list1[0])
       print(list1[4])
       # print(list1[5])  # IndexError: list index out of range
       print(list1[-1])
       print(list1[-3])
       list1[2] = 300
       print(list1)
       # 添加元素
       list1.append(200)
       list1.insert(1, 400)
       list1 += [1000, 2000]
       print(list1)
       print(len(list1))
       # 删除元素
       list1.remove(3)
       if 1234 in list1:
           list1.remove(1234)
       del list1[0]
       print(list1)
       # 清空列表元素
       list1.clear()
       print(list1)
   ```

3.列表的生成式语法：f = [x for x in range(1,10)]和f=(x for x in range(1,10))的区别，一个是列表，所有数据都在内存中，如果有海量数据就很耗内存，生成器是可以迭代的，但只可以读取它一次，因为用的时候才生成。

4.yield关键字，相当于return，并且记住这个位置，下次迭代从这个位置开始，带有yield的函数就变成了生成式函数

5.元组：使用小括号，相当于不能修改元素的列表

  列表转换元组，元组转换列表：t=[a,b,c],p=tuple(t),t=list(p)

6.字典，由键值对组成：scores = {'骆昊': 95, '白元芳': 78, '狄仁杰': 82}，通过键可获取对应值

7.

```
    days_of_month = [
        [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31],
        [31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    ][is_leap_year(year)]
```

**列表自带判断条件**

8.rfind()函数，表示最后出现该字符的位置

9.enumerate()函数，将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中。

10.sample(序列a，n)

功能：从序列a中随机抽取n个元素，并将n个元素生以list形式返回。

11.pop()和apend的函数，删除最后一个元素，添加一个元素。