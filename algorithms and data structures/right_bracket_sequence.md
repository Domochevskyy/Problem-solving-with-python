## Условие
Напишите функцию, которая принимает в качестве параметра последовательность скобок и определяет, является ли введённая последовательность правильной.  
Правильная скобочная последовательность (ПСП) называется строка, состоящая только из символов "скобки", где каждой закрывающей скобке найдётся соответствующая открывающая (причём того же типа). К тому же:
1. Пустая последовательность является правильной.
2. Если A – правильная скобочная последовательность, то (A), [A] и {A} – правильные скобочные последовательности.
3. Если A и B – правильные скобочные последовательности, то AB – правильная скобочная последовательность.

Функция возвращает True или False.
## Входные и выходные данные
<div style="display: flex; flex-direction: row;">
<div>

| Input:|
|---|
| { { } { ( { [ [ ] ] } ) } |
|Output:|
| True |

</div>
<div>

| Input:|
|---|
| { [ } ] |
|Output:|
| False |

</div>
</div>

## Решение
<details><summary>Кликай, если хочешь узнать</summary>

```python
def right_bracket_sequence(bracket_sequence):
    stack = []
    balanced = True
    i = 0
    while i < len(bracket_sequence) and balanced:
        char = bracket_sequence[i]
        if char in "{[(":
            stack.append(char)
        else:
            if len(stack) == 0:
                balanced = False
            else:
                if stack[-1] + bracket_sequence[i] in '{}[]()':
                    stack.pop()
        i += 1
    return True if balanced and len(stack) == 0 else False
```
</details>

## Примечание 
В качестве структуры данных использовался стек. Сложность алгоритма O(n).



