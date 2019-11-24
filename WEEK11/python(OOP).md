# Object-Oritented Programming
文字上面的差別

| Imperative | OOP  |
| ---------- | ---- |
|  Variavble   |   Attribute/Fields   |
| Fucntion  | method |


OOP重要且常見的規則

|     英文      | 中文 | 意思                                                                            |
|:-------------:|:----:|:------------------------------------------------------------------------------- |
|  Inheritance  | 繼承 | A process of using details from a new class without modifying existing class.   |
| Encapsulation | 封裝 | Hiding the private details of a class from other objects.                       |
| Polymorphism  | Text | A concept of using common operation in different ways for different data input. |


## Inheritance (繼承)
>將新的class沿用舊的class使用的一些東西或是進行更動。新的class通常叫做 derived class (or child class). 而被使用的class叫做base class (or parent class).

```python
class node:
    def __init__(self):
        print('this is node')
    def makenode(self):
        print('i can make node')
class tree(node):
    def __init__(self):
        # call super() function
        super().__init__()
        print('this is tree')
new = tree()
# this is node
# this is tree
# i can make node

```
>並且要注意！把super() function 放在__init__() method的前面，因為要把parent的class 放入child的class

## Inheritance(封裝)

>封裝可以限制某些變數，來當作私有變數，讓人無法更動到。當你不想要隨意被更動時可以用
>denote private attribute using underscore as prefix(前綴詞) i.e double “ __“.

```python
class node():
    def __init__(self):
        self.__val = 10
    def print(self):
        print('now value:{}'.format(self.__val))
    def changeval(self,change_num):
        self.__val = change_num

new = node()
new.print()

new.__val = 20
new.print()

new.changeval(30)
new.print()


#now value:10
#now value:10 ->沒有被更動
#now value:30

```

## Polymorphism
>Suppose, we need to color a shape, there are multiple shape option (rectangle, square, circle). However we could use same method to color any shape. This concept is called Polymorphism.
>
>這邊舉例是說，我想要測試這個鳥到底會不會飛，我就可以使用`fun flytin_test`來做測試
```python
class Parrot:

    def fly(self):
        print("Parrot can fly")
    
    def swim(self):
        print("Parrot can't swim")

class Penguin:

    def fly(self):
        print("Penguin can't fly")
    
    def swim(self):
        print("Penguin can swim")

# common interface
def flying_test(bird):
    bird.fly()
    
def swimming_test(bird):
    bird.swim()

#instantiate objects
blu = Parrot()
peggy = Penguin()

# passing the object
flying_test(blu)
flying_test(peggy)


#Parrot can fly
#Penguin can't fly
#Parrot can't swim
#Penguin can swim

```
## Ref.
[Python Object Oriented Programming](https://www.programiz.com/python-programming/object-oriented-programming)
[Imperativ programming是什麼](https://ithelp.ithome.com.tw/articles/10191612)