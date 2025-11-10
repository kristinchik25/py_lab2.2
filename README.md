## Лабораторная работа № 2.2 Импорт и использование стандартных модулей Python

## Цель:
Получить практические навыки импорта и использования
функций, классов и констант из стандартной библиотеки Python для решения
прикладных задач.


## Задачи:
- Изучить понятие "модуль" в Python и его роль в организации кода.
- Освоить различные способы импорта модулей и их компонентов (import, from ... import, as).
- Познакомиться с функциональностью нескольких ключевых стандартных модулей, таких как math, random и datetime.
- Научиться находить необходимую информацию в официальной документации Python.
- Решить практические задачи, применяя функции из стандартных модулей.

## Выполнение практической работы


## № 2.2.1 Используя модуль math, вычислите площадь круга по заданному радиусу.

````
import math

def circle_area(radius):
    return math.pi * radius ** 2

try:
    radius_input = input()
    radius = float(radius_input)

    # Проверяем, что радиус неотрицательный
    if radius < 0:
        print("Ошибка: Радиус не может быть отрицательным.")
    else:
        area = circle_area(radius)
        print(f"Площадь круга: {area:.2f}")

except ValueError:
    print("Ошибка: Введено нечисловое значение.")
````
<img width="225" height="50" alt="image" src="https://github.com/user-attachments/assets/06e49b08-ac75-4957-8d51-dde1204c168d" />

## № 2.2.2 Используя модуль random, сгенерируйте случайное целое число в заданном диапазоне (включительно).
````
import random

def generate_random_int(min_val, max_val):
    return random.randint(min_val, max_val)

try:
    min_input = input()
    max_input = input()

    min_val = int(min_input)
    max_val = int(max_input)

    if min_val > max_val:
        print("Ошибка: Нижняя граница не может быть больше верхней.")
    else:
        random_number = generate_random_int(min_val, max_val)
        print(f"Случайное число от {min_val} до {max_val}: {random_number}")

except ValueError:
    print("Ошибка: Введены некорректные данные.")
````
<img width="371" height="68" alt="image" src="https://github.com/user-attachments/assets/550dcca2-cf5c-42f1-846e-ccbe001ba56a" />

## № 2.2.3 Используя модуль datetime, выведите текущую дату и время в формате ГГГГ-ММДД ЧЧ:ММ:СС.
````
import datetime

def get_current_datetime():
    current_time = datetime.datetime.now()
    return current_time.strftime("%Y-%m-%d %H:%M:%S")


print(f"Текущая дата и время: {get_current_datetime()}")
````
<img width="417" height="32" alt="image" src="https://github.com/user-attachments/assets/8f454a0f-93d4-4f20-ba01-52c1e0ae8c96" />


## № 2.2.4 Используя модуль math, вычислите длину гипотенузы прямоугольного треугольника по двум заданным катетам. 
````
import math

def hypotenuse(a, b):
    return math.sqrt(a**2 + b**2)

try:
    cathetus1 = float(input("Введите длину первого катета: "))
    cathetus2 = float(input("Введите длину второго катета: "))
    
    if cathetus1 <= 0 or cathetus2 <= 0:
        raise ValueError("Длины катетов должны быть положительными числами.")
    
    result = hypotenuse(cathetus1, cathetus2)
    print(f"Гипотенуза для катетов {cathetus1} и {cathetus2}: {result:.2f}")
    
except ValueError as e:
  print("Длины катетов должны быть положительными числами.")
````
<img width="407" height="66" alt="image" src="https://github.com/user-attachments/assets/f682dbea-3b43-456b-a541-a45ce7e5639e" />


## № 2.2.5 Используя модуль random, сгенерируйте случайное число с плавающей точкой в диапазоне [0.0, 1.0).
````
import random

def generate_random_float():
    return random.random()


print(f"Случайное число от 0.0 до 1.0: {generate_random_float():.4f}")
````
<img width="382" height="30" alt="image" src="https://github.com/user-attachments/assets/346fe30d-5964-4979-9c91-0ca9731a2c6f" />


## № 2.2.6 Используя модуль math, найдите синус угла, заданного в радианах.
````
import math

def sin_of_angle(angle_rad):
    return math.sin(angle_rad)

try:
    degrees_input = input()
    degrees = float(degrees_input)

    radians = math.radians(degrees)
    sine_value = sin_of_angle(radians)

    print(f"Синус угла {degrees} градусов: {sine_value:.2f}")

except ValueError:
    print("Ошибка: Введено нечисловое значение.")
````
<img width="322" height="52" alt="image" src="https://github.com/user-attachments/assets/270746ef-ddba-4880-a003-c51135a861ab" />

## № 2.2.7 Используя модуль random, перемешайте элементы списка

````
import random

def shuffle_list(input_list):
    random.shuffle(input_list)


my_list = [1, 2, 3, 4, 5]
print(f"Исходный список: {my_list}")
shuffle_list(my_list)
print(f"Перемешанный список: {my_list}")
````

<img width="362" height="43" alt="image" src="https://github.com/user-attachments/assets/e47b9115-e864-43e8-9fd1-261406476d68" />

## № 2.2.8 Используя модуль datetime, вычислите количество дней между двумя датами.

````
import datetime

def days_between_dates(date1, date2):
    delta = abs(date1 - date2)
    return delta.days

try:
    date1_str = input()
    date2_str = input()

    date_format = "%Y-%m-%d"
    date_start = datetime.datetime.strptime(date1_str, date_format).date()
    date_end = datetime.datetime.strptime(date2_str, date_format).date()

    days = days_between_dates(date_start, date_end)
    print(f"Количество дней между {date_start} и {date_end}: {days}")

except ValueError:
    print("Ошибка: Некорректный формат даты.")
````

<img width="502" height="77" alt="image" src="https://github.com/user-attachments/assets/1656e6f8-e826-43ac-85b7-80339353943c" />

## № 2.2.9 Используя модуль math, найдите целую часть числа (отбросьте дробную часть).

````
import math

def integer_part(number):
    return math.trunc(number)

try:
    number_input = input()
    number = float(number_input)
    part = integer_part(number)
    print(f"Целая часть числа {number}: {part}")

except ValueError:
    print("Ошибка: Введено нечисловое значение.")
````

<img width="330" height="52" alt="image" src="https://github.com/user-attachments/assets/385b02dc-a9cb-4ea0-9720-fdbe210c8713" />

## № 2.2.10 Используя модуль random, выберите один случайный элемент из списка.

````
import random

def choose_random_element(input_list):
    return random.choice(input_list)


my_list = ["apple", "banana", "cherry", "date", "meow"]
print(f"Список: {my_list}")
print(f"Случайный элемент: {choose_random_element(my_list)}")
````

<img width="530" height="47" alt="image" src="https://github.com/user-attachments/assets/68808953-9f1f-4420-8fbf-fbff010ca120" />


## Выводы
В ходе выполнения практической работы были успешно достигнуты все поставленные цели и решены задачи. Теоретическая часть позволила изучить модули в Python. Были освоены различные способы импорта, включая базовый импорт модулей, импорт с псевдонимами для удобства использования, а также выборочный импорт конкретных функций и констант.Практическая часть продемонстрировала широкие возможности стандартной библиотеки Python через работу с ключевыми модулями:
- Модуль math был применен для математических вычислений - работы с константами, вычисления квадратных корней и извлечения целых частей чисел
- Модуль random использовался для генерации случайных данных - создания случайных чисел, выбора элементов и перемешивания последовательностей
- Модуль datetime позволил эффективно работать с датой и временем, форматировать временные метки и получать текущие системные время
