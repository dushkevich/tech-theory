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

```python
words = [word.lower().strip('.,;:-?!') 
for word in input().split()] print(len(set(words)))
```

`numbers = [int(i) for i in input().split()]`

```python
x = [input() for _ in range(int(input()))] 
y = [i for i in x if i.split(': ')[1] == 'Correct'] 
print(f'Верно решили {len(set(y))} учащихся\nИз всех попыток {round((len(y)/len(x))*100 + 0.001)}% верных' if set(y) else 'Вы можете стать первым, кто решит эту задачу')
```

`result = [user['name'] for user in users if user['phone'].endswith('8')]`

`result = [user['name'] for user in users if 'email' not in user or user['email'] == '']`

```python
digits = { 0: "zero", 1: "one", 2: "two", 3: "three", 4: "four", 5: "five", 6: "six", 7: "seven", 8: "eight", 9: "nine" } 
print(*[digits[int(c)] for c in input()])
```

```python
dic = {
    "1": ".,?!:",
    "2": "ABC",
    "3": "DEF",
    "4": "GHI",
    "5": "JKL",
    "6": "MNO",
    "7": "PQRS",
    "8": "TUV",
    "9": "WXYZ",
    "0": " "
}
string = input().upper()
for ch in string:
    for i in dic:
        if ch in dic[i]:
            print(i*(dic[i].index(ch)+1), end='')
```

```python
letters = [c for c in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789']
morse = ['.-', '-...', '-.-.', '-..', '.', '..-.', '--.', '....', '..', '.---', '-.-', '.-..', '--', '-.', '---', '.--.', '--.-', '.-.', '...', '-', '..-', '...-', '.--', '-..-', '-.--', '--..', '-----', '.----', '..---', '...--', '....-', '.....', '-....', '--...', '---..', '----.']


mo = dict(zip(letters, morse))

print(*[mo[i] for i in input().upper() if i in letters])
```

`result = {i: i ** 2 for i in range(1, 16)}`

```python
dict1 = {'a': 100, 'z': 333, 'b': 200, 'c': 300, 'd': 45, 'e': 98, 't': 76, 'q': 34, 'f': 90, 'm': 230} 
dict2 = {'a': 300, 'b': 200, 'd': 400, 't': 777, 'c': 12, 'p': 123, 'w': 111, 'z': 666} 
result = dict1.copy() for k, v in dict2.items(): result[k] = result.get(k, 0) + v

for i in dict2:
  if i in dict1:
    dict2[i] += dict1[i]
dict1.update(dict2)
result = dict1.copy()
```

```python
text = 'footballcyberpunkextraterritorialityconversationalistblockophthalmoscopicinterdependencemamauserfff'
set_di = set(text)
result = {i: text.count(i) for i in set_di}
```

```python
pets = [('Hatiko', 'Parker', 'Wilson', 50), ('Rusty', 'Josh', 'King', 25), ('Fido', 'John', 'Smith', 28), ('Butch', 'Jake', 'Smirnoff', 18), ('Odi', 'Emma', 'Wright', 18), ('Balto', 'Josh', 'King', 25), ('Barry', 'Josh', 'King', 25), ('Snape', 'Hannah', 'Taylor', 40), ('Horry', 'Martha', 'Robinson', 73), ('Giro', 'Alex', 'Martinez', 65), ('Zooma', 'Simon', 'Nevel', 32), ('Lassie', 'Josh', 'King', 25), ('Chase', 'Martha', 'Robinson', 73), ('Ace', 'Martha', 'Williams', 38), ('Rocky', 'Simon', 'Nevel', 32)] 
result = {} 
for pet in pets: result.setdefault(pet[1:], []).append(pet[0])
```

```python
mydict = {} 
for _ in range(int(input())): 
	key, value = input().split(': ') 
	mydict[key.lower()] = value 
for _ in range(int(input())): 
	print(mydict.get(input().lower(), 'Не найдено'))
```

```python
s1 = [i for i in input().lower() if i.isalpha()] 
s2 = [i for i in input().lower() if i.isalpha()] 
print('YES' if sorted(s1) == sorted(s2) else 'NO')
```

```python
words = {}
for _ in range(int(input())):
    a, b = input().split()
    words[a], words[b] = b, a
print(words[input()])
```

```python
d = {}
for _ in range(int(input())):
    country, *cities = input().split()
    d.update(dict.fromkeys(cities, country))
for _ in range(int(input())):    
    print(d[input()])
```

```python
dct = {}
for _ in range(int(input())):
    phone, name = input().lower().split()
    dct.setdefault(name, []).append(phone)
for _ in range(int(input())):
    print(*dct.get(input().lower(), ['абонент не найден']))

d = {}
for _ in range(int(input())):
    nu, na = input().split()
    d[na.lower()] = d.get(na.lower(), '') + f'{nu} '
for _ in range(int(input())):    
    print(d.get(input().lower(), "абонент не найден"))
```

```python
code, dec, j, fin = input(), {}, {}, {}
f = sorted(set(code))
for i in range(int(input())):
    a, b = input().split(': ')
    dec[int(b)] = a
    j[code.count(f[i])] = f[i]
for i in j:
    fin[j[i]] = dec[i]
for i in code:
    print(fin[i], end='')

dct, word = {}, {}
s = input()
for c in s:
    word[c] = word.get(c, 0) + 1
for _ in range(int(input())):
    a, b = input().split(': ')
    dct[int(b)] = a
for c in s:
    print(dct[word[c]], end='')
```

```python
from random import randint as R
for _ in range(int(input())):
    print([chr(R(65, 90)), chr(R(97, 122))][R(0, 1)], end = '')
```

```python
import random
se = set()
while len(se) != 7:
    se.add(random.randint(1, 49))
print(*sorted(se))
```

method Monte Carlo
```python
import random
n = 10**6       # количество испытаний
k = 0
s0 = 16
for _ in range(n):
    x = random.uniform(-2, 2)
    y = random.uniform(-2, 2)
    if x**3+y**4+2 >= 0 and 3*x+y**2 <= 2:
        k += 1
print((k/n)*s0)
```

```python
import random
n = 10**6       # количество испытаний
k = 0
So = 4
for _ in range(n):
    x = random.uniform(-1, 1)     # случайное число с плавающей точкой от 0 до 1
    y = random.uniform(-1, 1)     # случайное число с плавающей точкой от 0 до 1
    if x**2 + y**2 <= 1:                # если попадает в нужную область
        k += 1
print((k/n)*4)
```

```python
def matrix(a=1, b=None, c=0):
    if b == None: b = a
    return [[c]*b]*a

def matrix(n=1, m=None, value=0):
    if m is None:
        m = n
    return [[value] * m for _ in range(n)]
```

```python
def sq_sum(*args):
    return sum(x ** 2 for x in args)
```

```python
def mean(*args):
    s = [float(i) for i in args if type(i) in (int, float)]
    return sum(s)/len(s) if len(s) > 0 else 0.0
```

```python
def greet(name, *args):
    return f'Hello, {" and ".join((name,) + args)}!'
```

```python
def print_products(*args):
    cnt = 0
    for e in args:
        if type(e) == str and e:
            cnt += 1
            print(f'{cnt}) {e}')
    if cnt == 0:
        print('Нет продуктов')
```

```python
def info_kwargs(**kwargs):
    for k, v in sorted(kwargs.items()):
        print(f'{k}: {v}')

def info_kwargs(**kwars):
    print(*[f"{i}: {kwars[i]}" for i in sorted(kwars)], sep='\n')
```

```python
numbers = [(10, 10, 10), (30, 45, 56), (81, 39), (1, 2, 3), (12,), (-2, -4, 100), (1, 2, 99), (89, 9, 34), (10, 20, 30, -2), (50, 40, 50), (34, 78, 65), (-5, 90, -1, -5), (1, 2, 3, 4, 5, 6), (-9, 8, 4), (90, 1, -45, -21)]
def comb(st):
    return sum(st)/len(st)
print(min(numbers, key=comb))
print(max(numbers, key=comb))
```

```python
points = [(-1, 1), (5, 6), (12, 0), (4, 3), (0, 1), (-3, 2), (0, 0), (-1, 3), (2, 0), (3, 0), (-9, 1), (3, 6), (8, 8)]
def dist(po):
    return (po[0]**2+po[1]**2)**0.5
print(sorted(points, key=dist))
```

```python
athletes = [('Дима', 10, 130, 35), ('Тимур', 11, 135, 39), ('Руслан', 9, 140, 33), ('Рустам', 10, 128, 30), ('Амир', 16, 170, 70), ('Рома', 16, 188, 100), ('Матвей', 17, 168, 68), ('Петя', 15, 190, 90)]
def gen_comparator(field=1):
    def comp(seq):
        return seq[field - 1]
    return comp
cmp = gen_comparator(int(input()))
athletes.sort(key=cmp)
for a in athletes:
    print(*a)
```

```python
import math
def pwr(p):
  def numpower(n):
    return n**p
  return numpower
commands = {"квадрат": pwr(2), "куб": pwr(3), "корень": pwr(0.5), "модуль": abs, "синус": math.sin}
n = int(input())
command = input()
print(commands[command](n))
```

```python
print(*sorted(input().split(), key=lambda x: sum(map(int, x))))

so = input().split()
def sor(a):
    return sum(int(i) for i in a)
print(*sorted(so, key=sor))
```

```python
def comparator(n):
    return sum([int(i) for i in str(n)]), n
numbers = [int(i) for i in input().split()]
print(*sorted(numbers, key=comparator))

so = [int(i) for i in input().split()]
def sor(a):
    return sum(int(i) for i in str(a))
print(*sorted(sorted(so), key=sor))
```

```python
def map(function, items):
    result = []
    for item in items:
        result.append(function(item))
    return result
def filter(function, items):
    result = []
    for item in items:
        if function(item):
            result.append(item)
    return result
numbers = [1014, 1321, 675, 1215, 56, 1386, 1385, 431, 1058, 486, 1434, 696, 1016, 1084, 424, 1189, 475, 95, 1434, 1462, 815, 776, 657, 1225, 912, 537, 1478, 1176, 544, 488, 668, 944, 207, 266, 1309, 1027, 257, 1374, 1289, 1155, 230, 866, 708, 144, 1434, 1163, 345, 394, 560, 338, 232, 182, 1438, 1127, 928, 1309, 98, 530, 1013, 898, 669, 105, 130, 1363, 947, 72, 1278, 166, 904, 349, 831, 1207, 1496, 370, 725, 926, 175, 959, 1282, 336, 1268, 351, 1439, 186, 273, 1008, 231, 138, 142, 433, 456, 1268, 1018, 1274, 387, 120, 340, 963, 832, 1127]
def sel(num):
    return len(str(num)) == 3 and num%5 == 2
print(*map(lambda x: x**3, filter(sel, numbers)), sep='\n')
```

```python
def reduce(operation, items, initial_value):
    acc = initial_value
    for item in items:
        acc = operation(acc, item)
    return acc
numbers = [97, 42, 9, 32, 3, 45, 31, 77, -1, 11, -2, 75, 5, 51, 34, 28, 46, 1, -8, 84, 16, 51, 90, 56, 65, 90, 23, 35, 11, -10, 70, 90, 90, 12, 96, 58, -8, -4, 91, 76, 94, 60, 72, 43, 4, -6, -5, 51, 58, 60, 30, 38, 67, 62, 36, 72, 34, 82, 62, -1, 60, 82, 87, 81, -7, 57, 26, 36, 17, 43, 80, 40, 75, 94, 91, 64, 38, 72, 29, 84, 38, 35, 7, 54, 31, 95, 78, 27, 82, 1, 64, 94, 31, 29, -8, 98, 24, 61, 7, 73]
def smt(i, r=0):
    return i + r**2
print(reduce(smt, numbers, 0))
```

```python
numbers = [77, 293, 28, 242, 213, 285, 71, 286, 144, 276, 61, 298, 280, 214, 156, 227, 228, 51, -4, 202, 58, 99, 270, 219, 94, 253, 53, 235, 9, 158, 49, 183, 166, 205, 183, 266, 180, 6, 279, 200, 208, 231, 178, 201, 260, -35, 152, 115, 79, 284, 181, 92, 286, 98, 271, 259, 258, 196, -8, 43, 2, 128, 143, 43, 297, 229, 60, 254, -9, 5, 187, 220, -8, 111, 285, 5, 263, 187, 192, -9, 268, -9, 23, 71, 135, 7, -161, 65, 135, 29, 148, 242, 33, 35, 211, 5, 161, 46, 159, 23, 169, 23, 172, 184, -7, 228, 129, 274, 73, 197, 272, 54, 278, 26, 280, 13, 171, 2, 79, -2, 183, 10, 236, 276, 4, 29, -10, 41, 269, 94, 279, 129, 39, 92, -63, 263, 219, 57, 18, 236, 291, 234, 10, 250, 0, 64, 172, 216, 30, 15, 229, 205, 123, -105]
print(sum(map(lambda x: x**2, filter(lambda i: 9 < abs(i) < 100 and i%7==0, numbers))))
```

```python
def func_apply(func, arr):
    return [func(x) for x in arr]
```

----
Неполный список функций из модуля operator выглядит так:
```
Операция	Синтаксис	Функция
Addition	a + b	add(a, b)
Containment Test	obj in seq	contains(seq, obj)
Division	a / b	truediv(a, b)
Division	a // b	floordiv(a, b)
Exponentiation	a ** b	pow(a, b)
Modulo	a % b	mod(a, b)
Multiplication	a * b	mul(a, b)
Negation (Arithmetic)	-a	neg(a)
Subtraction	a - b	sub(a, b)
Ordering	a < b	lt(a, b)
Ordering	a <= b	le(a, b)
Equality	a == b	eq(a, b)
Difference	a != b	ne(a, b)
Ordering	a >= b	ge(a, b)
Ordering	a > b	gt(a, b)
```

```python
from functools import reduce
data=[['Tokyo', 35676000, 'primary'],
      ['New York', 19354922, 'nan'],
      ['Mexico City', 19028000, 'primary'],
      ['Mumbai', 18978000, 'admin'],
      ['Sao Paulo', 18845000, 'admin'],
      ['Delhi', 15926000, 'admin'],
      ['Shanghai', 14987000, 'admin'],
      ['Kolkata', 14787000, 'admin'],
      ['Los Angeles', 12815475, 'nan'],
      ['Dhaka', 12797394, 'primary'],
      ['Buenos Aires', 12795000, 'primary'],
      ['Karachi', 12130000, 'admin'],
      ['Cairo', 11893000, 'primary'],
      ['Rio de Janeiro', 11748000, 'admin'],
      ['Osaka', 11294000, 'admin'],
      ['Beijing', 11106000, 'primary'],
      ['Manila', 11100000, 'primary'],
      ['Moscow', 10452000, 'primary'],
      ['Istanbul', 10061000, 'admin'],
      ['Paris', 9904000, 'primary']]
cities = filter(lambda city: city[1] > 10 ** 7 and city[2] == 'primary', data)
cities = map(lambda city: city[0], cities)
cities = sorted(cities)
cities = 'Cities: ' + reduce(lambda city1, city2: f'{city1}, {city2}', cities)
print(cities)

dt = sorted(map(lambda x: x[0], filter(lambda x: x[1] >= 10000000 and x[2] == 'primary', data)))
print("Cities:", ', '.join(dt))
```

-----

```python
file = open(input())
print(file.read())
file.close()

print(*open(input()))
```

`print(open(input()).readlines()[-2])`

```python
import random
file = open('lines.txt')
print(random.choice(file.readlines()).rstrip())
file.close()
```

```python
file = open('numbers.txt')
print(sum(map(int, file)))
file.close()

file = open('nums.txt')
print(sum(map(int, file.read().split())))
file.close()
```

```python
file = open('prices.txt')
lines = map(str.split, file)
print(sum(map(lambda line: int(line[1]) * int(line[2]), lines)))
file.close()

si = file.readlines()
print(sum(map(lambda a: int(a.split('\t')[1]) * int(a.split('\t')[2]), si)))
```
