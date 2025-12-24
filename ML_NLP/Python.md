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
n = int(input()) 
print([i for i in range(1, n + 1) if n % i == 0])
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

`print(*sorted([input() for _ in range(int(input()))]), sep='\n')`

---
Пусть `word = 'Hello', numbers = [1, 14, 5, 9, 12], words = ['one', 'two', 'three', 'four', 'five', 'six']`.

|Списочное выражение|Результирующий список|
|---|---|
|`[0 for i in range(10)]`|`[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]`|
|`[i ** 2 for i in range(1, 8)]`|`[1, 4, 9, 16, 25, 36, 49]`|
|`[i * 10 for i in numbers]`|`[10, 140, 50, 90, 120]`|
|`[c * 2 for c in word]`|`['HH', 'ee', 'll', 'll', 'oo']`|
|`[m[0] for m in words]`|`['o', 't', 't', 'f', 'f', 's']`|
|`[i for i in numbers if i < 10]`|`[1, 5, 9]`|
|`[m[0] for m in words if len(m) == 3]`|`['o', 't', 's']`|

```python
animals = ['🐢', '🐈', '🦜', '🐟', '🐍'] 
favorite_animals = [animal for animal in animals[1::2]]
```

`palindromes = [(num * 10) + (num // 10) for num in range(10, 100) ]`

---
```python
a = [78, -32, 5, 39, 58, -5, -63, 57, 72, 9, 53, -1, 63, -97, -21, -94, -47, 57, -8, 60, -23, -72, -22, -79, 90, 96, -41, -71, -48, 84, 89, -96, 41, -16, 94, -60, -64, -39, 60, -14, -62, -19, -3, 32, 98, 14, 43, 3, -56, 71, -71, -67, 80, 27, 92, 92, -64, 0, -77, 2, -26, 41, 3, -31, 48, 39, 20, -30, 35, 32, -58, 2, 63, 64, 66, 62, 82, -62, 9, -52, 35, -61, 87, 78, 93, -42, 87, -72, -10, -36, 61, -16, 59, 59, 22, -24, -67, 76, -94, 59] 
n = len(a) 
for i in range(n): 
    mx = max(a[:n - i]) 
    mx_ind = a.index(mx) 
    a[n - 1 - i], a[mx_ind] = a[mx_ind], a[n - 1 - i]
    print(a)

print([a.pop(a.index(min(a))) for i in range(len(a))])
```

`print((surname[0]+name[0]+patronymic[0]).upper())`

```python
print('Букв в верхнем регистре:', sum(1 for letter in s if letter.isupper())) print('Букв в нижнем регистре:', sum(1 for letter in s if letter.islower()))
```

```python
a, b = msc_time.split(':') 
print(f'Созвон будет в {int(a) + 2:02d}:{b}.')
```

```python
return [numbers[i] for i in range(len(numbers)) if numbers[i] not in numbers[:i]]

return sorted(set(numbers), key=numbers.index)
```

`return ([i for i in range(len(data)) if data[i] == value] or ["ERROR!"])[-1]`

```python
    string = ''.join(i.lower() for i in text if i.isalpha())
    return string == string[::-1]
```

`return len([i for i in word1 if i not in word2]) == 1 and len(word1) == len(word2)`

```python
def convert_to_python_case(text): 
    s = '' 
    for el in text: 
        if el.isupper(): 
            s += '_' 
        s += el.lower() return s[1:]
        
return ''.join(['_' + i if i.isupper() else i for i in text]).lstrip('_').lower()
```

```python
def is_password_good(password):
    upp = [i for i in password if i.isupper()]
    low = [i for i in password if i.islower()]
    dig = [i for i in password if i.isdigit()]
    return all([len(password) >= 8, upp, low, dig])
```

```python
def is_valid_password(password):
    password = password.split(':')
    a, b, c = password[0], int(password[1]), int(password[2])
    if len(password) != 3 or a != a[::-1] or c % 2 != 0:
        return False
    for i in range(2, b):
        if b % i == 0:
            return False
    return True

def is_valid_password(password):
    if password.count(':') > 2:
        return False
    a, b, c = password.split(":")
    return a == a[::-1] and (all(False for i in range(2, int(int(b) ** 0.5) + 1) if int(b) % i == 0) and int(b) != 1) and int(c)%2 == 0
```

```python
while "()" in text: 
	text = text.replace("()", "") 
return text == ""
```

```python
def solve(a, b, c): 
	d = b**2 - 4 * (a * c) 
	return sorted([(-b + d ** 0.5) / (2 * a), (-b - d ** 0.5) / (2 * a)])
```

---

```python
list1 = [[1, 7, 8], [9, 7, 102], [6, 106, 105], [100, 99, 98, 103], [1, 2, 3]]
maximum = max(max(i) for i in list1)
```

```python
list1 = [[1, 7, 8], [9, 7, 102], [102, 106, 105], [100, 99, 98, 103], [1, 2, 3]] [x.reverse() for x in list1]
```

```python
list1 = [[1, 7, 8], [9, 7, 102], [102, 106, 105], [100, 99, 98, 103], [1, 2, 3]]
total = sum(sum(i) for i in list1)
counter = sum(len(i) for i in list1)
```

```python
n, m = int(input()), int(input()) # считываем значения n и m 
my_list = [[0] * m for _ in range(n)]
```

```python
n = int(input())
print(*[[i for i in range(1, i+1)] for i in range(1, n+1)], sep = "\n")

[print(list(range(1, x + 2))) for x in range(int(input()))]
```

```python
n = int(input()) 
li = [1] 
for i in range(n): 
    for j in range(len(li) - 1): 
        li[j] = li[j] + li[j + 1] 
        li.insert(0, 1) 
print(li)

def pascal(num):
    num += 1
    some = [[1 for i in range(1, i+1)] for i in range(1, num+1)]
    for row in range(2, len(some)):
        for col in range(len(some[row])-1):
            if col != 0 and col != len(some[row]):
                some[row][col] = some[row-1][col-1] + some[row-1][col]
    return some[num-1]
print(pascal(int(input())))

pasc = [1] 
for x in range(int(input())): 
	print(*pasc) 
	pasc[1:] = list(map(lambda a, b: a + b, pasc, pasc[1:] + [0]))
```

```python
tuples = [(10, 20, 40), (40, 50, 60), (70, 80, 90), (10, 90), (1, 2, 3, 4), (5, 6, 10, 2, 1, 77)]
new_tuples = [i[:-1] + (100, ) for i in tuples ]
print(new_tuples)

poet_data = ('Пушкин', 1799, 'Санкт-Петербург') 
poet_data = poet_data[:-1] + ('Москва',) 
print(poet_data)
```

```python
n = int(input()) 
f1, f2 = 1, 1 
for i in range(n): 
	print(f1) 
	f1, f2 = f2, f1 + f2
	
n = int(input())
f1, f2, f3 = 1, 1, 1
for i in range(n):
    print(f1, end=' ')
    f1, f2, f3 = f2, f3, f1 + f2 + f3
```

`print(('NO', 'YES')[len(set(input() + input())) == 10])`

```python
a, b, c = [set(el) for el in input().split()] 
print("YNEOS"[not(a == b == c)::2])
```