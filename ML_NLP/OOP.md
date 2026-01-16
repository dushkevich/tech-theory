```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y
        
###
        
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def move(self, a, b):
        self.x += a
        self.y += b

    def length(self, point):
        return round(((self.x - point.x) ** 2 + (self.y - point.y) ** 2) ** 0.5, 2)

###

class RedButton:
    def __init__(self):
        self.c = 0

    def click(self):
        print("Тревога!")
        self.c += 1

    def count(self):
        return self.c

###

class Programmer:
    def __init__(self, full_name, job_title):
        self.name = full_name
        self.title = (0 if job_title == 'Junior' else (1 if job_title == 'Middle' else 2))
        self.pay = (10 if self.title == 0 else (15 if self.title == 1 else 20))
        self.time = 0
        self.payed = 0

    def work(self, time):
        self.time += time
        self.payed += self.pay * time

    def rise(self):
        self.title += 1
        if self.title > 2:
            self.pay += 1
        elif self.title <= 2:
            self.pay += 5

    def info(self):
        return f"{self.name} {self.time}ч. {self.payed}тгр."
        
###

class Rectangle:
    def __init__(self, first, second):
        (x1, y1), (x2, y2) = first, second
        x1, x2 = sorted((x1, x2))
        y1, y2 = sorted((y1, y2))
        self.x, self.y = x1, y1
        self.width, self.height = x2 - x1, y2 - y1

    def perimeter(self):
        return round((self.width + self.height) * 2, 2)

    def area(self):
        return round(self.width * self.height, 2)
```


```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def move(self, a, b):
        self.x += a
        self.y += b

    def length(self, point):
        return round(((self.x - point.x) ** 2 + (self.y - point.y) ** 2) ** 0.5, 2)


class PatchedPoint(Point):
    def __init__(self, *args):
        if len(args) == 0:
            super().__init__(x=0, y=0)
        elif len(args) == 1:
            super().__init__(x=args[0][0], y=args[0][1])
        else:
            super().__init__(x=args[0], y=args[1])

####


```