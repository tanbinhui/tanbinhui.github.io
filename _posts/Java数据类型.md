---
layout: post
title: Java基本数据类型
category: Java
tags: [Java]
keywords: Java基本数据类型
---
#### 基本数据类型
-  概念：
    Java提供了8中基本数据类型，他们都不具备对象的特性，没有属性和行为。基本数据是指不可再分的原子数据类型，内存中直接存储改类型的值

-    8种类型分别为boolean、byte、char、double、float、int、long、short
    

序号| 类型名称 | 默认值 | 大小 | 最小值 | 最大值 | 包装类 | 缓存区间
---|---|---|---|---|---|---|---|
 1 | boolean | false | 1B | 0（false）| 1（true）| Boolean | 无
 2 | byte | （byte）0 | 1B | -128 | 127 | Byte | -128～127
 3 | char | '\u0000' | 2B | '\u0000' | '\uFFFF' | Character | （char）0～（char）127
 4 | double | 0.0d | 8B | 4.9e-324 | 1.798e+308 | Double | 无
 5 | float | 0.0f | 4b | 1.4e-45 | 3.4e+3.8 | Float | 无
 6 | int | 0 | 4B | `$-2^{31}$` | `$2^{31}-1$` | Integer | -128~127
 7 | long | 0L | 8B | `$-2^{63}$` | `$2^{63}-1$` | Long | -128~127
 8 | short | (short)0 | 2B | `$-2^{15}$` | `$2^{15}-1$`(32767) | Short | -128~127  
 
---
- 八种数据都有对应的包装类，Java的设计理念是万物皆对象，很多情况下都需要以对象的方式存储。包装类解决了大部分基本数据类型无法解决的的事；泛型类型参数、序列化、类型转换、高频区间数据缓存；
    高频区间内的数据可以直接用==号来判断，而这个区间外的所有数据都会在堆上产生，并且不会复用已有对象。所以包装类型的数据应该都用equals()来判断

- Boolean：使用静态final变量定义，valueOf()就是返回这两个静态值。  
- Byte：使用范围是-128～127，全部缓存  
- Short：表示范围是-32768～32767，缓存范围是-128～127  
- Character：表示范围是0-65535，缓存范围是0-127  
- Long：表示范围[`$-2^{63}$`,`$2^{63}$`-1]，缓存范围是-128～127  
- Integer：表示范围是[`$-2^{31}$`,`$2^{31}$`-1]，缓存范围是-128～127.Integer是唯一可以修改缓存范围的类 在VM options 加入参数 XX:AutoBoxCacheMax=7777,即可设置最大缓存值为7777    

---
- 所有的POJO类属性必须用包装数据类型
- RPC方法的返回值和参数必须使用包转类型
- 所有的局部变量推荐使用包装类型  
</br>
---
- 字符串
    字符串有三种类型；String、StringBuilder、StringBuffer；  
    &ensp;String是immutable对象，对它的任何改动，都是创建一个新的对象，再把引用指向该对象  
    &ensp;StringBuffer则可以在原有对象上进行修改，是线程安全的  
    &ensp;StringBuilder也可以在原有对象上进行修改的，但不是线程安全的，效率比StringBuffer搞

StringBuffer和StringBuilder均继承自AbstractStringBuilder







