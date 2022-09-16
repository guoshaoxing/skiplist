# 做项目时遇到的困难
## **forward的两层指针如何使用的
```cpp
//一级指针
int *p1=new int[2];
*p1=1; ++*p1=2;
cout<<*p1<<" "<<--*p1<<endl;
//二级指针
int **p2=new int*[2];
int a1=1, a2=2;
cout<<&a1<<" "<<&a2<<endl;
*p2=&a1; cout<<"&p2[0]:"<<p2<<endl;
*(++p2)=&a2; cout<<"&p2[1]:"<<p2<<endl;
cout<<**p2<<" "<<**(--p2)<<endl;
```
* 通过new Node<K, V>*[level+1]右值动态创建一个数组，数组中存放的是一串地址；
* 左值是一个二级指针；
## memset与fill
```cpp
//按照单元赋值，将一个区间的元素都赋予val值
#include <cstring>
const int INF = 0x3f3f3f3f;
memset(a,INF,sizeof(a));
```
```cpp
//按照字节填充某字符
#include <algorithm>
fill(vec.begin(), vec.end(), val); //原来容器中每个元素被重置为val
```