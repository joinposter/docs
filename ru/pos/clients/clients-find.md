## clients.find: найти клиента на терминале  

> Пример запроса на поиск клиента 

```javascript
Poster.clients.find({
        searchVal: 'Владимир'            
    })
    .then(function (result) {
        console.log('clients search', result);    
    })
```

> Пример ответа 

```json
{
   "foundClients":[
      {
         "id":33,
         "firstname":"Владимир",
         "lastname":"Иванченко",
         "loyaltyType":1,
         "discount":10,
         "hidden":0,
         "groupId":1,
         "cardNumber":"0",
         "bonus":0,
         "totalPayedSum":0,
         "city":"0",
         "address":"0",
         "comment":"0",
         "phone":""
      }
   ],
   "foundByCard":[

   ]
}
```

Метод создает нового клиента на терминале. И возвращает модель этого клиента [Client](/docs/v3/pos/types/client)

### Аргументы

Аргумент | Описание
-------- | --------
1-й, объект запроса | Объект со свойством `searchVal` с данными клиента
 
 
Свойство | Описание
-------- | --------
searchVal | Обязательный параметр, строка по которой ищем клиента, поиск ведется по телефону, имени, фамилии и карте клиента. 

### Ответ

Функция возвращает Promise, который вернет объект с такими свойствами.

Свойство | Описание
-------- | --------
foundClients | Массив с найденными клиентами, содержит объекты типа [Client](/docs/v3/pos/types/client)
foundByCard | Массив с найденными клиентами с совпадениями по карте клиента, содержит объекты типа [Client](/docs/v3/pos/types/client)
