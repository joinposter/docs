## afterPopupClosed: After the Popup Close

```javascript
Poster.on('afterPopupClosed', () => {
	alert("Popup closed");
});
```

The event is triggered when the popup, which has been opened by your application using the [interface.popup](/en/docs/v3/pos/interfaces/interface-popup) method, closes.
