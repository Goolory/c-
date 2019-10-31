#### 迭代器vector的使用

类似指针，不同的是获取迭代器不是用取地址符，而是用**迭代器成员函数**begin()和end()



#### 迭代器类型

```c++
vector<int>::iterator it; //可读写
string::iterator it2;

vector<int>::const_iterator it3;
strig::const_iterator it4; //只读

(*it2).empty(); //解引用-调用成员函数
```

