## clients.get: получить данные клиента

> Пример запроса:

```javascript
Poster.clients.get(1).then((client) => {
	if ( ! client) {
		return;
	}

	console.log(client.phone);
});
```

Метод получает данные клиента по ID, тип данных [Client](/docs/v3/pos/types/client).

### Аргументы

Аргумент | Описание
-------- | --------
1-й, id | ID клиента

### Ответ

Функция возвращает Promise, который вернет `false`, если нет клиента с таким ID. Или объект с данными клиента, если он есть.

Параметр | Описание
-------- | --------
client | Объект типа [Client](/docs/v3/pos/types/client)
