## Условие
Вычислить n-ое число Фибоначчи. F(0) = 0, F(1) = 1
## Решение №1
очень плохое
```
def fib(n):
    if n == 0:
        return 0
    elif n == 1:
        return 1
    return fib(n - 1) + fib(n - 2)


def main():
    n = int(input())
    print(fib1(n))


if __name__ == "__main__":
    main()
``` 
## Решение №2
уже получше
```
def fib(n):
    f1, f2 = 0, 1
    for i in range(n):
        f1, f2 = f2, f1 + f2
    return f1


def main():
    n = int(input())
    print(fib(n))


if __name__ == "__main__":
    main()
```

## Пояснение
Можно показать, что временная сложность первого алгоритма равна O(2^n), а второго O(n)
