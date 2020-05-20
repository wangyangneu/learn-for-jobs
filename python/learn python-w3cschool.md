# python 学习笔记   
1. 打开文件open(),readline()和readlines()返回行的内容，fead()返回字符内容：  
 f.read(5)返回的是前5个字符    
2. 删除文件使用os.remove(), 删除文件加os.rmdir()，但只能删除空文件夹  
3. 变量命名规则：  
必须以字母或下划线字符开头   
只能包含字母数字字符和下划线（A-z、0-9 和 _）
区分大小写  
+号只能相加相同类型的变量3+5或'acd'+'sasd'  
在函数内部创建的变量是局部变量，只在函数内部有效，如果想要在函数外使用，需要global关键字，若外部有全局变量x,函数内使用global x，则全局值将改变  
4. 内置数据类型： 文本str, 数值int float complex, 布尔bool, 序列list tuple range, 映射dict, 集合set frozenset冻结集合不能添加或删除任何元素, 二进制bytes bytearray memoryview，使用type()可以返回对象的数据类型  
5. 字符串方法，a.strip()删除开头和结尾空白字符，a.lower()返回小写的字符串 "Hello, world"->"hello, world"，a.upper()返回大写字符串，a.replace(str1, str2)使用str2替换str1，split分割字符串  
字符串格式，字符串只能和字符串使用+相连，其余需要使用format  
str = "{}aa  , {}"  
str.format(65, 24)  
str的{}中可以给定索引号{1} {0}  字符串用法  
6. 除空值（例如 ()、[]、{}、""、数字 0 和值 None）外，没有多少值会被评估为 False。当然，值 False 的计算结果为 False。  
7. isinstance(200, int)判断是否是同一类型  
8. 列表在末尾添加使用append，在任意位置添加使用insert, str(1, 'a')在第一个位置添加'a',remove()删除指定项目a.remove('bb')，pop()删除指定的索引，若没有指定索引则删除最后一个位置thislist.pop(),del删除指定索引或者完整的列表 del thislist[1] or del thisllist, clear清空整个列表，thislist.copy()或者list(thislist)复制列表，列表的追加如果是元素使用append 如果是列表使用extend，构造列表list(())双括号，thislist.count(value)返回元素value的个数，thislist.index(value)返回value第一次出现的位置，thislist.reverse()颠倒列表顺序，thislist.sort()升序排列 list.sort(reverse=False or True| key=myfunc)默认是升序reverse=false    
9. tuple元组使用的是括号，有序不可变的，若想改变可以先转化成list在转换为tuple, y = list(x), x=tuple(y)，创建元组（'1', '2'）如果只有一个元素需要在后面加逗号（'1',）,元组不可变所以不能删除其中的元素但可以删除整个元组del thistuple，元组也是可以相加的，使用tuple()方法创建元组需要双括号tupel(('1', '2','3')),len(thistuple)计算元组长度，thistuple.count(value) thistuple.index(value)返回value次数和首次出现的位置，没找到会抛出错误异常  
10. 集合是无序和无索引的，花括号，无法确定其显示的顺序，可以通过for in访问，无法通过索引访问元素，集合创建后无法更改，但可以add添加元素，或者使用update将多项添加到集合中。thisset.update(["apple", "orange", "banana"])，使用remove和discard删除指定项目，thisset.clear()清空集合，del thisset删除整个集合。thisset1.update(thisset2)或者thisset1.union(thisset2)都可以将两个集合合并在一起，并且会排除任何重复项  
11. 字典是一个无序的，可变的有索引的集合，花括号，有键和值，thisdict['key']或thisdict.get("key")获取键的值，thisdict.values()返回键的值，thisdict.items()遍历键和值 ，字典是可以嵌套的  
12. if语句不能为空，若无内容，可以使用pass语句  
13. for 循环用于迭代序列（即列表，元组，字典，集合或字符串）。  
14. 函数定义中可以有默认参数，若传递则使用传递值，否则使用默认参数，传递参数时可以使用关键字发放参数，此时参数与顺序无关，与关键字相关  
def my_function(child3, child2, child1):  
. . print("The youngest child is " + child3)  
my_function(child1 = "Phoebe", child2 = "Jennifer", child3 = "Rory")  
15. 