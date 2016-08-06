---
layout: post
title: 初学 Python 的一些笔记（02）-与列表有关
date: 2016-07-23
categories: blog
tags: [Python]
description: Python 笔记第2页
---
#1. 列表#

## 如何创建列表 ##

Python 的列表类似于 C++ 的数组，但可以存放不同的数据类型。可以新建普通列表、混合列表与空列表。

例如：

**(1) 普通列表**

    >>> member = [0,1,2,3,4,5]
    >>> member
    [0, 1, 2, 3, 4, 5]

**(2) 混合列表**

    >>> mix = [0,1,3.14,'Clarenous']
    >>> mix
    [0, 1, 3.14, 'Clarenous']

**(3) 空列表**

    >>> empty = []
    >>> empty
    []

**注意：**

列表中的元素也可以是一个列表，例如：

    >>> spec = [0,1,[2,3]]
    >>> spec
    [0, 1, [2, 3]]

## 如何向列表添加元素 ##

**(1) append 方法**

在 Shell 中使用 append 方法可以向某个列表添加一个元素。

    >>> member.append(6)
    >>> member
    [0, 1, 2, 3, 4, 5, 6]

**(2) extend 方法**

使用 extend 方法可以将一个列表添加在另一个列表中，且此方法的参数必须是列表。

    >>> member.extend(mix)
    >>> member
    [0, 1, 2, 3, 4, 5, 6, 0, 1, 3.14, 'Clarenous']

**(3) insert 方法**

append 与 extend 都是将目标添加在了原列表的末尾，而使用 insert 可以在指定位置插入一个元素（可以是一个列表）。

    >>> examp = [0,1,2,3,4]
    >>> examp.insert(0,'list')
    >>> examp
    ['list', 0, 1, 2, 3, 4]

## 如何从列表移除元素 ##

**(1) remove 方法**

使用 remove 方法不需要知道元素在列表的位置，而在参数中写明要去除的元素，则位置靠前的第一个同名元素将被去除。例如：

    >>> mylist = [0,1,2,3,1,4,5]
    >>> mylist.remove(1)
    >>> mylist
    [0, 2, 3, 1, 4, 5]

**(2) del 语句**

使用 del 语句可以去除指定位置的元素，也可以删除整个列表。

    >>> mylist
    [0, 2, 3, 1, 4, 5]
    >>> del mylist[1]
    >>> mylist
    [0, 3, 1, 4, 5]
    >>> del mylist

**(3) pop 方法**

使用 pop 方法可以去除指定位置的元素并返回该元素，当 pop 不带参数时，默认去除列表的最后一个元素。

    >>> list = [0,1,2,3,4,5]
    >>> list.pop()
    5
    >>> list
    [0, 1, 2, 3, 4]

## 列表分片(Slice) ##

对于一个列表 member，可以使用 `member[a:b]` 来进行分片处理，我们就可以得到一个 member 从 a 到 b-1 的拷贝。

    >>> member = [0,1,2,3,4,5]
    >>> member[1:3]
    [1, 2]

也可以省略 a 和 b 的值，例如：

    >>> member[:4]
    [0, 1, 2, 3]
    >>> member[2:]
    [2, 3, 4, 5]

同时省略两个值时，就得到了一个完整的列表的拷贝。

    >>> member_copy = member[:]
    >>> member_copy
    [0, 1, 2, 3, 4, 5]

## 与列表相关的一些其他内置方法 ##

**(1) count 方法**

使用 count 可以统计某元素在某列表中出现的次数。

    >>> list = [0,0,0,1,2,3,0,2,5]
    >>> list.count(0)
    4

**(2) index 方法**

使用 index 可以查看某元素在列表中的位置（索引值），但它只返回该元素第一次出现的位置。

    >>> example = [0,1,2,3,0,3,2,4,0,1]
    >>> example.index(1)
    1

当列表中有多个相同元素，且需要找出某范围 [a,b) 内该元素的位置时，使用 `member.index(element,a,b)` ，例如：

    >>> example = [0,1,2,3,0,3,2,4,0,1]
    >>> example.index(0,1,8)
    4
    >>> example.index(1,2)
    9

**(3) reverse 方法**

使用 reverse 可以将整个列表翻转。

    >>> list = [0,1,[2,3],4,5,6,7]
    >>> list.reverse()
    >>> list
    [7, 6, 5, 4, [2, 3], 1, 0]

**(4) sort 方法**

使用 sort 可以将列表元素排序，默认为从小到大排序。

    >>> list = [23,12,4,2,1,0,34,8,11]
    >>> list.sort()
    >>> list
    [0, 1, 2, 4, 8, 11, 12, 23, 34]

如果需要从大到小排序，可以在参数中做改动。

    >>> list.sort(reverse = True)
    >>> list
    [34, 23, 12, 11, 8, 4, 2, 1, 0]

