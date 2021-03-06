默认值只被赋值一次。这使得当默认值是可变对象时会有所不同，比如列表、字典或者大多数类的实例。例如，下面的函数在后续调用过程中会累积（前面）传给它的参数。


默认参数值
最常用的一种形式是为一个或多个参数指定默认值。这会创建一个可以使用比定义时允许的参数更少的参数调用的函数，例如：



在 Python 中，你也可以定义包含若干参数的函数。这里有三种可用的形式，也可以混合使用。

和以前一样，这个例子演示了一些新的 Python 功能：
    return 语句从函数中返回了一个值。
    不带表达式的return返回 None。过程结束后也会返回 Node。
    
    语句 result.append(b)称为链表对象 result 的一个方法(METHOD)
    
    方法是一个“属于”摸个对象的函数，它被命名为 obj.methodename，这里的 obj 是某个对象（可能是一个表达式），methodename 是某个在该对象类型中的方法的命名。不同的类型定义不

同的方法。不同类型可能有同样名字的方法，但不会混淆（当你定义自己的对象类型和方法时，可能会出现这种情况，class 的定义方法详见类）。示例中演示的 append 方法由链表对象定义，它向

链表中加入一个元素。在示例中它等同于 result = result + [b]，不过效率更高。





一个函数定义会在当前符号表内引入函数名。函数名指代的值（即函数体）存在一个被 python 解释器认定为 用户自定义函数 的类型。这个值可以赋予其他的名字（即变量名），然后它也可以被当

做函数使用。这可以作为通用的重命名机制：

函数引用的实际参数在函数调用时引入局部符号表，因此，实参总是传值调用（这里的值总是一个对象引用，而不是该对象的值）

函数 调用 会为函数局部变量生成一个新的符号表。确切地说，所有函数中的变量赋值都是将值存储在局部符号表。变量引用首先在局部符号表中查找，然后是包含函数的局部符号表，然后是全局符

号表，最后是内置名字表。因此，全局变量不能再函数中直接赋值（除非用 global 语句命名），尽管他们可以被引用。

函数体的第一行语句可以是可选的字符串文本，这个字符串是函数的文档字符串，或者称为 docstring。有些工具通过 docstrings 自动生成在线的或可打印的文档，或者让用户通过代码交互浏览；

在你的代码中包含 docstrings 是一个好的实践，让它成为习惯吧。

关键字 def 引入了一个函数 定义。在其后必须跟有函数名和包括形式参数的圆括号。函数体语句从下一行开始，必须是缩进的。

我们可以定义一个函数用来生成任意上界的菲波那契数列

continue 语句是从 C 中借鉴来的，它表示循环继续执行下一次迭代：


与循环一起使用时，else 子句与 try 语句的 else 子句比与if 语句的具有更多的共同点：try 语句的else子句在未出现异常时运行，循环的 else 子句在未出现 break 时运行


循环可以有一个 else 子句；它在循环迭代完整个列表（对于 for）后或执行条件为 false（对于 while）时执行，但循环被 break 终止的情况下不会执行。


range(10) 生成了一个包含10个值得链表，它用链表的索引值填充了这个长度为10的列表，所生成的链表中不包括范围中的结束值。也可以让 range 操作从另一个数值开始，或者可以指定一个不同的

步进值（甚至是负数，有时这也被称为“步长”）：


如果你需要一个数值序列，内置函数 range() 会很方便，它生成一个等差级数链表


在迭代过程中修改迭代序列不安全（只有在使用链表这样的可变序列时才会有这样的情况）。如果你想要修改你迭代的序列（例如：复制选择项），你可以迭代它的副本。使用切割标识就可以很方便

的做到这一点：

Python 中的 for 语句和 C 或 Pascal 中的略有不同。通常的循环可能会依据一个等差数值步进过程（如 Pascal），或由用户来定义迭代步骤和终止条件（如C），Python 的 for 语句依据任意序列

（链表或字符串）中的子项，按它们在序列中的顺序来进行迭代。例如



关键字 print 语句输出给定表达式的值。它控制多个表达式和字符输出为你想要的字符串（就像我们在前面计算器的例子中那样）。字符打印时不用引号包围，每两个子项之间插入空间，所以你可以

把格式弄得很漂亮，像这样：