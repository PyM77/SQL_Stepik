#database #SQL #programming 

Вложенный запрос, возвращаюший нескольок значении можно изпользовать с помошью операторов ANY and ALL, совместно с операциями сравнения

Оператор ANY - изпользуется для соотношение списка, так чтобы хотя бы один элемент подходил условию.

Оператор ALL - изпользуется для соотношениее списка, так чтобы все условия элементы, подходили условию.

*Пример*

Вывести информацию о тех книгах, количество которых меньше самого маленького среднего количества книг каждого автора

```SQL
SELECT title, author, amount, price
FROM book
WHERE amount < (
	SELECT AVG(amoumt)
	FROM book
	GROUP BY author
);
```

