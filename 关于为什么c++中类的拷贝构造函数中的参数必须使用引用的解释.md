# 关于为什么c++中类的拷贝构造函数中的参数必须使用引用的解释

代码:

```c++
#include<iostream.h>
using namespace std;

//引用传递
class my_class
{
    my_class(const my_class &p){}
}

//值传递:
class my_class
{
    my_class(const my_class p){}
}

int main()
{
    my_class p;  
    my_class p1=p;//第二步
    return 0;
}
```

解释:

​		在第二步想要实现p赋值给p1,那么就需要调用拷贝构造函数,此时函数体需要构造一个临时变量(假设为w)来接收p的值,此时式子就变成w=p,变成p需要给w进行赋值,此时就需要调用拷贝构造函数,然后不断的一直进行下去,直到栈溢出,系统报错