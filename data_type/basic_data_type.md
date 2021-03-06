<font face="微软雅黑" size="5"><h1 align="center">**Python程序设计**</h1></font>

[toc]

## 1 数字类型
### 1.1 整数
在python中使用基本数据类型不像java、c中要使用数据类型（int、float等）说明，python中可以直接把值赋给变量，python会自动识别变量的数据类型。下面的例子可以说明这一点。

```python
   >>> a=4
   >>> print(type(a))
   <class 'int'>
```
### 1.2 浮点型
浮点数类型与数学中的实数相似，表示带有小数的数值。python中的浮点数必须带有小数部分，小数部分可以是0.python中浮点数表示有两种方法，其一是是十进制形式的一般表示方法，其二是科学计数法。下面是一些例子：
```python
   >>> 1.0+1.3
   2.3
   >>> 1e2+2e2
   300.0
   >>> 100+1E2
   200.0
```
### 1.3 复数型
复数类型表示数学中的的复数。在python中可以用`a+bj`的形式表示复数，其中a表示实部，b表示虚部。下面是一些复数的例子。

```python
   >>> a=10+5j
   >>> b=10+5j
   >>> a+b
   (20+10j)
   >>> a*b
   (75+100j)
   >>> a/b
   (1+0j)
   >>> a-b
   0j
   >>> a**2
   (75+100j)
```
可以使用z.real和z.imag分别获取复数的实数部和虚部。例：

```python
   >>> a.real
   10.0
   >>> (10+5j).imag
   5.0
```
<font color="red">尽管复数的虚部是1或0，也不能省略，即1j，否则python会认为j是一个变量。</font>
### 1.4 运算符
`+ - * /`表示数字之间的加减乘除，就像数学中的加减乘除。`//`表示取两个数的商的整数部分。`**`表示对一个数取多少次方。`%`取一个数除一个数的余数，也就是模运算。下面是一些例子：
```python
   >>> a=5
   >>> b=2
   >>> a+b  #加法运算
   7
   >>> a-b  #减法运算
   3
   >>> a*b  #乘法运算
   10
   >>> a/b  #浮点除法
   2.5
   >>> a//b #整数除法
   2
   >>> a**2 #乘方运算
   25
   >>> a%b  #模运算
   1
```
## 2 字符串类型
### 2.1.1字符串的创建
python中字符串的创建非常简单，如前面所述，python中数据类型不需要使用关键字进行说明，相反，python中用英文单引号`''`和双引号`""`进行标识。在交互式解释器中，输出字符串用引号引起来，特殊字符用反斜杠转义。下面是一些简单的例子：
```python
   >>> str_1='Hi'
   >>> str_2="你好！"
   >>> print(str_1)
   Hi
   >>> print(str_2)
   你好！
```
### 2.1.2在有转义字符的字符串中使用原字符意思。<br>
如果不希望将开头的字符`\`解释为特殊字符(转义字符），则可以通过在第一引号之前添加一个原始字符串`r`来使用原始字符串。
```python
   >>> print('hello\nrunoob')
   hello
   runoob
   >>> print(r'hello\nrunoob')
   hello\nrunoob
```
### 2.1.3 字符串的跨行表示
如果字符串太长，一行不能完全显示，或超过了PEP的建议，可以使用多行字符串显示。字符串跨越多行用三引号：`"""......"""`或`'''......'''`来表示。如以下例子：
```python
   >>> print("""\
   ... gdfgdf
   ... ggggg
   ... """)
   gdfgdf
   ggggg

   >>> print("""
   ... ggfg
   ... ggfdg\
   ... """)

   ggfg
   ggfdg
```
### 2.2 对字符串的一些简单操作
#### 2.2.1字符串的连接
1、使用`+`运算符进行字符串的连接。该方式可以连接任意形式的字符串，即：字符串变量连接字符串常量、字符串常量连接字符串常量、字符串变量连接字符串变量。
```python
   >>> str_1="你好"
   >>> str_2=" 世界!"
   >>> print(str_1+str_2)
   你好 世界!
   >>> print(str_1+" 世界！")
   你好 世界！
   >>> print("你好"+" 世界!")
   你好 世界!
```
2、彼此相邻的两个或多个字符串文字（即用引号引起来的文字）会自动连接在一起。此方法只适用于字符串常量之间的连接，不适用于字符串变量与字符穿常量之间的连接。
```python
   >>> "你好""世界！"
   '你好世界！
   >>> "你好"str_2
   File "<stdin>", line 1
   "你好"str_2
        ^
   SyntaxError: invalid syntax
```
### 2.2.2字符串的索引与切片
1、字符串有两种索引方式，一种是从左到右的顺序，这种方式从0开始；另一种方式的是从右到左，这种方式是从-1开始编码的。当字符串中含有空格时，该空格也占据一个位置，也有索引。
```
   +------+------+------+------+------+------+
   |  S   |   t  |   r  |   i  |   n  |   g  |
   +------+------+------+------+------+------+
   from left to right:
      0       1      2      3      4      5
   from right to left:
     -6      -5     -4     -3     -2     -1
```
可以使用字符串的索引取除字符串中任何一个字符，也可以取出源字符串的一个片段作为子字符串。两种索引可以混合使用。下面是一些例子：
```python
   >>> str="String" 
   >>> str[0] #正序索引取出字符"S"
   'S'
   >>> str[-6] #倒序索引取出字符"S"
   'S'
   >>> str[:2] 
   'St'
   >>> str[:-4]
   'St'
   >>> str[:]
   'String'
   >>> str[1:6]
   'tring'
   >>> str[-5:6]
   'tring'
```
### 2.2.3字符串的一些操作函数
str.lower（） 返回字符串的副本，并将所有大小写的字符转换为小写。<br>
```python
   >>> str_1="Hello World!"
   >>> str_1.lower()
   'hello world!'
```
str.upper（） 返回字符串的副本，并将所有大小写的字符转换为大写。<br>
```python
   >>> str_1.upper()
   'HELLO WORLD!'
```
str.title（） 返回标题的字符串形式，其中单词以大写字母开头，其余字符为小写字母。<br>
```python
   >>> str_2="Hello world!"
   >>> str_2.title()
   'Hello World!'
```
str.lstrip（[字符]） 返回删除了前导字符的字符串的副本。如果省略或None，则字符参数默认为删除空格。该字符参数不是前缀; 而是删除其值的所有组合。
```python
   >>> str_3='hello world!'
   >>> str_3.lstrip('he')
   'llo world!'
   >>> str_3.lstrip('eh')
   'llo world!'
   
   >>> str_4="  hello world!  "
   >>> str_4.lstrip()
   'hello world!
   >>> str_4.lstrip(None)
   'hello world!  '
```
str.rstrip（[字符] ） 返回删除了结尾字符的字符串副本。如果省略或None，则字符参数默认为删除空格。该字 参数不是后缀; 而是删除其值的所有组合。<br>
str.strip（[字符] ） 返回删除前导和尾随字符的字符串的副本。如果省略或None，则字符参数默认为删除空格。该字符参数不是前缀或后缀; 而是删除其值的所有组合.
## 3列表
### 3.1.1列表及其表示
列表由一系列按特定排列顺序排列的元素构成。列表中可以加入数字、字母、以及任何你想加入的内容。这些被加入的内容之间可以没有任何关系，并且列表可以包含不同类型的项目，但通常所有项目都具有相同的类型。列表用`[项目1,项目2,项目3，...,项目n]`表示，各项目之间用半角的逗号分隔。例如：
```python
   >>> list=[1,2,3,4,5,6]
   >>> list
   [1, 2, 3, 4, 5, 6]
   >>> list1=['h','e','l','l','o']
   >>> list1
   ['h', 'e', 'l', 'l', 'o']
   >>> list2=['h','2']
   >>> list2
   ['h', '2']
```
### 3.2.1列表元素的访问
由于列表是一个有序集合，可以像字符串那样使用索引来访问列表中任意一个元素。但是需要注意的是，列表元素的索引从0开始。访问的方法是`listname[index]`。
```python
   >>> list[1]
   2
   >>> list2[1]
   '2'
```
### 3.2.2列表索引与切片
列表与字符串一样，也可以做切片。下面是一些例子：
```python
   >>> list2[1]
   '2'
   >>> list1[:]
   ['h', 'e', 'l', 'l', 'o']
   >>> list1[2:]
   ['l', 'l', 'o']
   >>> list1[-5:5]
   ['h', 'e', 'l', 'l', 'o']
   >>> list1[:3]
   ['h', 'e', 'l']
```
### 3.2.3元素的删除、添加与修改
#### 1、元素的添加
使用方法`listname.append(object)`将项目添加到列表的末尾。
```python
   >>> list1.append(',')  #在列表末尾追加元素
   >>> list1
   ['h', 'e', 'l', 'l', 'o', ',']
```
使用列表相加的方法添加元素。`listname1+listname2`。
```python
   >>> list2=['w','o','r','l','d','!']
   >>> list1+list2  #两个列表相加
   ['h', 'e', 'l', 'l', 'o', 'w', 'o', 'r', 'l', 'd', '!']
```
使用方法`listname.insert(index,object)`插入对象，如果插入对象的索引不是最大，那么插入元素后，其右边的的元素全部向右移动一位。
```python
   >>> list2.insert(2,'h')  #插入元素
   >>> list2
   ['w', 'o', 'h', 'r', 'l', 'd', '!']
```
#### 2、元素的修改
列表元素的修改可以使用索引调用列表元素复制进行修改，下面是一些例子：
```python
   >>> list2=['w', 'o', 'h', 'r', 'l', 'd', '!']
   >>> list2[-1]='o'   #对单个元素进行修改
   >>> list2
   ['w', 'o', 'h', 'r', 'l', 'd', 'o']
   >>> list2[0:2]=['h','l'] #对一个区域进行修改
   >>> list2
   ['h', 'l', 'h', 'r', 'l', 'd', 'o']
```
#### 3、删除列表中的元素
(1)、使用`del listname[index]`方法删除列表中的元素。使用该方法删除元素的条件是，你必须知道你要删除的元素在列表中的哪个位置。
如果只删除个别元素，那么可以使用单个索引来进行删除。
```python
   >>> del list2[2]  #delete single element
   >>> list2
   ['h', 'l', 'r', 'l', 'd', 'o']
```
如果删除的元素是一个连续的区域，可以使用索引一片区域来删除。
```python
   >>> del list2[0:2]  #delete more elements
   >>> list2
   ['r', 'l', 'd', 'o']
```
如果删除的元素是不连续的，而又有多个需要删除，那么可以把要删除的元素用索引方式调用，并用逗号分隔之后排列在`del`后面。
```python
   >>> del list2[0],list2[1] 
   >>> list2
   ['l', 'o']
```
(2)使用方法`listname.pop([index])`删除列表中元素时，它将返回被删除元素，同时将指定元素删除。如果省略索引，`pop()`将默认删除列表最后一个元素。
使用默认索引删除最后一个元素。
```python 
   >>> vehicles=["bus","train","subway","bike","motorbike","taxi"]
   >>> taxi_pop=vehicles.pop()
   >>> vehicles
   ['bus', 'train', 'subway', 'bike', 'motorbike']
   >>> print(taxi_pop)
   taxi
```
指定索引删除指定元素。
```python
   >>> subway_pop=vehicles.pop(2)
   >>> vehicles
   ['bus', 'train', 'bike', 'motorbike']
   >>> subway_pop
   'subway'
```
(3)使用方法`listname.remove(object)`删除列表中的元素。值得注意的是，`remove()`方法只删除列表中第一个与指定元素匹配的元素。
```python
   >>> vehicles.remove("bus")
   >>> vehicles
   ['train', 'bike', 'motorbike']
```
如果要删除的元素不在列表中，那么使用方法`remove()`删除将发生错误。
```python
   >>> vehicles.remove("bus")
   Traceback (most recent call last):
     File "<stdin>", line 1, in <module>
   ValueError: list.remove(x): x not in list
```
由于程序中一旦出现错误，整个程序将会停止运行。为了使程序更加健壮，我们建议使用以下方式进行删除:
```python
   >>> if "bus" in vehicles:
   ...     vehicles.remove("bus")
   ... else:
   ...     print("删除的元素不在列表中！")
   ...
   删除的元素不在列表中！
```
















