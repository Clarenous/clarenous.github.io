---
layout: post
title: 初学 Python 的一些笔记（01）
date: 2016-07-21
categories: blog
tags: [Python]
description: Python 笔记第1页
---

**# 1.原始字符串 #**

当需要输出路径等较为复杂的字符串时，可以不用挨个使用 \ 来转义，而是在字符串的引号前加上小写字母 r ，这样输出的就是你的原始字符串。

例如：

    >>> print (r'\nhhh')
    \nhhh

但是使用此方法时，原始字符串的最后一个字符不能是 \ ，否则编译器会报错。解决办法是，例如想要输出“C:\Program Files\Adobe\”，就应把最后一个字符单独拿出来转义：

    >>> str = r'C:\Program Files\Adobe''\\'
    >>> str
    'C:\\Program Files\\Adobe\\'
    >>> print (str)
    C:\Program Files\Adobe\


**# 2.三重引号字符串 #**

需要得到一个跨越多行的长字符串时，可以使用三重引号字符串。例如打印唐诗《静夜思》时，可以这样操作：

    >>> str = """床前明月光，
    疑是地上霜。
    举头望明月，
    低头思故乡。
    """
    >>> str
    '床前明月光，\n疑是地上霜。\n举头望明月，\n低头思故乡。\n'
    >>> print (str)
    床前明月光，
    疑是地上霜。
    举头望明月，
    低头思故乡。


**# 3.关于 BIF #**

BIF 即 Built-in-Functions，内置函数。

在Python 中输入 `dir(__builtins__)`可以查看Python 的内置方法列表（builtins 前后分别有两个下划线），其中小写的就是BIF。

当我们想查看某个BIF 的功能，例如 print()，可以在 Shell 中输入 `help(print)`，会显示详细的英文描述。

例如：

    >>> help (pow)
    Help on built-in function pow in module builtins:
    
    pow(x, y, z=None, /)
    Equivalent to x**y (with two arguments) or x**y % z (with three arguments)
    
    Some types, such as ints, are able to use a more efficient algorithm when
    invoked using the three argument form.
    