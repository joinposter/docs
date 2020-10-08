## Shift: Кассовая смена

> Пример объекта: 

```json
{
   "cash_pos_id": 1597042083441,
   "cash_shift_id": 10,
   "timestart": 1597042083440,
   "timeend": 0,
   "amount_start": 100,
   "amount_end": 0,
   "comment": ""
}
```

### Свойства

Свойство | Описание
-------- | --------
cash_pos_id | ID кассовой смены
cash_shift_id | ID кассовой смены в бек-офисе. Может быть пустым, пока смена не засинхронизируется с сервером
timestart | Время открытия кассовой смены, timestamp
timeend | Время закрытия, timestamp
amount_start | Сумма открытия
amount_end | Сумма закрытия
comment | Комментарий
