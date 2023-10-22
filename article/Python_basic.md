# Python基础

## 

## 1.python语法

python的语法和C/C++、Java最明显的不同的一点就是，python使用缩进来替代大括号表示代码块，强调了代码的可读性。

同时，python和Java一样，是一门强类型的语言，不同的是python不需要显示的声明变量的数据类型。

并且，python是一门解释性语言，代码不需要显示编译，可以直接运行



## 2.注释和标识符

### 1）单行注释

单行注释使用 # 作为标识

如果单行注释在当前行代码后，需要间隔两个空格位置

```python
# 这是一个单行注释
print('大吉大利，今晚吃鸡')  # 这是一个单行注释
```



### 2）多行注释

多行注释使用 ''' ''' 作为标识

```python
'''
这是一个多行注释
这是一个多行注释
这是一个多行注释
'''
```



### 3）标识符

python中的标识符，仅允许使用英文、数字、下划线、中文（不推荐使用中文）

必须以字母、下划线开头，不允许数字开头，同时不允许使用python的保留字作为标识符

```python
# 合规的标识符
my_variable = 42
user_name = "Alice"
MAX_SIZE = 100
ClassA = "Hello"

# 不合规的标识符
my_variable = 42
user_name = "Alice"
MAX_SIZE = 100
ClassA = "Hello"

```



## 3.变量、运算符、数据类型、数据类型转换

### 1）变量

变量的定义

> 变量是用于存储数据的标识符。在Python中，不需要显式声明变量的类型，它们会根据赋予的值自动确定数据类型。

```python
# 定义一个变量 ---> 变量名 = 变量值
name = 'kunkun'
age = 25
```

### 

### 2）运算符

```python
''' 数学运算符 '''
# 加法运算符
result = 5 + 3  # 结果为8
# 减法运算符
result = 7 - 2  # 结果为5
# 乘法运算符
result = 4 * 6  # 结果为24
# 除法运算符
result = 10 / 3  # 结果为3.3333333333333335
# 取模运算符
result = 10 % 3  # 结果为1
# 整除运算符
result = 10 // 3  # 结果为3
# 幂运算符
result = 2 ** 3  # 结果为8

''' 比较运算符 '''
# 等于运算符
result = 5 == 5  # 结果为True
# 不等于运算符
result = 7 != 3  # 结果为True
# 小于运算符
result = 4 < 7  # 结果为True
# 大于运算符
result = 8 > 6  # 结果为True
# 小于等于运算符
result = 5 <= 5  # 结果为True
# 大于等于运算符
result = 7 >= 8  # 结果为False

''' 逻辑运算符 '''
# 逻辑与运算符
result = True and False  # 结果为False
# 逻辑或运算符
result = True or False  # 结果为True
# 逻辑非运算符
result = not True  # 结果为False

''' 位运算符 '''
# 按位与运算符
result = 0b1100 & 0b1010  # 结果为0b1000（8）
# 按位或运算符
result = 0b1100 | 0b1010  # 结果为0b1110（14）
# 按位异或运算符
result = 0b1100 ^ 0b1010  # 结果为0b0110（6）
# 按位取反运算符
result = ~0b1100  # 结果为-13
# 左移位运算符
result = 5 << 2  # 结果为20
# 右移位运算符
result = 20 >> 2  # 结果为5

''' 赋值运算符 '''
# 赋值运算符
x = 5
# 复合赋值运算符
x += 3  # 等同于 x = x + 3，结果为8

''' 特殊运算符 '''
# 身份运算符（is）
a = [1, 2, 3]
b = a
result = a is b  # 结果为True
# 不是身份运算符（is not）
c = [1, 2, 3]
result = a is not c  # 结果为True
```



### 3）数据类型

1. **整数（int）**：用于表示整数值，例如：-1、0、1、100等。
2. **浮点数（float）**：用于表示浮点数，即带小数点的数字，例如：3.14、-0.5、1.0等。
3. **字符串（str）**：用于表示文本数据，由字符组成，例如："Hello, World"、'Python'等。
4. **布尔值（bool）**：用于表示真值或假值，只有两个可能的值：True和False。
5. **列表（list）**：用于存储一组有序的数据，可以包含不同类型的元素，例如：[1, "apple", 3.14, True]。
6. **元组（tuple）**：类似于列表，但是不可变的，用圆括号表示，例如：(1, "apple", 3.14, True)。
7. **集合（set）**：用于存储一组唯一的元素，不包含重复值，例如：{1, 2, 3}。
8. **字典（dictionary）**：用于存储键-值对的映射关系，类似于关联数组，例如：{'name': 'Alice', 'age': 30}。
9. **字节串（bytes）**：用于表示字节数据，常用于处理二进制数据。
10. **字节数组（bytearray）**：类似于字节串，但是可变的。
11. **复数（complex）**：用于表示复数，例如：3 + 4j。
12. **空值（None）**：表示一个特殊的空值或缺失值。
13. **自定义类（class）**：您可以创建自定义类来定义自己的数据类型，包括属性和方法。

> 其中，int、float、str、bool、bytes属于基本数据类型，也是最常用的数据类型
>
> list、tuple、set、dictionary、bytearray属于基本数据结构，详细讲解可以跳到序列讲解
>
> complex、none、class暂时不讲，后面再详细展开



### 4）数据类型转换

1. **整数转换（int()）**：将其他数据类型转换为整数。

```python
pythonCopy codefloat_num = 3.14
int_num = int(float_num)  # 将浮点数转换为整数，结果为3
```

1. **浮点数转换（float()）**：将其他数据类型转换为浮点数。

```python
pythonCopy codeint_num = 5
float_num = float(int_num)  # 将整数转换为浮点数，结果为5.0
```

1. **字符串转换（str()）**：将其他数据类型转换为字符串。

```python
pythonCopy codenumber = 42
string_num = str(number)  # 将整数转换为字符串，结果为'42'
```

1. **布尔值转换（bool()）**：将其他数据类型转换为布尔值。

```python
pythonCopy codezero = 0
non_zero = 42
bool_zero = bool(zero)  # 将整数0转换为False
bool_non_zero = bool(non_zero)  # 将非零整数转换为True
```



## 4.输入和输出

### 1）输入

> python中提供了input函数获取用户的输入，返回值默认是字符串类型，需要根据需要转换为其它类型

```python
name = input("请输入您的姓名：")

age = input("请输入您的年龄：")
age = (int)age
```



### 2）输出

> python中提供了print函数将内容输出到控制台或标准输出

```python
# 格式化输出
# 方式1
print("My name is %s and I am %d years old." % (name, age))
# 方式2 ：python3.6及更高版本支持
print(f"My name is {name} and I am {age} years old.")

# 输出到文件
with open("output.txt", "w") as file:
    print("Hello, World!", file=file)
```



## 5.序列（数据容器）

Python中的序列有6种，分别为列表、元祖、集合、字典、字符串、字节数组



### 1）列表list

列表的定义

```python
my_list = [0,1,2,3,4] # 定义一个列表
my_list1 = [] # 定义一个空列表
my_list = list() # 定义一个空列表
```

列表的索引

> 列表的索引是从0开始的，并且支持反向索引，反向索引从-1开始

列表存储的数据类型

> 列表存储的数据的类型可以不一样，并且支持列表间的嵌套

列表的常用方法

```python
my_list = [0,1,2,3,4,5]

# 取出数据
print(my_list[0]) # 取出下标为0的数据
print(my_list[-1]) # 取出下标为-1的数据（倒数第一个数据）

# 追加数据
my_list.append(6) # 追加方式1
my_list.append(["a","b","c"]) # 追加方式2

# 删除
# 方式1：删除下标为2的元素，结果为[0,1,3,4,5]
del my_list[2] 
 # 方式2：删除值为2的元素，返回删除后的列表，结果为[0,1,3,4,5]
res = my_list.remove(2)
# 方式3：删除下标2为的元素，并将其返回，结果为[0,1,3,4,5]
res = my_list.pop(2) 
res = my_list.pop() # 空参则移除列表最后一个元素
```



### 2）元祖 tuple

元祖的定义

> 元祖是一个有序、不可变的数据结构。
>
> 元祖中的元素可以是不同的数据类型
>
> 元祖支持嵌套

```python
my_tuple = (1,2,3) # 定义一个元祖
empty_tuple = () # 定义一个空元祖
single_tupel = (1,) # 定义一个单个数据的元祖
nums_tuple = (1,2,3,"a","b","c") # 定义一个含有不同数据类型的元祖
nested_tuple = ((1, 2), (3, 4), (5, 6)) # 定义一个嵌套的元祖
```

元祖的索引

> 元祖的索引从0开始，并且支持反向索引，反向索引从-1开始

```python
my_tuple = (1,2,3,"a","b","c")
print(f"第1个索引对应的值为：{nums_tuple[0]}")
print(f"最后1个索引对应的值为：{nums_tuple[-1]}")
```

元祖的常用方法

```python
# count(value)：返回指定元素在元组中出现的次数。
fruits = ("apple", "banana", "orange", "apple")
count = fruits.count("apple")
print(count)  # 输出: 2

# index(value)：返回指定元素在元组中首次出现的索引。
fruits = ("apple", "banana", "orange", "apple")
index = fruits.index("banana")
print(index)  # 输出: 1

# list(),转换为列表。tuple(),转换为元祖
fruits = ("apple", "banana", "orange")
fruits_list = list(fruits)  # 转换为列表
fruits_list.append("pear")  # 修改列表，添加新元素
fruits = tuple(fruits_list)  # 转换回元组
print(fruits)  # 输出: ("apple", "banana", "orange", "pear")
```



### 3）集合set

集合的定义

> 集合是一组无序、不重复的的数据集合
>
> 集合中的元素是唯一的
>
> 集合中的元素的数据类型可以不同，但必须是可哈希的数据类型

```python
empty_set1 = {}  # 定于一个空集合，实际上创建的是一个空字典
empty_set2 = set()  # 定义一个空集合
my_set1 = {1, 2, 3, "a", "b", "c"}  # 定义一个集合
my_set2 = set([1, 2, 3, "a", "b", "C"])  # 定义一个集合
try:
	error_set = {[1, 2], [3, 4], [5, 6]}  # 集合中元素的类型必须是可哈希的，不然会报TypeError。列表list是不可哈希的数据类型
except TypeError:
print("捕获到TypeError")
```

集合的常用方法

```python
# 添加元素
my_set.add(4)

# 删除元素：使用 remove() 方法删除集合中的元素。如果元素不存在，会引发 KeyError。如果希望避免引发异常，可以使用 discard() 方法
my_set.remove(3)
my_set.discard(5)

# 清空集合：使用 clear() 方法清空集合中的所有元素
my_set.clear()

# 集合支持各种集合操作，如并集、交集和差集。这些操作可以使用方法或运算符进行。
set1 = {1, 2, 3}
set2 = {3, 4, 5}

union_set = set1.union(set2) # 并集
union_set = set1 | set2 # 或者使用运算符

intersection_set = set1.intersection(set2) # 交集
intersection_set = set1 & set2 # 或者使用运算符

difference_set = set1.difference(set2) # 差集
difference_set = set1 - set2 # 或者使用运算符
```



### 4）字典dictionary

字典的定义

> 字典是一种以键-值对的方式存储元素的数据结构
>
> 字典的元素是无序的
>
> 字典的键值是唯一的
>
> 字典的键值是不可变的，通常为字符串，数字、元祖
>
> 字典支持嵌套

```python
# 创建一个字典：使用{}，键值对之间使用冒号分隔
my_dict = {'name': 'Alice', 'age': 30, 'city': 'New York'}

# 创建一个字典：使用dict()方法
another_dict = dict(name='Bob', age=25, city='San Francisco')

# 创建一个字典：嵌套
person = {
    'name': 'Alice',
    'address': {
        'street': '123 Main St',
        'city': 'New York'
    }
}
```

访问字典中的元素

```python
# 可以使用键值来访问字典中的元素
name = my_dict['name']
age = my_dict['age']

# 如果键值不存在，则会引发KeyError异常，可以使用get()方法避免
name = my_dict.get('name', 'unknown') # 如果键不存在，返回unknown
```

字典的常用操作

```python
''' 增删改 '''
# 添加数据
my_dict['hobby'] = 'basketball'
# 删除数据
del my_dict['name'] # 使用del
my_dict.pop('name') # 使用pop()
# 修改数据
my_dict['name'] = 'kunkun'

''' 常用方法 '''
# keys() 返回字典所有键
keys = my_dict.keys()
# values() 返回字典所有值
values = my_dict.values()
# items() 返回字典所有键值对（以元祖tuple的形式）
items = my_dict.items()
# update() 将一个字典的键值对合并到另一个字典中
my_dict.update(another_dict)
# clear() 清除字典中的所有元素
my_dict.clear()
```



### 5）字符串strings

字符串的定义

> 字符串是python中的一种基本数据类型
>
> 字符串是不可变，如果需要修改字符串，则必须创建一个新的字符串

```python
# 使用单引号创建字符串
my_string = 'Hello, World!'
# 使用双引号创建字符串
another_string = "Python is great!"
# 使用三重引号创建多行字符串
multi_line_string = '''This is a
multi-line
string.'''
```

字符串的索引和切片

> 字符串支持索引访问和切片操作

```python
# 使用索引
my_string = 'Python'
first_char = my_string[0]  # 结果为 'P'

# 使用切片
sub_string = my_string[2:4]  # 结果为 'th'
```

字符串的常用操作

```python
# 字符串的连接
greeting = 'Hello, '
name = 'Alice'
message = greeting + name  # 结果为 'Hello, Alice'

# 字符串的重复
repeat_string = 'abc' * 3  # 结果为 'abcabcabc'

# 字符串的方法
text = 'Python is a powerful programming language.'
text.lower()  # 转换为小写
text.upper()  # 转换为大写
text.find('is')  # 查找子字符串的位置
text.replace('Python', 'Java')  # 替换文本

# 字符串的格式化
name = 'Alice'
age = 30
formatted_string = f"My name is {name} and I am {age} years old."
```



### 6）字节数组byte-array

字节数组的定义

> 字节数组是一个存储字节数据的数据结构，元素是字节（0-255的整数）
>
> 字节数组是一个可变的序列，允许修改
>
> 字节数组常用于存储二进制数据，例如图形、音频、网络通信、文件操作

```python
# 创建字节数组
my_bytearray = bytearray()
data = bytearray(b'hello')
```

字节数组的访问

```python
my_bytearray = bytearray(b'hello')
first_byte = my_bytearray[0]  # 获取第一个字节
```

字节数组的常用操作

```python
''' 增删改 '''
# 修改元素
my_bytearray[1] = 101  # 修改第二个字节为101
# 添加元素
my_bytearray.append(111)  # 在末尾添加字节111
# 删除元素
del my_bytearray[2]  # 删除第三个字节

''' 常用方法 '''
my_bytearray.find(b'lo')  # 查找子字节数组的位置
my_bytearray.replace(b'hello', b'world')  # 替换字节数组中的内容
my_bytearray[:3]  # 切片字节数组

''' 字节数组和字符串之间的转换 '''
my_bytearray.decode('utf-8')  # 将字节数组转换为字符串
'hello'.encode('utf-8')  # 将字符串转换为字节数组
```



### 总结

- list集合，多类型、可变、可嵌套、有序、不唯一
- set集合，多类型、可变、可嵌套、无序、唯一、必须可哈希
- tuple元祖，多类型、不可变、可嵌套、有序、不唯一
- dictionary字典，多类型、键值对、可变、可嵌套、无序、键值唯一且不可变
- strings字符串，单类型、字符、不可变
- bytearray字节数组，单类型、字节、可变



## 6.代码结构

python常见的代码结构通常包括模块Module、函数Function、条件语句Conditional Statements、循环语句Loop Statements、异常处理Exception Handling



### 1）模块Module

模块的定义

> 模块就是一个python文件，包含一组相关的函数、变量和类。
>
> 模块可以被导入到其它python文件中，便于重复使用代码

```python
# 模块示例（module_example.py）
def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

if __name__ == "__main__":
    # 在模块中编写的测试代码
    result = add(5, 3)
    print(result)
```

补充：

> `if __name__ == '__main__':` 是一个常见的Python编程约定，用于确定一个脚本文件是否正在直接运行，还是被作为模块导入到其他脚本中。这个约定通常用于在一个Python文件中定义可执行代码和模块导入时执行的代码，以便将脚本文件和模块导入分开。
>
> 当一个Python脚本文件被执行时，Python解释器会设置特殊变量`__name__`的值。如果脚本文件是直接执行的，`__name__` 的值将被设置为`'__main__'`。如果脚本文件被导入为一个模块，`__name__` 的值将被设置为模块的名称。
>
> 因此，`if __name__ == '__main__':` 的目的是检查 `__name__` 的值是否等于 `'__main__'`，如果条件成立，就执行其后的代码块。这意味着这部分代码仅在脚本文件直接运行时才会执行，而在被导入为模块时不会执行。



### 2）函数Function

函数的定义

> 函数是一段可重复使用的代码块，接受参数并执行特定任务。函数通常用于模块化代码，提高可读性和维护性。

```python
def greet(name):
    print(f"Hello, {name}!")

# 调用函数
greet("Alice")
```



### 3）条件语句Conditional Statements

条件语句的定义

> 条件语句用于根据条件执行不同的代码块，从而控制程序的流程。

```python
''' 模板
if condition:
    # 当条件为True时执行
    pass
elif another_condition:
    # 当第一个条件为False，但第二个条件为True时执行
    pass
else:
    # 当所有条件都为False时执行
    pass
'''

''' 示例如下：猜数字游戏。设定一个答案，根据输入的数字和答案对比，打印不同的结果 '''
res = 10
num = input('请输入你的数字：')
num = int(num) # 是否记得前面提过的，input()函数接收的数据类型默认是str，想要进行比较的话，需要转为int类型噢
if num > 10:
	print('你输入的数字比答案大了')
elif num < 10:
    print('你输入的数字比答案小了')
else:
    print('恭喜你，答案正确')
```



### 4）循环语句Loop Statements

循环语句的定义

> 循环语句用于多次执行一段代码块
>
> `python`中循环有两种结构，for循环和while循环
>
> `for`循环常用于迭代（遍历）可迭代对象（list、set、tuple、dictionary、str等）。工作原理是依次将可迭代对象中的每个元素赋值给循环变量，直至遍历完可迭代对象中的所有元素。循环遍历过程中，可以通过break和continue两种方式来控制循环的行为。break是结束整个for循环，continue是跳过当前for循环的这一次迭代
>
> `while` 循环是一种条件控制的循环结构，它会反复执行一组语句，直到条件变为 `False`。常用于需要动态循环次数的的迭代。迭代过程中，也可以像`for`循环一样，使用break和continue语句来控制循环行为。

```python
''' for循环 '''
fans =  ['ikun01', 'ikun02', 'ikun03']
for fan in fans:
    print(fan)
# 运行结果是依次打印ikun01，ikun02，ikun03
for fan in fans:
    if fan == 'ikun02':
        break # 结束当前for循环
    else:
        print(fan)
# 运行结果为仅打印ikun01。因为当if条件成立后，for循环结束了

for fan in fans:
    if fan == 'ikun02':
        continue # 跳过当前这一次迭代，进入下一次迭代
    else:
        print(fan)
# 运行结果为依次打印ikun01，ikun03。因为当迭代到fan = ikun02时，触发了if条件，跳过了本次迭代。
```

```python
''' while循环 '''
count = 0
while count < 5:
    print(count)
    count += 1
# 运行结果为01234
```



### 5）异常处理Exception Handling

异常处理的定义

> 异常处理用于处理代码执行中可能出现的异常情况。`try`、`except`、`finally`关键字用于捕获和处理异常。
>
> `try`代码块是可能出现的异常，`except`代码块是指定`try`代码块中出现的某一异常的处理逻辑，`finally`代码块是必然执行的逻辑，不论`try`代码块中是否出现异常

```python
try:
    result = 10 / 0  # 会引发ZeroDivisionError异常
except ZeroDivisionError:
    print("除数不允许为0")
finally:
    print("异常结束")
```



## 7.文件操作

### 1）打开文件

`python`提供了一个内置的`open()`函数，通过传入`文件名参数`和`打开模式参数`。

`文件名参数`可以包括文件的相对路径或绝对路径，如果仅传入文件名，默认从当前项目路径寻找。

`打开模式参数`包括6种。分别为

- `"r"`：读取模式（默认）。用于打开文件以供读取，如果文件不存在会引发异常。
- `"w"`：写入模式。用于打开文件以供写入，如果文件存在，会截断文件内容；如果文件不存在，会创建新文件。
- `"a"`：追加模式。用于打开文件以供追加数据，如果文件不存在，会创建新文件。
- `"x"`：独占创建模式。用于创建新文件，如果文件已存在，则引发错误。
- `"b"`：二进制模式。用于以二进制模式打开文件，例如读取或写入二进制数据。
- `"t"`：文本模式（默认）。用于以文本模式打开文件，适用于读取或写入文本数据。

```python
# 打开一个文本文件进行读取
file = open("example.txt", "r")

# 打开一个文本文件进行写入（如果文件不存在，则创建）
file = open("example.txt", "w")
```



`python`中的标准库提供了一个os模块，可以使用这个模块中的功能来检查文件是否存在

```python
import os  # 引入os模块

# 查看当前文件目录
cur_directory = os.getcwd()
    print(f"cur_directory is {cur_directory}")
    
# 检查文件是否存在
if os.path.exists("file_to_check.txt"):
    print("文件存在")
else:
    print("文件不存在")
```



### 2）读取文件

`python`提供了3个内置的函数来读取文件内容，分别是

- read()：一次性读取整个文件的内容，并将其存储为一个字符串
- readLine()：逐行读取文件的内容，以字符串返回，每次调用会返回文件中的下一行
- readLines()：将文件中的每一行以字符串返回，然后存储在一个列表中

```python
# read()
with open("example.txt", "r") as file:
    file_content = file.read()
    print(file_content)

# readLine()
with open("example.txt", "r") as file:
    line = file.readline()
    while line:
        print(line)
        line = file.readline()

# readLines()
with open("example.txt", "r") as file:
    lines = file.readlines()
    for line in lines:
        print(line)
```



### 3）写入文件

`python`提供了两个函数来写入，传入参数为写入内容

- `write()`：写入指定的传入的数据
- `writelines()`：一次性写入多行数据，传入参数为一个list集合

```python
# write()
with open("output.txt", "w") as file:
    file.write("Hello, World!")

# writes()
lines = ["Line 1\n", "Line 2\n", "Line 3\n"]
with open("output.txt", "w") as file:
    file.writelines(lines)
```



### 4）关闭文件

`python`中，打开文件执行完文件操作后需要关闭已打开的文件，有两种方式

- 使用显示调用`close()`方法来关闭文件
- 使用`with`语句，在代码块中完成对文件的操作，最后隐式调用`close()`方法

```python
# 显示调用close()
file = open("example.txt", "r")
content = file.read()
file.close()  # 手动关闭文件

# 使用with，隐式调用close()
with open("example.txt", "r") as file:
    content = file.read()
```

补充

> 在使用 `with` 语句时，无需显式调用 `close()`，这是因为 `with` 语句会自动处理关闭文件的操作，即使在发生异常时也会执行。这有助于确保文件被正确关闭，不会产生资源泄漏。最佳实践是在需要打开文件时始终使用 `with` 语句。



### 5）复制、删除、重命名文件

对于复制、删除、重命名三个文件操作，可以使用`python`标准库中的`shutil`模块来实现

```python
import shutil # 引入shutil模块

# 复制文件
shutil.copy("source.txt", "destination.txt")

# 删除文件
os.remove("file_to_delete.txt")

# 重命名文件
os.rename("old_name.txt", "new_name.txt")

```

补充

> 在执行这些操作时，出现异常的可能性较大，例如文件不存在或文件权限不足等。因此在执行这些操作时，最好提前进行错误处理