## interface.showManageRightsModal: показать окно с паролем админа

> Пример запроса: 

```javascript
Poster.interface.showManageRightsModal({
  askRights: true,
  enableLogging: false,
})
```

Метод вызывает окно с паролем админа. Подходит для действий, которые невозможно выполнить без подтверджения администратора.

### Аргументы

В качестве аргумента принимается объект с параметрами:

Аргумент | Описание
-------- | --------
askRights | true — вывести окно, false — не выводить 
enableLogging | всегда false

### Ответ

Функция возвращает Promise с результатом запроса
