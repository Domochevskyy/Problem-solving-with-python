<h2 align=center>Задача о различных слагаемых</h2>

## Условие
По заданному числу 1 &#8804; *`n`* &#8804; 10<sup>9</sup> найдите максимальное число *`k`*, для которого *`n`* можно представить как сумму *`k`*  различных натуральных слагаемых. Выведите в первой строке число *`k`*, во второй — *`k`* слагаемых.
## Входные и выходные данные
| Input |
| ---|
| 15 |
|Output|
|5|
|1 2 3 4 5|
## Решение
```python
def main():
    n = int(input())

    terms = []
    term, current_n = 1, n - 1

    while current_n > term:
        terms.append(term)
        term += 1
        current_n -= term
    terms.append(n - sum(terms))

    print(len(terms))
    print(*terms)


if __name__ == "__main__":
    main()
```