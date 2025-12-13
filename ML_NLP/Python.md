num % 10 ** (n + 1 - i) // (10 ** (n - i))

| Функция                                   | Описание                                                                         |
| ----------------------------------------- | -------------------------------------------------------------------------------- |
| **Округления**                            |                                                                                  |
| `floor(x)`                                | Округляет число `x` вниз («пол»)                                                 |
| `ceil(x)`                                 | Округляет число `x` вверх («потолок»)                                            |
| **Корни, логарифмы, степени и факториал** |                                                                                  |
| `sqrt(x)`                                 | Квадратный корень числа `x`                                                      |
| `pow(x, n)`                               | Возведение числа `x` в степень `n`                                               |
| `log(x)`                                  | Натуральный логарифм числа `x`. Основание натурального логарифма равно числу `e` |
| `log10(x)`                                | Десятичный логарифм числа `x`. Основание десятичного логарифма равно числу 10    |
| `log(x, b)`                               | Логарифм числа `x` по основанию `b`                                              |
| `factorial(n)`                            | Факториал натурального числа `n`                                                 |
| **Тригонометрия**                         |                                                                                  |
| `degrees(x)`                              | Преобразует угол `x`, заданный в радианах, в градусы                             |
| `radians(x)`                              | Преобразует угол `x`, заданный в градусах, в радианы                             |
| `cos(x)`                                  | Косинус угла `x`, задаваемого в радианах                                         |
| `sin(x)`                                  | Синус угла `x`, задаваемого в радианах                                           |
| `tan(x)`                                  | Тангенс угла `x`, задаваемого в радианах                                         |
| `acos(x)`                                 | Возвращает угол в радианах от 00 до ππ, `cos` которого равен `x`                 |
| `asin(x)`                                 | Возвращает угол в радианах от −π2−2π​ до π22π​, `sin` которого равен `x`         |
| `atan(x)`                                 | Возвращает угол в радианах от −π2−2π​ до π22π​, `tan` которого равен `x`         |
| `atan2(y, x)`                             | Полярный угол (в радианах) точки с координатами `(x, y)`                         |

`for i,j,k in zip('ABETG',[3,4,1,5,1],[6,5,1,9,1]): print(((i*j)+'\n')*k, end='')`

`print(sum([1 for i in range(int(input()), int(input())+1) if i**3%10 in [4,9]]))`

`from math import log; print(*[sum([1/j for j in range(1, i+1)]) -  log(i) for i in [int(input())]])`

`print(sum(int(input()) for _ in range(int(input()))))`

`print(5 * ((int(input())+5) // 10)**2)`

```python
res = 1 
for _ in range(10): 
    res *= int(input()) or 1 
print(res)
```

if in one line, it goes from right to left

`[print(next(i for i in range(2, t + 1) if t % i == 0)) for t in [int(input())]]`

`print(*[i for i in range(1,int(input())+1) if not(5<=i<=9 or 17<=i<=37 or 78<=i<=87)], sep='\n')`

`(lambda x: [[print(f'{j} + {i} = {j+i}') for i in range(1,10)] and print() for j in range(1, x+1)])(int(input()))`

```python
s = input()
any(substring in string for substring in substring_list)

if any(i in s for i in ['1','2','3','4','5','6','7','8','9']):
    print('Цифра')
else:
    print('Цифр нет')
```

`print('Цифра' if set('1234567890') & set(input()) else 'Цифр нет')`

```python
n = input()
for i in ['+','*']:
    print(f'Символ {i} встречается {n.count(i)} раз')
```


`(lambda s: print(len(list(s[i] for i in range(1,len(s)) if s[i] == s[i-1]))))(input())`

```python
s = input().lower()
print('Количество гласных букв равно', sum(1 for _ in s if _ in 'ауоыиэяюёе'))
print('Количество согласных букв равно', sum(1 for _ in s if _ in 'бвгджзйклмнпрстфхцчшщ'))
```

`x[::-1] = "dlrow olleh"`

`print(str(bin(int(input())))[2:])`

```
s = 'abcdefghij'
Программный код	Результат	Пояснение
s[2:5]	cde	строка состоящая из символов с индексами 2, 3, 4
s[:5]	abcde	первые пять символов строки
s[5:]	fghij	строка состоящая из символов с индексами от 5 до конца
s[-2:]	ij	последние два символа строки
s[:]	abcdefghij	вся строка целиком
s[1:7:2]	bdf	строка, состоящая из каждого второго символа с индексами от 1 до 6
s[::-1]	jihgfedcba	строка в обратном порядке, так как шаг отрицательный

s = s[:4] + 'X' + s[5:]

print(s[::7])
```

```python
s = input()
print(['NO','YES'][s == s.title()])

print(['NO','YES']['хорош' in input().lower()])
```

`print(sum(s.islower() for s in input()))` 

`print([chr(i) for i in range(97, 97 + int(input()))])`

`print(list(input()[::2]))`

`print([input() for _ in range(int(input()))])`

```python
n = int(input()) print([i for i in range(1, n + 1) if n % i == 0])
```

```python
a = [int(input()) for i in range(int(input()))] 
print([a[i] + a[i + 1] for i in range(len(a) - 1)])
```

```python
numbers = [int(input()) for _ in range(int(input()))] 
print(*numbers, '',*[(x + 1) ** 2 for x in numbers], sep='\n')
```

```python
ls = [int(input()) for _ in range(int(input()))] 
[print(i) for i in ls if i not in (max(ls), min(ls))]
```

```python
n = [int(input()) for _ in range(int(input()))]
del n[n.index(max(n))]
del n[n.index(min(n))]
print(*n, sep='\n')
```

`print(*{input(): 0 for _ in range(int(input()))}, sep='\n')`

```python
my_list, word = [input() for _ in range(int(input()))], input() 
[print(i) for i in my_list if word.lower() in i.lower()]
```

```python
lst = [input() for _ in range(int(input()))] 
searches = [input() for _ in range(int(input()))] 
for text in lst: 
	if all(search.lower() in text.lower() for search in searches): 
		print(text)

text = [input() for _ in range(int(input()))] 
search = [input() for _ in range(int(input()))] 
for t in text: 
	for s in search: 
		if s.lower() not in t.lower(): 
		break 
	else: 
		print(t)
```

`print(*input().split(), sep='\n')`

`print('.'.join([name[0] for name in input().split()]), end='.')`

`print("ДА" if all(int(i) <= 255 for i in input().split('.')) else "НЕТ")`

```python
a = input().split() 
print(sum(a.count(x) - 1 for x in a) // 2)

a=input().split() 
p=0 
for i in range(len(a)): 
	p+=a[i:].count(a[i])-1 
print(p)
```

```python
numbers = [8, 9, 10, 11] 
numbers[1] = 17 
numbers.extend([4, 5, 6]) 
del numbers[0] 
numbers *= 2 
numbers.insert(3, 25) 
print(numbers)
```

```python
a = list(map(int, input().split())) 
x = a.index(max(a)) 
y = a.index(min(a)) 
a[x], a[y] = a[y], a[x] 
print(*a)

d = [int(i) for i in input().split()] 
x, y = d.index(min(d)), d.index(max(d)) 
d[x], d[y] = d[y], d[x] 
print(*d)
```