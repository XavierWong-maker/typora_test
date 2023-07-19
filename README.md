## 函数对象

- 使用具体的类对象取代函数
- 该类的对象`具备函数调用行为`
- 多个对象相互独立

函数调用操作符（`（）`）

- 只能通过类的成员函数重载
- 可以定义不同参数的多个重载函数

```c++
class Fib
{
    int a0;
    int a1;
public:
    Fib()
    {
        a0 = 0;
        a1 = 1;
    }

    Fib(int n)
    {
        a0 = 0;
        a1 = 1;

        for(int i = 2; i <= n; i++)
        {
            int t = a1;
            a1 = a0 + a1;
            a0 = t;
        }
    }

    int operator ()()
    {
        int ret = a1;
        a1 = a0 + a1;
        a0 = ret;

        return ret;
    }
};

int main ()
{
    Fib fib;

    for(int i = 0; i < 10; i++)
    {
        cout << fib() << endl;
    }

    cout << endl;

    for(int i = 0; i < 5; i++)
    {
        cout << fib() << endl;
    }

    cout << endl;

    Fib fib2(10);

    for(int i = 0; i < 5; i++)
    {
        cout << fib2() << endl;
    }
}
```

## 赋值操作符疑问
