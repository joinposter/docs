```js

(async function example() {
    // Подписываемся на событие
    Poster.on('finishedCooking', (res) => {
        console.log(res);
    });

    const order = (await Poster.orders.getActive()).order;
    const user = await Poster.users.getActiveUser();

    Poster.orders.finishedCooking(resOrder.order.id, { 
        id: order.products['0'].id, 
        userId: user.id, 
        count: 1,
    });
})();
```
