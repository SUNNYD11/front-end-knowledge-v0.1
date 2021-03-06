# let

- 类似于var，所声明的变量，只在let命令所在的代码块内有效（例如for计数器）。
  - 不存在变量提升，所声明的变量一定要在声明后使用。
  - 暂时性死区，只要块级作用域内存在let，所声明的变量就被绑定在这个区域，不受外界影响。
  - 不允许重复声明。
- 块级作用域：防止内层变量覆盖外层变量。防止用来计数的循环变量泄露为全局变量。
  - 允许块级作用域任意嵌套，外层无法读取内层变量，内层作用域可以定义外层同名变量。

# const

- 声明一个只读的常量，一旦声明，常量的值就不能改变，同样只在声明所在的块级作用域内有效。不存在变量提升，有暂时性死区，不可重复声明。
- 本质是变量指向的内存地址所保持的数据不得改动。对于复合数据类型，对象和数组，保存的只是一个指向实际数据的指针，指向的数据结构是可变的。想把对象冻结，应该使用object.freeze方法。

------

- var和function声明的全局变量依旧是顶层对象的属性，let，const，class声明的全局变量，不属于顶层对象的属性(let a=1;window.a//undefined)。
