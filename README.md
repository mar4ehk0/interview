# Вопросы на интервью

#### Как микросервисы могут общаться друг с другом?

http, polling, uqeue

#### Какие виды sql injection вы знаете?

слепые и т.д.

#### Что должно содержаться в логах?

дата, уровень, модуль

#### Чем git fetch отличается от git pull?

fetch забирает, а pull забирает и мержит

#### Как создать ветку в git?

git checkout -b branch_name

#### Как вызвать команду при сборке докер контейнера?

RUN

#### Зачем в докере делает команда CMD?

То, что в этой команде, запустится при старте контейнера

#### Где валидировать json данные, которые пришли в django?

Если у нас django rest framework, то в сериалайзере

#### Зачем нужны генераторы (yeld)?

Для вычисления следующего значения только в момент вызова, а не для просчета всех значений предварительно.

#### Задача по алгоритмам #0

```
a = [1, 3, 4]
b = [1, 4, 5]
c = [2, 7, 1]
n = 4

def check(a, b, c, n):
    # реализовать функцию check, которая получает 3 массива a, b, c и число n
    # возвращает True если есть хоть одна комбинация, где сумма чисел по одному числу каждом массиве равна n
    # в данном примере должно быть True, т.к. a[0]+b[0]+c[0]=1+1+2=4
    return True or False
```

Реализация:

```
def check(a, b, c, n):
    for i_a in a:
        for i_b in b:
            for i_c in c:
                if i_a + i_b + i_c == n:
                    return True
    return False

print(check(a, b, c, n))
```

Какая алгоритмическая сложность данной задачи? o(n^3)

Как можно ускорить алгоритм?

```
def check(a, b, c, n):
    for i_a in a:
        if i_a > n:
            continue
        for i_b in b:
            if i_a + i_b > n:
                continue
            for i_c in c:
                if i_a + i_b + i_c == n:
                    return True
    return False

print(check(a, b, c, n))
```

Как можно снизить алгоритмическую сложность?

```
def check(a, b, c, n):
    c_set = set(c)
    for i_a in a:
        for i_b in b:
            if (n - i_a + i_b) in c_set:
                return True
    return False

print(check(a, b, c, n))
```
