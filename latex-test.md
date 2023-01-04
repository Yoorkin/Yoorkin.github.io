# docsify测试

$$
(abst_2)
\frac{\Gamma, \alpha: * \vdash M : A}
    {\Gamma\vdash \lambda\alpha:*.M : \Pi\alpha:*.A}
$$


这$\lambda x.x$是一个输入x输出x的函数。

```cpp
#include<iostream>

int main(){
    std::cout << "test" << std::endl;
    return 0;
}

```

```vb
    Sub Foo(Byval a As String, ParamArray Byval arr As Object[])
        ...
    End Sub

    Sub Main()
        Foo("第一次输入:",1,2,3,4,5,6)

        Dim arr As Object[]
        arr = [1,2,3,4,5,6]
        Foo("等效的输入:", arr)
    End Sub
```
