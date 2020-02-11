## makeApiRequest: сделать запрос к API Poster

> Пример запроса:

```javascript
Poster.makeApiRequest('clients.getGroups', {
    method: 'get'

}, (groups) => {
	if (groups) {
		console.log(groups);
	}
});
```

Метод делает запрос к API Poster. 
Запросы к API можно делать и через [Poster.makeRequest](/docs/v3/pos/requests/makeRequest), но `Poster.makeApiRequest` упрощает эту процедуру: автоматически подставляет токен вашего приложения и аккаунт текущего пользователя, делает `JSON.parse` ответа.

### Аргументы

Аргумент | Описание
-------- | --------
1-й, method | Название метода из Poster API
2-й, options | Объект с настройками запроса. Доступны все параметры метода [jQuery.ajax](http://api.jquery.com/jquery.ajax/)
3-й, callback | Функция-обработчик ответа

### Ответ

В `callback` в качестве первого аргумента придет объект с ответом API или `false`, если запрос не удался.
