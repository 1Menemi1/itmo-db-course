# 6. Логическая и физическая модели данных. Содержание уровней

## Логическая (даталогическая) модель

Определяет **способ** организации данных (концепцию), а **не конкретную реализацию**.

Набор схем отношений, обычно с указанием первичных ключей, а также связей между отношениями, представляющих собой внешние ключи. Учитывается специфика конкретной модели данных, но не учитываться специфика конкретной СУБД.

1. Иерархическая - возникают несколько деревьев(каталогов): алфавитный каталог, тематические каталоги
2. Сетевая - поля + агрегаты + связи
3. Реляционная - основным объектом выступает отношение ~ двумерный массив
4. Постреляционная - поле может иметь собственную структуру
5. Многомерная - можно сделать кубом и, как результат, отчёт - срез куба(некоторая плоскость)
6. Объектная(объектно-ориентированная)

## Физическая модель

Сопоставима с внутренним уровнем (построение часто автоматизировано).

Создание схемы базы данных для конкретной СУБД:

Выбор решений, связанных с физической средой хранения данных (выбор методов управления дисковой памятью, разделение БД по файлам и устройствам, методов доступа к данным), создание индексов.

1. Определяем всевозможные ограничения в названиях и т.п
2. Ограничения на типы данных (доменты атрибутов)
3. Индексы и всё такое
4. Разделение на отдельные файлы, партиции

