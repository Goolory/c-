## C++ 中memset函数的用法

**memset: char型初始化函数**

头文件：*<string.h>或<memory.h>*

函数原型：

```c++
void *memset(void *s, int ch, size_t n);

//memset(结构体/数组名, 用于替换的ASCII码对应字符，前n个字符)
//memset(结构体/数组名，“用于替换的字符”，前n个字符)
```

**函数解释：将s中的前n个字节用ch替换并返回s**

**函数作用：**在一段内存块中填充某一个给定的值，**常用于较大的对结构体和数组的清零操作**

```c++
#include<iostream>
//#include"string.h"
using namespace std;
int main()
{
    char str[10];
    str[9] = 'w';
    memset(str,97,9);
    for(int i=0;i<10;i++){
        cout<<str[i]<<" ";
    }
    return 0;
} 
输出：a a a a a a a a a w
```

```c++
#include<iostream>
//#include"string.h"
using namespace std;
int main()
{
    char str[10];
    str[9] = 'w';
    memset(str,97,sizeof(char)*10);
    for(int i=0;i<10;i++){
        cout<<str[i]<<" ";
    }
    return 0;
} 
输出：a a a a a a a a a a
```

