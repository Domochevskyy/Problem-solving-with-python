## Условие
По данным двум числам 1 ≤ a,b ≤ 2*10^9 найдите их наибольший общий делитель.
## Решение #1 
### через рекурсию
```
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
### через цикл
```
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
