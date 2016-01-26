# Keyword

##### noexcept
`noexcept`表示静态异常规范，指定函数是否有异常抛出。  
用法: `noexcept(true/false)`，默认为`false`。
如果`noexcept`函数有异常抛出，则直接调用`std::terminate`中断程序的执行

##### constexpr
`constexpr`用于修饰函数结果为常量的函数或者编译器可以确定的常量。

##### alignas
用于获取指定表达式的的对齐。？？

##### static_assert
编译器断言。
用法: 

##### auto
自动推导类型。

##### decltype
推断类型。

#### nullptr
空指针常量，类型为`std::nullptr_t`。

#### char16_t 和 char32_t
克服wchar_t在不同平台上无法保证确定宽度的缺点而引入。