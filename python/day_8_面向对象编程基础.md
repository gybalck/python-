1.在Python中，属性和方法的访问权限只有两种，也就是公开的和私有的，如果希望属性是私有的，在给属性命名时可以用两个下划线作为开头

```
class Test:

    def __init__(self, foo):
        self.__foo = foo

    def __bar(self):
        print(self.__foo)
        print('__bar')
```

在实际开发中，我们并不建议将属性设置为私有的，因为这会导致子类无法访问，

所以大多数Python程序员会遵循一种命名惯例就是让属性名以单下划线开头来表示属性是受保护的

`__init__()函数`是特殊函数，用来定义类中属性。

`__str__()`函数同样是特殊函数，用来返回对象的字符串表达式，

对比：不使用__str__():

`s=Student(111,"Bob",18)`
`print(s)`

使用str()：

`def __str__(self):`
`return "学号:{}--姓名:{}--年龄{}".format(self.id,self.name,self.age)`
`s=Student(111,"Bob",18)`
`print(s)`

输出结果分别为：<**main**.Student object at 0x0362EBF0>

​								学号:111–姓名:Bob–年龄18