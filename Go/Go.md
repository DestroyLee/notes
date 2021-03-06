# Go

## 最佳实践和建议

* 尽可能的使用:=去初始化声明一个变量（在函数内部）
* 尽可能的使用字符代替字符串
* 尽可能的使用切片代替数组
* 尽可能的使用数组和切片代替映射
* 如果只想获取切片中某项值，不需要值的索引，尽可能的使用for range去遍历切片，这比必须查询切片中的每个元素要快一些
* 当数组元素是稀疏的（例如有很多0值或者空值nil），使用映射会降低内存消耗
* 初始化映射时指定其容量
* 当定义一个方法时，使用指针类型作为方法的接受者
* 在代码中使用常量或者标志提取常量的值
* 尽可能在需要分配大量内存时使用缓存
* 使用缓存模板

## 常见的陷阱与错误

* 永远不要使用形如 `var p*a` 声明变量，这会混淆指针声明和乘法运算
* 永远不要在`for`循环自身中改变计数器变量
* 永远不要在`for-range`循环中使用一个值去改变自身的值
* 永远不要将`goto`和前置标签一起使用
* 永远不要忘记在函数名后加括号 ()，尤其调用一个对象的方法或者使用匿名函数启动一个协程时
* 永远不要使用`new()`一个 map，一直使用 make
* 当为一个类型定义一个 String() 方法时，不要使用`fmt.Print`或者类似的代码
* 永远不要忘记当终止缓存写入时，使用`Flush`函数
* 永远不要忽略错误提示，忽略错误会导致程序奔溃
* 不要使用全局变量或者共享内存，这会使并发执行的代码变得不安全
* `println`函数仅仅是用于调试的目的
