## c++内联函数（c++ inline）使用

http://c.biancheng.net/view/199.html

使用函数能够避免将相同代码重写的麻烦，还能**减少可执行程序的体积**，**但是与会带来程序运行上的时间开销。**

函数调用在执行时，**首先**要<u>在栈中为形参和局部变量分配存储空间</u>，然后还要<u>将实参的值赋值给形参</u>，接下来还要将<u>函数的返回地址</u>（该地址指明了函数执行结束后，程序应该回到哪里继续执行）放入栈中，<u>最后才跳到函数内部执行</u>。这个过程是要耗费时间的。

另外，**函数执行return语句返回时**，需要从栈中回收形参和局部变量占用的存储空间，然后从栈中取出返回地址，在跳转到该地址继续执行，这个过程也要耗费时间。

一般情况下，这个开销可以忽略不计。但是，如果一个函数内部没有几条语句，执行时间本来就非常短，那么这个函数调用产生的额外开销和函数本身执行的时间相比，就显得不能忽略了。假如这样的函数在一个循环中被成千上万次地执行，函数调用导致的时间开销就可能使得程序运行明显变慢。

-------------------------------------------------

**c++用inline关键字较好地解决函数调用的开销问题**

```c++
inline int Max(int a, int b)
{
	if(a>b)
		return a;
	return b;
}
```

增加了inline关键字的函数称为“内联函数”。内联函数与普通函数的区别在于：**当编译器处理调用内联函数的语句时，不会将该语句编译成函数调用的指令，而是直接将整个函数体的代码插入调用语句处，就像整个函数体在调用处被重写了一遍一样。**

有了内联函数，就像调用一个函数那样方便地重复使用一段代码，而不需要付出执行函数调用的额外开销。很显然，使用内联函数会使得最终可执行程序的体积增加。以时间换空间，或增加空间消耗来节省时间。

**如果一个函数复杂，使用内联函数就不适合**