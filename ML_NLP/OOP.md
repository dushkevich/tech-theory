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

```