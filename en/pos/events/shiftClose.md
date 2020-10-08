## shiftClose: Closing of a cash shift

```javascript
Poster.on('shiftClose', (data) => {
    console.log(data.shift);
});
```

Event fires when cash shift closes

### Ответ

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | --------
shift | Object of type [CashShift](/en/docs/v3/pos/types/shift)
