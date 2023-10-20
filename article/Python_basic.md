# Python基础



## 1.输入和输出

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



## 2.序列（数据容器）

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

