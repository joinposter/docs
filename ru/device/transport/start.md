# Начало работы с транспорта

Чтобы использовать транспорт, включить переключатели **POS платформа** и **Device платформа** в настройках вашего приложения.


### Как работают устройства на кассе

!> Чтобы тестировать транспорт вам нужно открыть кассу на 
[iOS](https://apps.apple.com/us/app/poster/id691098784), 
[Android](https://play.google.com/store/apps/details?id=com.joinposter&hl=ru) или 
[Desktop](https://joinposter.com/mac) приложении.

Поиск устройств выполняется через WiFi, для этого касса и внешнее устройство должны быть в одной сети. 
Как только касса впервые увидит устройство в сети у вас появится всплывающее окно, c предложением подключить приложение.

Если окно не показывается, то можно выполнить поиск вручную. 
Для этого зайдите в Настройки → Устройства → Другое оборудование → Ваше приложение → Подключить устройство.
<video src="/img/site/docs/devices-custom-search.mp4" controls autoplay="true" width="100%"></video>

После подключения ваше устройство будет доступно в разделе Настройки → Устройства. 
Для устройств вы можете выводить интерфейс с настройками. 
Например, для экрана на кухню мы показываем список цехов которых привязан экран.


### Подготовка Android приложения

1. Установите по [инструкции](/docs/v3/device/transport/methods/setup) библиотеку в ваш проект 
2. При старте приложения задайте настройки для потока
3. Установите методом [PosterTransport.init](/docs/v3/device/transport/methods/init) контекст и `ID` вашего приложения
4. Вызовите метод [PosterTransport.start](/docs/v3/device/transport/methods/start) чтобы запустить поиск устройств

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
        // Задаем настройки потока
        val policy = StrictMode.ThreadPolicy.Builder().permitAll().build()
        StrictMode.setThreadPolicy(policy)

        // Инициализировали библиотеку со своим ID приложения
        PosterTransport.init(applicationContext, "272")

        // Включили библиотеку чтобы касса могла найти наше устройство
        PosterTransport.start()
    }
}
```


### Отправка и получение сообщений

Касса и внешнее устройство могут отправлять и получать сообщения друг другу. 

1. Получите список всех доступных вам устройств используйте метод [Poster.devices.getAll](/docs/v3/device/transport/methods/getAll) 
2. Отправите сообщение устройству используйте метод [sendMessage](/docs/v3/device/transport/methods/sendMessage)
3. Подпишитесь на сообщения методом [deviceMessage](/docs/v3/device/transport/events/onMessage)

К примеру этот код на терминале отправит сообщение всем доступным устройствам. 
На каждое сообщение от устройства будет показывать всплывающее сообщение.

```javascript
// Подписываемся на событие 
Poster.on('deviceMessage', (msg) => {
    // Показываем всплывающее сообщение
    Poster.interface.showNotification({
        title: 'Device Message',
        message: msg.text
    })
});

// Получаем всем доступным устройства
let devices = await Poster.devices.getAll();
devices.forEach((device) => {
        // Рассылаем сообщение
    device.sendMessage({
        text: 'Hello, World!',
        terminalId: Poster.settings.accountUrl + Poster.settings.spotTabletId
    });
});
```

По такому же принципу как и на кассе можно отправить сообщения всем кассам доступным в сети:

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        // ...иницализация билиотеки        

        // Подписались на сообщения из кассы
        PosterTransport.onMessage = this.onMessage
    }
    
    private val onMessage: (device: PosterDevice, message: String) -> Unit = { device, message ->
        // Показали сообщение с кассы
        Log.d("Lib", "Message: $message\nFrom: ${device.ip}")
                
        // Отправили обратно сообщение
        device.sendMessage("{ text: \"Hi back from the device\" }")
    }
}
```

Таким образом касса и внешнее устройство могут общаться друг с другом по локальной сети без интернета. 
На кассе доступны методы POS платформы которые работают без интернета. 
Например, если вы захотите сделать экран покупателя вы подписываетесь на 
[событие добавления товара в чек](/docs/v3/pos/events/orderProductChange) и при каждом событие отправляете заказа на внешнее устройство и отображает чек.


?> Посмотрите [пример приложения на Github](https://github.com/joinposter/device-platform-example)
