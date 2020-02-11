## interface.scanBarcode: Scan a Barcode or a QR Code

> Request example:

```javascript
Poster.interface.scanBarcode()
    .then(function (barcode) {
        console.log('barcode', barcode);
    })
```

> Response example: 

```json
{
  "barcode":"my barcode string"
}
```

The method calls a barcode or QR code scanning window. It is available only in apps on Android and iOS version 3.5 and above.

To determine the availability of the `scanBarcode` method, you can get the environment from the `Poster.environment` variable. 
If it is `environment.android` or `environment.iOS`, the methods are available.

### Response

The function returns Promise, which returns an object with a `barcode` property or an error.

Property | Description
-------- | -----------
barcode | A line with a barcode or QR code value. If the window is closed without scanning, an empty line will be returned.

