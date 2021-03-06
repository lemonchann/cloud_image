**本书包含Python2.6和Python3.0**
[TOC]
### 第一部分 使用入门
### 第二部分 类型和运算
#### 第4章 介绍Python对象类型
**本章是简明介绍而已**
- 不可变性
> 数字、字符串、元组**不可变**   
列表、字典**可变**
- 列表解析
> ord()返回字符的Unicode编码值   
> 列表解析可以用来创建列表、字典、集合
- 如何破坏代码的灵活性
> 类型检查（不推荐）
> type()、isinstance()
- 完结

#### 第5章 数字
- python表达式操作符

#### 第6章 动态类型简介
- 变量、对象和引用
> 1. 变量在赋值的是时候创建。
> 2. 变量必须在引用之前赋值。
- 类型属于对象而不是变量
> 类型只与对象关联不与变量关联
；对象包含两部分头部信息：类型信息，引用计数；
- 对象的垃圾收集
> 利用引用计数，回收引用计数为0的对象空间。
- 共享引用
> 多个变量引用指向同一个对象
- 共享引用和在原地修改
> 拷贝的三种方法：序列对象用全切片L[:]、字典和序列用X.copy方法、还有标准copy模块import copy
- 共享引用和相等
> 1. 为了提高效率，缓存复用，在没有引用之后小的整数和字符串可能并不立即回收，等待下次被使用
> 2. == 和 is 的区别：== 判断对象的值是否相等
is判断是否是同一个对象的引用，is是更严格的判断
```L1 = [1,2,3] L2=[1,2,3] (L1==L2)True 但(L1 is L2) False```
- ...
- 完结

#### 第7章 字符串
- 与%格式化表达式比较
- 为什么用新的格式化方法

#### 第9章 元组文件及其他
- 引用vs拷贝
> 赋值总是存储对象的引用
- ...
- **内置类型陷阱**（重要）
- 


### 第三部分 语句和语法
#### 第11章 赋值、表达式和打印
- 赋值语句
> **几点重要的特性需要注意。**
- 赋值语句的形式
- 序列赋值
> 这一节有很多有用的赋值技巧
 ```python
#如下交换元素
a, b = b, a #元组赋值，省略了括号而已

#如下两句，等价于front = L.pop(0)
L = [0,1,2,3]
front, L = L[0], L[1:]
 ```
- python3中扩展的序列解包
- 多目标赋值
> 这里有坑，**共享引用** 要注意：   
区分可变对象和不可变对象的多目标赋值   
```python
a = b = 0 #改变b不影响a
L1 = L2 = [1,2,3] #改变L2会影响到L1
```
- 增强赋值语句以及共享引用
> 这里有坑，**共享引用** 要注意

- 变量命名规则
- 表达式语句
> 赋值语句的=不能嵌入到其他表达式中 ，避免和==的混淆操作错误
- 表达式语句和在原处的修改
> L.append(x) 原处修改L 返回值是None
- 打印操作
- 打印流重定向
- 版本独立的打印
- 为什么要注意print和stdout
- **完结**

#### 第12章 if测试和语法规则
- 真值测试
> 1. and or运算返回的是短路求值的对象，不是简单的True和False   
> 2. 比较测试相等测试返回True或False 
- if/else三元表达式
- 为什么要在意布尔值

#### 第13章 while和for循环
- while循环
- break、continue、pass语句
> 当主体语句不是复合语句时可以写在冒号同一行，如：   
> while True: pass    
> if True: pass
- ...   
- for循环
- 一般格式
- 例子
- 为什么要在意文件扫描
- **完结**

#### 第14章 迭代和解析，第一部分
- python3.0中新的可迭代对象
- **完结**

### 第四部分 函数
#### 第16章 函数基础
- 编写函数
>global关键字用来扩大函数内部定义变量的作用域；如果变量本身不在函数内部定义没有必要用global
- def语句是实时执行的
- 完结

#### 第17章 作用域
- python作用域基础
> Pytho没有变量申明，变量创建在变量第一次赋值的时候，并且赋值后才能使用。并且第一次赋值的时候绑定了一个作用域
- 变量名解析：LEGB原则
- ...
- **嵌套作用域举例**
> 1. 所谓嵌套作用域，就是在函数f1中定义的函数f2，在f2中能访问f1作用域内的变量   
> 2. 子小节 **作用域与带有循环变量的默认参数相比较** 重点关注下

- ...
- nonlocal应用，py3引入的
> 1. nonlocal语句允许对嵌套作用域中的变量进行修改，否者是不能修改的，类似c的静态局部变量用来计数比较多。
> 2. nonlocal申明的变量必须在之前已经赋值过，而global申明的变量没有这个要求

- 为什么使用nonlocal
> 这里对比了使用nonlocal保存独立的状态信息、使用global保存、使用类保存、函数属性保存的优缺点
- 本章小结
- **完结**

#### 第18章 参数 
- 传递参数
> Python默认用赋值也就是引用传递参数
- 参数和共享引用
> 这一节有点重要的特殊点：
> **参数赋值对调用者没有影响；对可变对象参数的原处修改对象会有影响**
- 避免可变参数的修改
> 运用拷贝L[:]的方法传递参数，或者tuple(L)
- 任意参数的示例
- 对输出参数进行模拟
- ...
- 为什么要在意：关键字参数
- 本章习题
> 注意习题2这种形式的调用也是合法的：   
定义：def fun(a,b,c):print(a, b, c)   
调用：fun(1, c=1, b=2)
- 完结

#### 第19章 函数的高级话题
- ...
- 循环语句vs递归
- 处理任意结构
> 一般不建议递归，但477页的程序展示了不是线性迭代只能用递归的例子。
- 函数对象：属性和注解
- 间接函数调用
- 函数内省
- 函数属性
- python3.0的函数注解
- 匿名函数lambda
- lambda表达式
- 为什么使用lambda
- 如何不要让pythond代码晦涩难懂
- 嵌套lambda和作用域
- 为什么要在意回调
- 函数式编程 filter和reduce
- **完结**

#### 第20章 迭代和解析， 第二部分
- ...
- 为什么要在意：列表解析和map
- ... 
- 对迭代的各种方法进行计时
> 列表解析比for循环要快一些；生成器比列表解析慢一些但是对内存的要求降到了最低（因为列表解析一次性生成一个列表，而生成器每次返回一个单次的迭代对象，应用在大序列中性能优点才明显）
- ...
- 计时结果
- ...
- 其他建议
- **完结**

### 第五部分 模块
### 第六部分 类和OOP
#### 第25章 OOP:宏伟蓝图
- 属性继承搜索
> 由下到上，由左到右（下指的是子类，上指的基类；左指的是写继承关系时候的表达式左边如C1(C2, C3)其中C2是左）
- ...
- 完结

#### 第26章 类代码编写基础

> 区分**对象和类**：
在继承层次中，子类的同名属性会覆盖基类的方法。  
数据成员保存在对象中，方法保存在类中。
   
> 继承层次的搜索顺序是，子类对象空间->子类空间->基类空间

- 类可以截获python运算符
> 要重载就要定义__xxx__ 双下划线开头和结尾的方法

- 为什么要使用运算符
> 为了让类支持像内置操作符一样的运算操作，比如+  - print等看起来像内置类型一样 

- **完结**
#### 第27章 更多实例
- 步骤1：创建实例
> 1. 类属性的添加最好是通过__init__函数内对self的赋值实现，因为这样构造类的对象时候该对象就一定有相应的属性，避免了对没有赋值的属性的引用导致异常。   
> 2. `if __name__=="__main__"`:有效避免单个程序文件运行于作为模块导入的场景，比如作为单个文件执行可以继续跑一些测试，而模块导入则只使用函数。

- 步骤2：添加行为方法
> 方法就是类的函数，符合函数的任何规范

- 步骤3：运算符重载
> __str__的重载可以对对象调用print

- 步骤4：通过子类定义行为
- 扩展方法：好的方式
> **重点：在子类内部调用基类的方法。**
- 步骤5：定制构造函数
> **再次，重点：在子类构造函数内部调用基类构造函数**

- 步骤6：使用内省工具
- 特殊类属性
> `instance.__class__ ; object.__dict__ #属性map; object.__name__ #类名；instance.__bases__ #基类`
- 一种通用显示工具
> 上一节的应用，通用的打印对象属性工具
- 实例与类属性的关系
> `self.__dict__` 只显示实例的属性，而不是类的
- 工具类的命名考虑
> 
- 工具类的命名考虑
> 类的私有属性通常约定命名`_xxx 单下划线 或者 __xxx 双下划线` 单下划线只是约定不是最好的方法，还可能被子类重写；双下划线是真正唯一；
- 
#### 第28章 类代码编写细节
- 命名空间完整的内容
- ...
- Python命名空间的禅：赋值将变量名分类
> **查看重要例子：各种变量定义的作用范围**
- **完结**

#### 第29章 运算符重载
- ...
- 用户定义的迭代器
- 有多个迭代器对象
- 

### 第七部分 异常和工具
- 

### 第八部分 高级话题
