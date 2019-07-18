1.@property装饰器

```
def __init__(self, name, age):
        self._name = name
        self._age = age
  # 修改器 - setter方法
    @age.setter
    def age(self, age):
        self._age = age
  # 修改器 - setter方法
    @age.setter
    def age(self, age):
        self._age = age
def main():
	person.age = 22
	print(person.age)
```

可以实现对属性的保护，并且方便对属性进行访问和修改。

2.`__slots__`变量可以限定类中绑定特定的属性：

注意：该方法仅对该类有效，对子类不起作用

```
__slots__ = ('_name', '_age', '_gender')
```

3.对象方法，静态方法和类方法

通常在类中定义的方法都是对象方法，通过对对象发送消息来调用。

静态方法和类方法可以在对象还没创建的情况下使用，都是通过给类发送消息来调用的。

静态方法：

```
@staticmethod
    def is_valid(a, b, c):
        return a + b > c and b + c > a and a + c > b
```

```
Triangle.is_valid(a, b, c)#通过类来调用
```

类方法：

```
 @classmethod
    def now(cls):#类方法的第一个参数约定名为cls，它代表的是当前类相关的信息的对象（类本身也是一个对象，有的地方也称之为类的元数据对象）
        ctime = localtime(time())
        return cls(ctime.tm_hour, ctime.tm_min, ctime.tm_sec)
```

4.类之间的三种关系：继承（is-a)，依赖(use-a)，关联(has-a)

5.继承和多态，子类继承父类的属性和方法，同时自己可以定义新的属性和方法，多态指子类在继承父类方法后，可以对方法进行重写，当调用这个方法时，不同子类有不同的行为，这就叫多态。

抽象类就是不能够创建对象的类，这种类的存在就是专门为了让其他类去继承它，可以通过`abc`模块的`ABCMeta`元类和`abstractmethod`包装器来达到抽象类的效果，如果一个类中存在抽象方法那么这个类就不能够实例化：

```
from abc import ABCMeta, abstractmethod


class Pet(object, metaclass=ABCMeta):
    """宠物"""

    def __init__(self, nickname):
        self._nickname = nickname

    @abstractmethod
    def make_voice(self):
        """发出声音"""
        pass


class Dog(Pet):
    """狗"""

    def make_voice(self):
        print('%s: 汪汪汪...' % self._nickname)


class Cat(Pet):
    """猫"""

    def make_voice(self):
        print('%s: 喵...喵...' % self._nickname)


def main():
    pets = [Dog('旺财'), Cat('凯蒂'), Dog('大黄')]
    for pet in pets:
        pet.make_voice()


if __name__ == '__main__':
    main()
```

6.`__repr__`是python的自我描述方法，相当于print(m),返回该对象实现类的“类名+object at+内存地址”值