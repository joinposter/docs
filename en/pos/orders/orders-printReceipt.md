## orders.printReceipt: Print a Receipt

```javascript
Poster.orders.printReceipt(1503219480866, 'loremipsum', 'To scan QR code use special app')
```

The method prints a receipt, with an optional QR code.

### Arguments

Argument | Description
-------- | -----------
1st, id | Order ID (unix-timestamp in milliseconds)
2nd, qrCode | A line the QR code will be generated from, an optional parameter
3rd, qrCodeTitle | The header that will be printed at the bottom of the QR code, an optional parameter

