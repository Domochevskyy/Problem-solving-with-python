## Условие
По данным двум числам 1 ≤ a,b ≤ 2&#183;10<sup>9</sup> найдите их наибольший общий делитель.
## Входные и выходные данные
<div style="display: flex; flex-direction: row;" >
<div>

| Input:|
|---|
|18 35|
|Output:|
| 1 |

</div>
<div>

| Input:|
|---|
| 14159572 63967072 |
|Output:|
| 4 |

</div>
</div>

## Решение №1 
```python
def gcd(a, b):
    if a == 0:
        return b
    if b == 0:
        return a
    if a >= b:
        return gcd(a%b,b)
    return gcd(a,b%a)


def main():
    a, b = map(int, input().split())
    print(gcd(a, b))


if __name__ == "__main__":
    main()
```
## Решение №2
```python
def gcd(a, b)
	while b:
		a, b = b, a % b
	return abs(a)


    def main():
    a, b = map(int, input().split())
    print(gcd(a, b))


if __name__ == "__main__":
    main()
```
