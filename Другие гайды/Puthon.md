![logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/150px-Python-logo-notext.svg.png)
# Python FAQ 
## **Скачать тут** -> [Тык](https://www.python.org/downloads/)
---
## **Куча всего и обо всем** P.S главное не забыть сделать нормально
---
+ print(sum(range(2,101,2))) = сумма всех четных чисел от 1 до 100
___
> from statistics import mean  
it = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10)  
mean(it)  
print(mean(it))  
Среднее арифметическое 5.5  
___
+ >### **Решение поиска большего**
>if - условие(если)  
a = 1  
b = 8  
c = 3  
d = 6  
e = 2  
max - a  
if b > max: max = b  
if c > max: max = c  
if d > max: max = d  
if e > max: max = e  
print(max)   
max = b  
___
abs() = Установка положительного значения числа  
Min() = вычисление минимального из значений 
max() = вычисление наибольшего из значений  
pow() = возведений чисел в степень pow(6,2) = 36  
round() = округление чисел к ближайшему целому  
Другие модули = Import math  
mach.ceil() = округление до наибольшего числа  
mach.floor() = округление до наименьшего числа   
mach.factorial() = фактроиал числа   
mach.trunc() = отбрасывает дробную часть (аналог int)  
mach.log(2) = логорифмы числа  
mach.sqrt() = квадратный корень из числа   
mach.sin() = синус числа   
mach.cos() = косинус числа  
mach.pi = константа П  
mach.e = константа Е  
__
print() = вывод данных в консоль  
input() = ввод данных из стандартного входного потока  
sep = разделитель между данными = Print(a, b , c, sep=" | ")  
end = завершающий символ или строка =  Print("hello world", end=" ")  
___
len = вычисление длинны строки
str() = преобразование в строку
in = проверка вхождения подстроки в строку 
ord() = определение кода символа
___
### **ВСЕ СИМВОЛЫ ИДУТ С ИНДЕКСА 0!!!!!**
___
### **Методы строк!**
upper() = Преобразование строки к верхнему регистру  
lower() = Преобразование строки к нижнему регистру
capitalize() = Переводит первый символ строки в верхний регистр, а все остальные в нижний  
count() =   
find() =  
index() =  
replace() =  
isalpha() =  
isdigit() =  
rjust() = Делает длину строки не меньшей width, по необходимости заполняя первые символы символом fillchar  
split() =  
strip() = Удаление пробельных символов в начале и в конце строки  
\n = Новая строка = hello\npython  
\t - табуляция hello\tpython  
\\ - обратный слеш = hello\\python  
\' и \" - экранирование кавычек hello\"python\"  
absd.append(100) = добавляет в список значение в конец списка  
absd.insert(3 = индекс элемента -1000 = добавляемый элемент) = добавляет элемент новое значение в список по индексу  
a.remove(true) = удаляет элемент из списка по названию  
img = [1,2,3,4], [1,2,3,4], [1,2,3,4], [1,2,3,4], [1,2,3,4]] = многомерный список(вложенный список)  
img [0] = обращаемся к первому списку [1] обращаемся к второму элементу списка 0  
img[1] = [0,0,0,0] = изменение 2-го списка на нужные переменные  
## Синтаксис
+ >**Int** - целые числа
+ >**float** - Плавающие числа
+ >**str** - строка(буквы,символы)
+ >A + B — сумма
+ >A - B — разность
+ >A * B — произведение
+ >A / B — частное
+ >A ** B — возведение в степень
+ >A // B — целочисленное деление
+ >A % B — остаток от деления
+ >A + B — конкатенация
+ >A * n — повторение n раз, значение n должно быть целого типа.
+ >**True** - истина
+ >**False** - ложь
+ >while - последовательность
+ >for - альтернатива while
+ >списки \[] list()
+ >>a = list1 + list2 - комбинация списков 
+ >sort - сортировка list1.sort
+ >создание ключей
+ >keys = {"one":1, "two":2}
+ >l = {"name": Dima, "family": Андреев}
+ >def - определение новой функции
## **сортировка**
    a = [1,2,3,4,5]
    for elem in a:
        if elem <> 5:
            print (elem)
Print [(elem for elem in a if elem<>5)]
___
## **Ветвление**
    if Условие:  
     Блок_инструкций_1  
    else:  
     Блок_инструкций_2  
**Блок_инструкций_1 будет выполнен, если Условие истинно. Если Условие ложно, будет выполнен Блок_инструкций_2. Можно не использовать Else**
___
import random

random.seed()

class BlackJack:
    def __init__(self):
        self.deck = [2, 3, 4, 5, 6, 7, 8, 9, 10, 'Jack', 'Queen', 'King', 'Ace'] * 4
        self.score = 0
        self.bot_score = 0

    def print_card(self, current, score, bot):
        if not bot:
            print(f'Вам попалась карта {current}. У вас {score} очков.')
        else:
            print(f'Крупье попалась карта {current}. У крупье {score} очков')

    def random_card(self, score, bot):
        current = self.deck.pop()
        if type(current) is int:
            score += current
        elif current == 'Ace':
            if score <= 10:
                score += 11
            else:
                score += 1
        else:
            score += 10
        self.print_card(current, score, bot)
        return score

    def choice(self):
        score = self.random_card(self.score, False)
        bot_score = self.random_card(self.bot_score, True)
        while True:
            choice = input('Будете брать карту? y/n\n')
            if choice == 'y':
                score = self.random_card(score, False)
                if bot_score < 19 and score <= 21:
                    bot_score = self.random_card(bot_score, True)
                if score > 21 or bot_score == 21:
                    print('Извините, но вы проиграли')
                    break
                elif score == 21 and bot_score == 21:
                    print('ничья')
                elif score == 21 or bot_score > 21:
                    print('Поздравляю, вы победили!')
                    break
            elif choice == 'n':
                if score > bot_score and bot_score < 19:
                    while bot_score < 19:
                        bot_score = self.random_card(bot_score, True)
                if score < bot_score <= 21:
                    print(f'Вы проиграли, у вас {score} очков, у крупье {bot_score} очков')
                else:
                    print(f'Вы победили, у вас {score} очков, у крупье {bot_score} очков')

                break

    def start(self):
        random.shuffle(self.deck)
        print('Игра в BlackJack началась')
        print('В блэкджеке десятки, валеты, дамы и короли стоят по 10 очков.\nТуз может стоить 1 или 11 очков')
        print('----------------------------------')
        self.choice()

        print('До новых встреч!')


game = BlackJack()
game.start()