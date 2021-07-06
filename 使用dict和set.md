# 使用dict和set

## dict

dict全称dictionary，python内置的字典；在其他语言中也称为map，使用键-值（key-value）存储，具有极快的查询速度。

dict的key值必须是**不可变对象**。

### dict初始化方法

1. **直接创建**

   适用场景: 事先已经拼接出整个字典

```python
dict1 = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
print(dict1['Michael'])
```

2. **动态创建**

   适用场景: 适用于动态创建字典的一个字段

   ```python
   dict2 = {}
   dict2['Adam'] = 67
   print(dict2['Adam'])	# 67
   dict2['Adam'] = 70
   print(dict2['Adam'])	# 70
   ```

3. **关键字创建**

   适用场景: 关键字形式所需的代码比常量少，但键必须为字符串

   ```python
   dict3 = dict(name='Tom', age=40)
   print(dict3)	
   # {'age': 40, 'name': 'Tom'}
   ```

4. **键/值对创建**

   适用场景: 需要把键值逐步建成序列，此形式比较适用

   ```python
   dict4 = dict((['name', 'Tom'], ['age', 40]))
   print(dict4)
   # {'age': 40, 'name': 'Tom'}
   ```

5. **初始化字典**

   适用场景: 所有键的值都相同，此形式非常适用

   ```python
   dict5 = dict.fromkeys(['a', 'b'], 0)
   print(dict5)
   # {'a': 0, 'b': 0}
   ```

6. **zip创建字典**

   适用场景: 创建键列表和值列表，适用此方式比较适合

   ```python
   dict6 = dict(zip(['a', 'b'], [1, 2]))
   print(dict6)
   # {'a': 1, 'b': 2}
   ```

7. **通过字典解析来创建字典**

   适用场景: 动态，灵活地来创建字典

   ```python
   # 示例一
   D = {k:0 for k in 'ab'}
   Print(D)
   # {'a': 0, 'b': 0}
   # 示例二:
   D = {k:v for (k,v) in zip(['a', 'b'], [1, 2])}
   Print(D)
   # {'a': 1, 'b': 2}
   # 示例三:
   D = {k: ord(k) for k in ['A', 'B', 'C', 'D']}
   Print(D)
   # {'A': 65, 'C': 67, 'B': 66, 'D': 68}
   # 示例四:
   D = {c.lower(): c + '!' for c in ['SPAM', 'EGGS', 'HAM']}
   Print(D)
   # {'eggs': 'EGGS!', 'ham': 'HAM!', 'spam': 'SPAM!'}
   ```

### 判断dict中key是否存在

1. 通过`in` 判断

   ```python
   dict1 = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
   'Thomas' in dict1
   # False
   ```

2. 通过`get()`方法判断

```python
dict1 = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
dict1.get('Thomas')
# 返回None
dict1.get('Thomas',-1)
# 返回指定值-1
```

### dict删除

使用`pop(key)`删除key，对应的value也会从dict中删除

```python
dict1 = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
dict1.pop('Bob')
print(dict1)
#{'Michael': 95, 'Tracy': 85}
```

## Set

set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。

主要用于创建一个无序不重复元素集，可进行关系测试，删除重复数据，还可以计算交集、差集、并集等

```python
s = set([1, 1, 2, 2, 3, 3])
print(s)
# {1,2,3}
s = set('eleven')
print(s)
# {'l', 'e', 'n', 'v'}
```

### set添加/删除元素

```python
# add(key)添加
s = set([1, 1, 2, 2, 3, 3])
s.add(4)
print(s)
# {1,2,3,4}
# remove(key)删除
s.remove(3)
print(s)
# {1,2,4}
```

### 交集/并集

```python
s1 = set([1, 2, 3])
s2 = set([2, 3, 4])
print(s1 & s2)
# s1与s2的交集：{2, 3}
print(s1 | s2)
# s1与s2的并
集：{1, 2, 3, 4}
```



