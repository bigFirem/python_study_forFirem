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

Python中的序列有5种，分别为列表、元祖、集合、字符串、字典



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



### 4）数组



### 5）字符串
