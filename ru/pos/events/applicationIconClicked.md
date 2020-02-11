## applicationIconClicked: клик по иконке приложения

```javascript
Poster.interface.showApplicationIconAt({
    functions: 'Настройки интеграции',
    order: "Показать popup",
});
Poster.on('applicationIconClicked', function (data) {
    if (data.place === 'functions') {
        alert('Показать окно настроек');
    } 
    
    if (data.place === 'order') {
        alert('Показать окно с действиями для заказа');
    }
});
```

Событие срабатывает при клике по иконке или названию приложения. 
Места, в которых приложение должно отображать иконку вашего приложения устанавливаются методом [interface.showApplicationIconAt](/docs/v3/pos/interfaces/interface-showApplicationIconAt).

### Ответ

В качестве аргумента в обработчик приходит объект `data` с такими свойствами.

Свойство | Значение
-------- | ---------
place | Место в интерфейсе, в котором нажали на иконку приложения: order — кнопка с действием для заказ (левый нижний угол окна заказа), functions — кнопка с настройками в правом верхнем углу. 
order | Текущий [заказ](/docs/v3/pos/types/order), приходит если пользователь находится на экране заказа 
