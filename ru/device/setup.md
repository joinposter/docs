## Установка библиотеки

Для работы с платформой нужно использовать в Андроид проекте библиотеку Poster Transport. 
Скачайте [приложение пример](https://github.com/joinposter/device-platform-example) чтобы увидеть как это работает на деле.

1. Скачайте [AAR файл библиотеки](https://github.com/joinposter/device-platform-example/blob/master/poster-transport/poster-transport.aar?raw=true)
2. В Android проекте перейдите во вкладку File → New → New Module → Import .JAR/.AAR Package 
3. Выберете файл библиотеки скачнный на первом шаге
4. Добавьте в build.gradle следующие зависимости

```kotlin
    dependencies {
        implementation project(':poster-transport')
        implementation 'org.java-websocket:Java-WebSocket:1.3.8'
        implementation 'com.google.code.gson:gson:2.8.0'
    }
```

5. Добавьте в манифест приложения следующие разрешения

```xml
    <manifest>
        <uses-permission android:name="android.permission.CHANGE_WIFI_STATE"/>
        <uses-permission android:name="android.permission.INTERNET"/>
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
        <uses-permission android:name="android.permission.WRITE_SETTINGS"/>
        <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
    </manifest>
```

## Начало работы

> Пример использования:

```kotlin
    class MainActivity : AppCompatActivity() {
    
        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_main)
            
            // Задаем настройки потока
            val policy = StrictMode.ThreadPolicy.Builder().permitAll().build()
            StrictMode.setThreadPolicy(policy)

            
            PosterTransport.init(applicationContext, "272")
            
            PosterTransport.onMessage = this.onMessage
            
            PosterTransport.start()
        }
    
        private val onMessage: (device: PosterDevice, message: String) -> Unit = { device, message ->
            Log.d("Lib", "Message: $message\nFrom: ${device.ip}")
        }
    }
```


1. При старте приложения задайте настройки для потока
2. Установите методом [PosterTransport.init](/docs/v3/device/methods/init?id=postertransportinit) контекст и уникальный `Id` вашего приложения
3. Вызовите метод [PosterTransport.start](/docs/v3/device/methods/start?id=postertransportstart) чтобы запустить поиск устройств
4. Установите слушатель сообщений [onMessage](/docs/v3/device/events?id=onmessage)




# Device Classes: Классы


## PosterTransport: Singleton-объект библиотки 

Параметр | Описание
-------- | --------
devices | Список всех подключенных устройств


## PosterDevice: Устройство  

Параметр | Описание
-------- | --------
Id | Уникальный идентификатор подключённого устройства, тип `String`
Ip | Ip адрес подключенного терминала, тип `String`
