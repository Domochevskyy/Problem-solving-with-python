## Условие
Даны целые числа 1 ≤ n ≤ 10^18 и 2 ≤ m ≤ 10^5, необходимо найти остаток от деления n-го числа Фибоначчи на m.  
## Входные данные
10 2
## Выходные данные
1
## Решение
```
def fib_mod(n, m):
    f1, f2 = 0, 1
    t_pisano = [f1, f2] 
    for i in range(2, 6 * m):
        f1, f2 = f2, (f1 + f2) % m
        t_pisano.append(f2 % m)
        if t_pisano[-2] == 0 and t_pisano[-1] == 1:
            return t_pisano[n % (len(t_pisano) - 2)]


def main():
    n, m = map(int, input().split())
    print(fib_mod(n, m))


if __name__ == "__main__":
    main()
```
## Примечание
При решении данной задачи использовался период Пизано.