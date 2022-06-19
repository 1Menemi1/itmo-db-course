# 29. Распределенные БД. Определение. Стратегии размещения данных в системе, их достоинства и недостатки. Понятие прозрачности

## Распределённые ДБ

`def` **Распределённая БД** - это набор логически связанных между собой разделяемых данных и их описаний, которые физически распределены по нескоьким вычислительным узлам.

> Понятно, что нужно разделять таблицы

`def` **Фрагментирование** - это разделение отношения, а получившиеся компоненты называются фрагментами.

### Типы распределённых БД

1. Гомогенные - одинаковая СУБД на всех узлах
2. Гетерогенные - разные СУБД на узлах

### Преимущества распределённых БД

1. Может нативно отображать структуру организации
2. Отказоустойчивость?
3. Повышение доступности и надёжности
4. Модульность системы

### Недостатки распределённых БД

1. Повышение сложности
2. Увеличение стоимости владения
3. Проблема защиты
4. Усложнение контроля за целостностью данных
5. Отсутствие стандартов

## Фрагментироваие

1. Горизонтальное (шардирование) - выделение подмножеств строк

2. Вертикальное - пытаемся хранить таблицу не как кортежи со всеми атрибутаит, а отдельно столбцы (храним на разнызх узлах данные разной секретности)

3. Смешанное - очев (когда есть фрагмент таблицы, который часто используется)

`def` **Репликация** - поддержка синхронизированных физических копий некоторго объекта БД

## Стратегии размещения данных в распределённой системе

### 1. Фрагментированное (раздельное) размещение

БД разбиваетсяна непересекующиеся фрагменты, и каждый из фрагментов располагается строго на одном узле

### 2. Размещение с полной репликацией

На каждом узле есть полная реплика всей БД (олимпа ИТМО по рпоге)

### 3. Размещение с выборочной репликацией

Разделяем БД тем или иным способом, и для каждого фрагмента решаем 2 задачи:

1. Сколько копий фрагмента сделать
2. Где их прасположить

> СУБД должна принимать данные решения

## Принципы прозрачности СУБД

### 1. Прозрачность фрагментации

Пользователь не знает ,как фрагментирован тот или иной объект

### 2. Прозрачность расположения фрагмента

Пользователь не знает ,на каком конкретном узле расположен тот фрагмент, к которому он обращается

### 3. Прозрачность количества реплик

Пользователь не может обратиться к конкретнной реплике

### 4. Прозрачность контроля доступа

Пользователь не знает, данных действительно нет или у него нет на них доступа
