## interface.showApplicationIconAt: Display the Application Icon in Specified Placeholders

> Request example:

```javascript
Poster.interface.showApplicationIconAt({
    functions: 'App settings',
    order: 'App popup',
});
```

The method adds an icon or application name to different places in the interface. Clicking on the name or icon of the application will trigger an `applicationIconClicked` event.

### Arguments

Argument | Description
-------- | -----------
1st, places | An object with the place to display the application icon or name as the key and the header as the value

### Placeholders available

Name | Description
---- | -----------
functions | Upon clicking on the Products icon in the upper-right corner of the application; it is suitable for general functions and settings.
order | Upon clicking on the ellipsis in the lower left corner of the order screen. It is suitable for functions that relate to the current order.
receiptsArchive | Upon clicking on the ellipsis in the orders archive. It is suitable for app which works with receipts history.
payment | Adds button to checkout screen


Example of `receiptsArchive` placeholder:

<img src="/img/site/docs/app-icon-receipts-archive.jpg" alt="Placeholder example for receiptsArchive">


Example of `payment` placeholder:

<img src="/img/site/docs/app-icon-payment.jpg" alt="Placeholder example for payment">
