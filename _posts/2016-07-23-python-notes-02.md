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

先更这么多，回来继续写。