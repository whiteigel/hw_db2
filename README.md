#Домашнее задание

Написать SQL-запросы для создания таблиц из схемы, реализованной в предыдущем домашнем задании.

```
CREATE DATABASE netology
    WITH OWNER = netology;

CREATE TABLE genre(
	id serial primary key,
	name varchar(40)
);

CREATE TABLE singer(
	id serial primary key,
	name varchar(40),
	genre_id integer references genre(id)
);

CREATE TABLE album(
	id serial primary key,
	title varchar(250),
	release_date integer,
	singer_id integer references singer(id)
);

CREATE TABLE track(
	id serial primary key,
	title varchar(250),
	duration integer,
	album_id integer references album(id)
);
```