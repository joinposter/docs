## interface.scanBarcode: сканировать штрихкод или QR-код

> Пример сканирования кода

```javascript
Poster.interface.scanBarcode()
    .then(function (barcode) {
        console.log('barcode', barcode);
    })
```

> Пример ответа 

```json
{
  "barcode":"my barcode string"
}
```

Метод вызывает окно сканирования штрихкода или QR-кода. Доступен только в приложение Android и iOS версия 3.5 и выше. 

Чтобы определить доступен ли метод `scanBarcode` можно получить окружение из переменной `Poster.environment`. 
Если `environment.android` или `environment.iOS` — методы доступны. 

### Ответ

Функция возвращает Promise, который вернет объект со свойством `barcode` или ошибку.

Свойство | Описание
-------- | --------
barcode | Строка со значением штрихкода или QR-кода. Если окно закрыли без сканирования то вернется пустая строка.  


