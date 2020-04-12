## onError: Событие ошибки связи с устройством

```kotlin
PosterTransport.onError = { error ->
    Log.d(TAG, "Error: ${error.message ?: error.toString()}")
}
```


### Аргументы

Параметр | Описание
-------- | --------
1й, error | Exception в котором хранится объект ошибки 
