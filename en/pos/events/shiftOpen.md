## shiftOpen: Opening of a cash shift

```javascript
Poster.on('shiftOpen', (data) => {
    console.log(data.shift);
});
```

Event fires when cash shift opens

### Ответ

As an argument, the `data` object comes to the handler with the following properties

Property | Value
-------- | --------
shift | Object of type [CashShift](/en/docs/v3/pos/types/shift)
