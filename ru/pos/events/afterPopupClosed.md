## afterPopupClosed: после закрытия попапа

```javascript
Poster.on('afterPopupClosed', () => {
	alert("Закрыли попап");
});
```

Событие срабатывает при закрытии попапа, который ваше приложение открыло с помощью метода [interface.popup](/docs/v3/pos/interfaces/interface-popup).
