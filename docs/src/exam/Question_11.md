# 11. Реляционная модель данных: виды ключей, реализация различных типов связей, виды целостности

## Виды ключей

`def` **Суперключ** - это аттрибут или множество аттрибутов, единственным образом идентифицирующие кортеж.

> _Всё множество аттрибутов само по себе является **суперключом**._

`def` **Потенциальный ключ** - это суперключ, который не содержит модмножество, также являющегося суперключом _(суперключ минимального размера)_.

> _Потенциальный ключ может быть **простым** и **составным**._

`def` **Первичный ключ (Primary Key)** - это один из потенциальных ключей, который выбран для уникальной идентификации кортежей данного отношения.

`def` **Внешний ключ (Foreign Key)** - это аттрибут или множество аттрибутов, которое соответствует потенциальному ключу некоторого, может быть, того же самого отношения.

## Типы связей

### 1. Один-к-одному

Первичный ключ одного из отношений является одновременно и внешним ключём.

> Есть таблица работников, и таблица менеджеров по продажам. Id работника будет `PK`, который взят из `PK` менеджера. Таким образом, Id менеджера - это `PK` и `FK` одновременно.

**Employee**

| Id_Emp (`PK`) | Id_Boss (`FK`) | Other fields |
| :-----------: |:--------------:| :-----------:|
|       2       |        1       |     field    |

**SalesPerson**

| Id_SalesPerson (`PK`, `FK`) | Other fields |
| :-------------------------: | :-----------:|
|           1, 2              |     field    |

### 2. Один-к-многим

> Есть таблица групп и студентов. Значение Id группы у студента будет `FK`, который взят из Id, то есть `PK` группы.

**Student**

| Table_Number | LastName | MiddleName | FirstName | Group_Id (`FK`) |
| :----------: |:--------:| :---------:| :-------: | :-------------: |
|       1      |  Кудашев | Эдуардович |  Искандер |       32011     |

**Group**

| Group_Id (`PK`) |  Other fields |
| :-------------: | :-----------: |
|      32011      |      field    |

### 3. Много-ко-многим

Обычно используются таблицы-связки, хранящие связи по Id.

> Есть менеджеры, каждый из которых продаёт продукты. Создаём таблицу с `PK` продукта и менеджера.

## Виды целостности

1. Сущностная целостность - в отношении ни один аттрибут `PK` не может содержать `NULL` значение
2. Ссылочная целостность - если в отношении существует `FK`, то значение этого ключа должно соответствовать существующему значению `PK` в другом отношении
