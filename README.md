## Тема 4. Функции и модули
Отчет по теме № 3 подготовил(а):
Никитина Вероника Евгеньевна
Пиэ-23-1

| Заданияе | Выполнено |
|-----------|-----------|
| 1         | +         |
| 2         | +         |
| 3         | +         |
| 4         | +         |
| 5         | +         |


## Лабораторные задания
## Задание 1. 
```python
class Car:
    def __init__(self, make, model): #конструктор класса, который принимает 2 параметра
        self.make = make
        self.model = model

my_car = Car("Toyota", "Corolla") #создаем экземпляр класса
```
Результат:
![1](pic/1.png)
## Вывод
Был создан класс Car с атрибутами «производитель» и «модель», а затем его экземпляр

## Задание 2. 
```python
class Car: #объявляем класс
    def __init__(self, make, model): #конструктор класса, который принимает 2 параметра
        self.make = make
        self.model = model

    def drive(self): #добавляем метод класса
        print(f"Driving the {self.make} {self.model}")

my_car = Car("Toyota", "Corolla") #создаем экземпляр класса
my_car.drive() #вызываем метод для созданного объекта 
```
Результат:
![1](pic/2.png)
## Вывод
В класс Car добавили метод drive, который выводит строку в консоль

## Задание 3. 
```python
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model

    def drive(self):
        print(f"Driving the {self.make} {self.model}")

class ElectricCar(Car): # Наследование от Car
    def __init__(self, make, model, battery_capacity):
        super().__init__(make, model) # вызываем конструктор родительского класса
        self.battery_capacity = battery_capacity # добавляем новый атрибут

    def charge(self): #создаем уникальный метод для класса ElectricCar
        print(f"Charging the {self.make} {self.model} with {self.battery_capacity} kWh")

my_electric_car = ElectricCar("Tesla", "Model S", 75)
my_electric_car.drive() # используем унаследованный метод
my_electric_car.charge() # используем собственный метод
```
Результат:
![1](pic/3.png)
## Вывод
Создан класс ElectricCar, унаследованный от Car, с новым атрибутом "ёмкость батареи" и методом charge

## Задание 4. 

```python
class Car:
    def __init__(self, make, model):
        self._make = make # защищенный атрибут
        self.__model = model # приватный атрибут

    def drive(self):
        print(f"Driving the {self._make} {self.__model}") # метод имеет доступ ко всем атрибутам

my_car = Car("Toyota", "Corolla")
print(my_car._make) # вызова защищенного атрибута
my_car.drive() # вызов метода
```
Результат:
![1](pic/4.png)
## Вывод
Реализовали инкапсуляцию, изменив уровень доступа атрибутов с помощью _protected и __private модификаторов

## Задание 5. 
```python
class Shape: # общий класс
    def area(self):
        pass # абстрактный метод

class Rectangle(Shape): # Класс Прямоугольник, наследуется от Shape
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height # реализация метода поиска площади для прямоугольника

class Circle(Shape): # класс Круг, наследуется от Shape
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius * self.radius # реализация метода поиска площади для круга

# создаем объекты
my_rectangle = Rectangle(5, 4)
my_circle = Circle(5)
# вызываем методы для поиска площади
print(my_rectangle.area())
print(my_circle.area())
```
Результат:
![1](pic/5.png)
## Вывод
Реализовали полиморфизм через переопределение методов в двух классах


## Самостоятельные задания
## Задание 1.
```python
class Book:
    def __init__(self, title, author, pages):
        self.title = title
        self.author = author
        self.pages = pages
    
    def show_info(self):
        print(f"Книга: '{self.title}'")
        print(f"Автор: {self.author}")
        print(f"Страниц: {self.pages}")

my_book = Book("Мастер и Маргарита", "Михаил Булгаков", 480)
my_book.show_info()
```
Результат:
![1](pic/sam_1.png)
## вывод
Класс Book создан с атрибутами: название, автор, страницы
Создан объект: "Мастер и Маргарита", 480 страниц
## Задание 2. 
```python
class Book:
    def __init__(self, title, author, pages, genre, year):
        self.title = title
        self.author = author
        self.pages = pages
        self.genre = genre
        self.year = year
        self.is_read = False
        self.current_page = 0
    
    def show_info(self):
        print(f"Книга: '{self.title}'")
        print(f"Автор: {self.author}")
        print(f"Жанр: {self.genre}, Год: {self.year}")
        print(f"Статус: {'Прочитана' if self.is_read else 'Не прочитана'}")
        print(f"Прогресс: {self.current_page}/{self.pages} страниц")
    
    def read_page(self):
        if self.current_page < self.pages:
            self.current_page += 1
            print(f"Прочитана страница {self.current_page}/{self.pages}")
            if self.current_page == self.pages:
                self.is_read = True
                print("Книга полностью прочитана!")
        else:
            print("Книга уже прочитана!")
    
    def set_bookmark(self, page):
        if 0 <= page <= self.pages:
            self.current_page = page
            print(f"Закладка установлена на странице {page}")
        else:
            print("Неверный номер страницы!")

book2 = Book("Преступление и наказание", "Федор Достоевский", 672, "Роман", 1866)
book2.show_info()
book2.read_page()
book2.set_bookmark(50)
book2.show_info()
```
Результат:
![1](pic/sam_2.png)
## вывод
Добавлены атрибуты: жанр, год, статус прочтения, текущая страница
Добавлены методы: чтение страницы, установка закладки
Книга "Преступление и наказание": прочитана 1 страница, закладка на 50
## Задание 3. 
```python
class Ebook(Book):
    def __init__(self, title, author, pages, genre, year, file_format, file_size):
        super().__init__(title, author, pages, genre, year)
        self.file_format = file_format
        self.file_size = file_size
        self.is_downloaded = False
    
    def show_info(self):
        super().show_info()
        print(f"Формат: {self.file_format}, Размер: {self.file_size}MB")
        print(f"Статус загрузки: {'Загружена' if self.is_downloaded else 'Не загружена'}")
    
    def download(self):
        self.is_downloaded = True
        print(f"Электронная книга '{self.title}' загружена!")
    
    def read_page(self):
        if self.is_downloaded:
            super().read_page()
        else:
            print("Сначала загрузите книгу!")

ebook = Ebook("1984", "Джордж Оруэлл", 328, "Антиутопия", 1949, "PDF", 5)
ebook.show_info()
ebook.download()
ebook.read_page()
```
Результат:
![1](pic/sam_3.png)
## вывод
Создан класс Ebook-наследник от Book
Добавлены: формат файла, размер, статус загрузки
Электронная книга "1984" загружена и прочитана 1 страница
## Задание 4. 
```python
class LibraryBook(Book):
    def __init__(self, title, author, pages, genre, year, library_code):
        super().__init__(title, author, pages, genre, year)
        self.__library_code = library_code  # приватный атрибут
        self._is_available = True  # защищенный атрибут
        self.__rental_history = []  # приватный атрибут
    
    # Публичные методы для доступа к приватным данным
    def get_library_code(self):
        return f"Код книги: {self.__library_code}"
    
    def borrow_book(self, reader_name):
        if self._is_available:
            self._is_available = False
            self.__rental_history.append(reader_name)
            print(f"Книга '{self.title}' выдана читателю: {reader_name}")
        else:
            print(f"Книга '{self.title}' уже выдана другому читателю")
    
    def return_book(self):
        self._is_available = True
        self.current_page = 0
        print(f"Книга '{self.title}' возвращена в библиотеку")
    
    def get_rental_history(self):
        return f"История выдачи: {', '.join(self.__rental_history) if self.__rental_history else 'Нет записей'}"
    
    def show_info(self):
        super().show_info()
        print(f"Доступность: {'Доступна' if self._is_available else 'Выдана'}")
        print(self.get_rental_history())

library_book = LibraryBook("Война и мир", "Лев Толстой", 1225, "Роман-эпопея", 1869, "LIB-001")
library_book.show_info()
print(library_book.get_library_code())
library_book.borrow_book("Иван Петров")
library_book.borrow_book("Мария Сидорова")
library_book.return_book()
library_book.borrow_book("Анна Иванова")
library_book.show_info()
```
Результат:
![1](pic/sam_4.png)
## вывод
Создан LibraryBook с приватными атрибутами: код библиотеки, история выдачи
Книга "Война и мир" выдана читателям: Иван Петров, Анна Иванова
Приватные данные защищены, доступ через методы
## Задание 5.
```python
class AudioBook:
    def __init__(self, title, author, duration):
        self.title = title
        self.author = author
        self.duration = duration
        self.current_time = 0
    
    def show_info(self):
        print(f"Аудиокнига: '{self.title}'")
        print(f"Автор: {self.author}")
        print(f"Длительность: {self.duration} минут")
        print(f"Прогресс: {self.current_time}/{self.duration} минут")
    
    def read_page(self):
        if self.current_time < self.duration:
            self.current_time += 10
            print(f"Прослушано {self.current_time}/{self.duration} минут")
            if self.current_time >= self.duration:
                print("Аудиокнига полностью прослушана!")
        else:
            print("Аудиокнига уже прослушана!")

def test_reading_material(material):
    print(f"\n--- Тестирование материала: {material.title} ---")
    material.show_info()
    material.read_page()
    material.read_page()
    print("--- Тестирование завершено ---")

materials = [
    Book("Гарри Поттер", "Дж. К. Роулинг", 500, "Фэнтези", 1997),
    Ebook("451° по Фаренгейту", "Рэй Брэдбери", 256, "Научная фантастика", 1953, "EPUB", 3),
    AudioBook("Маленький принц", "Антуан де Сент-Экзюпери", 120)
]

for material in materials:
    test_reading_material(material)

print("\n" + "=" * 60)
print("ВСЕ ЗАДАНИЯ ВЫПОЛНЕНЫ!")
```
Результат:
![1](pic/sam_5.png)
## вывод
Созданы 3 разных класса: Book, Ebook, AudioBook
Единая функция test_reading_material работает со всеми типами
Каждый класс по-своему реализует методы show_info() и read_page()

## ОБЩИЙ ВЫВОД
Все задания выполнены успешно
