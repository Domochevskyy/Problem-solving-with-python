## Условие
Найти последнюю цифру n-ого числа Фибоначи,  
причем `n` может быть порядка миллиона.
## Входные и выходные данные
|Input:|
|---|
|3|
|Output:|
|2|

## Решение
<details><summary>Кликай, если хочешь узнать</summary>

```python
def fib(n):
    f1, f2 = 0, 1
    for i in range(n):
        f1, f2 = f2, (f1 + f2) % 10
    return f1


def main():
    n = int(input())
    print(fib(n))


if __name__ == "__main__":
    main()
```
</details>

## Примечание
Если а и b - это последние цифры чисел F<sub>i</sub> и F<sub>i+1</sub>, то (a+b)%10 - последняя цифра F<sub>i+2</sub> числа.