## users.getActiveUser: получить данные активного пользователя

> Пример запроса:

```javascript
Poster.users.getActiveUser().then((user) => {
	if (!user) {
		return;
	}

	console.log(user.name);
});
```

Метод получает данные активного пользователя, тип данных [User](/docs/v3/pos/types/user).

### Ответ

Функция возвращает Promise, который вернет `false`, если пользователя с таким ID нет и объект с данными пользователя, если он есть.
