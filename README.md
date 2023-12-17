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
  * Год публикации книги
  * Id автора книги (foreign key)

### Описание базы данных:
База данных будет использоваться в мобильном приложении, поэтому выбран СУБД SQLite. Она будет встроена в приложение с помощью библиотеки SQFLite(библиотека для работы с СУБД SQLite с использованием языка Dart).

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
![image](https://github.com/Vantwozz/lab2_Barovik/assets/95244485/69d1ce77-8fab-47d8-938a-e6147d824b9c)

### Пример заполнения данными:
```
INSERT INTO Authors (author_name, birth_year, nationality) VALUES
('Александр Пушкин', 1799, 'Россия'),
('Джордж Оруэлл', 1903, 'Великобритания'),
('Жюль Верн', 1828, 'Франция');
```
```
INSERT INTO Books (title, publication_year, author_id) VALUES
('Евгений Онегин', 1833, 1),
('1984', 1949, 2),
('Вокруг света за 80 дней', 1873, 3);
```
  
