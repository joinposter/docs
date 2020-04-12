## Установка

Для общения с кассой нужно использовать библиотеку Poster Transport

1. Скачайте [AAR файл библиотеки](https://github.com/joinposter/device-platform-example/blob/master/poster-transport/poster-transport.aar?raw=true)
2. В Android проекте перейдите во вкладку File → New → New Module → Import .JAR/.AAR Package 
3. Выберете файл библиотеки скачанный на первом шаге
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
