## applicationIconClicked: Click on the App Icon

```javascript
Poster.interface.showApplicationIconAt({
    functions: 'App settings',
    order: "Show app popup",
});
Poster.on('applicationIconClicked', function (data) {
    if (data.place === 'functions') {
        alert('App settings');
    } 
    
    if (data.place === 'order') {
        alert('App order action');
    }
});
```

The event is triggered by clicking on the icon or name of the application. The places where the application should display the icon of your application are set using the [interface.showApplicationIconAt](/en/docs/v3/pos/interfaces/interface-showApplicationIconAt) method.

### Response

As an argument, the `data` object comes to the handler with the following properties.

Property | Value
-------- | -----
place | The place in the interface where the application icon has been clicked on: order—the button with the operation for the order (the bottom left corner of the order window), functions—the button with the settings in the upper-right corner.
order | The current [order](/en/docs/v3/pos/types/order); it comes if the user is on the order screen

