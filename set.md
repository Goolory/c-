## 利用set为vector数组去重

```c++
vector<int>vec;
vec = {1,2,3,4,5,6,6,6};
set<int> st(vec.begin(), vec.end());

vec.assign(st.begin(), st.end()); //将set转vector删除vector中原来的内容
```

#### 判读set中是否含有某个元素

```c++
st.count(1); // true
```

