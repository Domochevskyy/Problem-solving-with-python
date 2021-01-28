## Непрерывный рюкзак
Первая строка содержит количество предметов 1 ≤ n ≤ 10<sup>3</sup> и вместимость рюкзака 0 ≤ W ≤ 2⋅10<sup>6</sup>. Каждая из следующих `n` строк задаёт стоимость 0 ≤ c<sub>i</sub> ≤ 2⋅10<sup>6</sup> и объём 0 ≤ w<sub>i</sub> ≤ 2⋅10<sup>6</sup> предмета (n, W, c<sub>i</sub>, w<sub>i</sub> — целые числа). Выведите максимальную стоимость частей предметов (от каждого предмета можно отделить любую часть, стоимость и объём при этом пропорционально уменьшатся), помещающихся в данный рюкзак, с точностью не менее трёх знаков после запятой.
## Входные и выходные данные
| Input |
|---|
|3 50|
|60 20|
|100 50|
|120 30|
|Output|
|180.000|
## Решение
```python
def fractional_knapsack(capacity, values_and_weights):
    order = [(v / w, w) for v, w in values_and_weights]
    order.sort(reverse=True)

    knapsack_cost = 0
    for v_per_w, w in order:
        if w < capacity:
            knapsack_cost += v_per_w * w
            capacity -= w
        else:
            knapsack_cost += v_per_w * capacity
            break
    return knapsack_cost


def main():
    n, capacity = map(int, input().split())
    values_and_weight = [tuple(map(int, input().split())) for _ in range(n)]

    assert len(values_and_weight) == n
    optimal_value = fractional_knapsack(capacity, values_and_weight)
    print(f"{optimal_value:.3f}")


if __name__ == "__main__":
    main()
```
## Примечание
Сложность алгоритма O(n&#183;log(n)).
