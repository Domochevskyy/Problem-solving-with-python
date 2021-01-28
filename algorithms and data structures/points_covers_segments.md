## Условие
Даны отрезки на прямой. Найти такие точки, которые лежат на всех заданных отрезках. Найденное множество должно быть минимальным по размеру.
В первой строке дано число 1 ≤ n ≤ 100 отрезков. Каждая из последующих `n` строк содержит по два числа 0 ≤ 1 ≤ r ≤ 10<sup>9</sup>, задающих начало и конец отрезка. Выведите оптимальное число `m` точек и сами `m` точек. Если таких множеств точек несколько, выведите любое из них.
## Входные и выходные данные

|Input:|
| --- |
 | 3 | 
 | 1 3 |
 | 2 5 |
 | 3 6 |
 | Output:|
 | 1 |
 | 3 |
   
## Решение
```python
n = int(input())

line_segments = [list(map(int, input().split())) for j in range(n)]

line_segments.sort(key=lambda segment: segment[1])
points = []

i = 0
while i < n:
    optional_step = line_segments[i][-1]
    points.append(optional_step)
    i += 1
    while i < n and points[-1] >= line_segments[i][0]:
        i += 1

print(len(points))
print(*points)
```
## Примечание
Сложность алгоритма O(n&#183;log(n))