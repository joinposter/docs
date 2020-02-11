## Client: Клиент

> Пример объекта:

```json
{
   "id":85,
   "firstname":"John",
   "lastname":"Smith",
   "loyaltyType":1,
   "discount":0,
   "hidden":0,
   "groupId":1,
   "cardNumber":"39237515928",
   "bonus":0,
   "totalPayedSum":0,
   "city":"",
   "address":"0",
   "comment":"",
   "email":"ivanchenko@gmail.com",
   "birthday":"1990-08-03",
   "phone":"+380682152264",
   "extras":{
   }
}
```

### Свойства

Свойство | Описание
-------- | --------
id | Id клиента
address | Адрес
bonus | Сумма накопленных бонусных баллов
cardNumber | Номер карты лояльности
city | Город
comment | Комментарий
discount | Процент скидки или процент начисления бонусов (в зависимости от свойства loyaltyType)
firstname | Имя
groupId | Id группы лояльности, к которой принадлежит клиент
hidden | 1 — клиент удален, 0 — клиент не удален
lastname | Фамилия
loyaltyType | 1 — бонусная система лояльности, 2 — скидочная
phone | Номер телефона
totalPayedSum | Общая сумма, которую клиент потратил в заведении
birthday | Дата рождения в формате `yyyy-MM-dd`. Если дата не указана будет передано значение `0000-00-00` 
email | Email адрес
