# Day：Java基础（循环）
## Java集合
### ArrayList和Array的区别：

* ArrayList长度是动态的；Array长度是静态的，创建后不可变
* ArrayList不可保存基本数据类型，但可保存封装类；Array可直接保存基本数据类型
* ArrayList是Java集合类；而Array是native的程序数据结构
* Array性能上优于ArrayList
* ArrayList类型安全，支持编译时检查；Array不是类型安全，支持运行时检查
* ArrayList显示支持泛型；Array不支持
* ArrayList不支持指定维度；Array支持多维度

## do...while循环
1、do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。如果布尔表达式的值为 true，则语句块一直执行，直到布尔表达式的值为 false。

2、break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块；break 跳出最里层的循环，并且继续执行该循环下面的语句。

3、continue 适用于任何循环控制结构中，作用是让程序立刻跳转到下一次循环的迭代。

## i++和++i
1、i++会先使用i的值，也就是将i的值加载到数据栈，在给i加1，最后使用数据栈中的值。

2、++i会先将i的值加1，再将增加后的值加载到数据栈，再使用数据栈中的值。

3、使用值的时候都是从数据栈顶去取值。

4、`int i = 0;i = i++;`该代码执行后i的值为0。

## int和Integer的区别
 
* int 是基本数据类型，Integer 是包装类
* Java中，会对 -128 到 127 的 Integer 对象进行缓存，当创建新的 Integer 对象时，如果符合这个这个范围，并且已有存在的相同值的对象，则返回这个对象，否则创建新的 Integer 对象