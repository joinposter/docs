## clients.create: создать клиента на терминале

> Пример запроса на создание нового клиента 

```javascript
Poster.clients.create({
        client: {
            client_sex: 1,
            client_name: "Иванченко Владимир", 
            client_groups_id_client: 1
        }
    })
    .then(function (client) {
        console.log('new client', client);
    });
```

> Пример ответа 

```json
{
  "client":{
    "address":"0",
    "bonus":0,
    "discount":10,
    "firstname":"Владимир",
    "groupId":1,
    "id":33,
    "lastname":"Иванченко",
    "loyaltyType":1,
    "phone":"",
    "totalPayedSum":0
  }
}
```

Метод создает нового клиента на терминале и возвращает модель этого клиента [Client](/docs/v3/pos/types/client)

### Аргументы

Аргумент | Описание
-------- | --------
1-й, объект запроса | Объект с полем `client` с данными клиента
 
Поле `client` содержит объект с такими свойствами
 
Свойство | Описание
-------- | --------
client_name | Обязательный параметр, строка c ФИО клиента 
client_groups_id_client | Обязательный параметр, id группы клиента
client_sex | Пол клиента: 1 — мужчина, 2 — женщина
country_phone_code | Число, код страны клиента, например, 380 — для Украины
phone | Строка, номер телефона клиента  
email | Строка, имейл клиента
card_number | Строка, номер карты клиента
city | Строка, город клиента
address | Строка, адрес клиента
country | Строка, стана клиента
comment | Строка, комментарий к клиенту 
birthday | Строка, в формате dd-MM-YYYY

### Ответ

Функция возвращает Promise, который вернет объект со свойством `client` или ошибку. 

Свойство | Описание
-------- | --------
client | Объект типа [Client](/docs/v3/pos/types/client)
