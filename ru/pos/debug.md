## Отладка приложения

### Отладка на ПК

В контейнере у настоящих пользователей ваше приложение будет грузиться с поддомена `platform.joinposter.com`.
Чтобы обновить приложение, вам нужно сделать деплой и перезагрузить планшет.
Однако в процессе разработки это не удобно и вам нужно обновлять приложение намного быстрее.

Для этого:

1. В вашем [аккаунте разработчика](/login) на странице **Пользователи и роли** добавьте аккаунт на котором вы проверяете приложение.
2. В правом верхнем углу терминала нажмите на **</>**, откроется окно настроек платформы.
3. В окне настроек платформы переключите приложение в режим **Development**.


<img src="/img/site/docs/pos-platform-dev-mode.gif" alt="Пример переключения в режим разработки">


В режиме разработки bundle в контейнере будет загружаться с вашего локального компьютера по адресу `http://127.0.0.1:8080/bundle.js`.
Вы можете использовать свой веб-сервер, либо `webpack-dev-server`, если пользуетесь нашим boilerplate для разработки.

С `webpack-dev-server` из нашего boilerplate, ваше приложение будет автоматически перезагружаться в контейнере, когда вы меняете его исходный код.
Это позволит вам быстро вносить изменения и получать обратную связь.

Для отладки вы можете использовать Chrome Developer Tools.
Все `console.log` в контейнере вашего приложения, отображаются в консоли веб-версии Poster.

### Отладка на планшете iOS, Android

Для отладки на планшете в окне настроек платформы на терминале перейдите в режим разработки.
В поле под переключателем введите IP адрес вашего компьютера на котором запущен webpack-dev-server. 
