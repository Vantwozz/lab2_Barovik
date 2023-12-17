# Вторая лабораторная работа Капитанов Иван 3 курс 12 группа
## База данных будет состоять из двух справочников: Авторы и книги.

### Справочник Авторы будет содержать колонки:
  * Id автора (primary key)
  * Имя автора
  * Год рождения автора
  * Национальность автора

### Справочник Книги будет содержать колонки:
  * Id книги (primary key)
  * Название книги
  * Дата публикации книги
  * Id автора книги (foreaign key)

### Описание базы данных:
База данных будет использоваться в мобильном приложении, поэтому был выбран СУБД SQLite, которая будет встроена в приложение с помощью библиотеки SQFLite(библиотека для работы с СУБД SQLite с использованием языка Dart)
Так как в СУБД SQLite нет формата данных, в котором можно было бы хранить дату, будет использоваться формат храниения даты timestamp(временная метка), который хранит сколько прошло секунд с 1970-01-01 00\:00\:00 по нулевому часовому поясу и занимает 4 байта.
Скрипты для создания таблиц бд:
```
CREATE TABLE Authors (
    author_id INTEGER PRIMARY KEY AUTOINCREMENT,
    author_name TEXT NOT NULL,
    birth_year INTEGER,
    nationality TEXT
);
```
```
CREATE TABLE Books (
    book_id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    publication_year INTEGER,
    author_id INTEGER,
    FOREIGN KEY (author_id) REFERENCES Authors(author_id)
);
```
### Схема базы данных:
![image](https://github.com/Vantwozz/lab2_Barovik/assets/95244485/68320818-d565-424a-a41e-2574a334b174)
  
