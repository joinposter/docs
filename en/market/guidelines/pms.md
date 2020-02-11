# Property Management System integration guide


Integration should send orders from Poster to PMS. 
Cashier should have an ability to close order in a venue or put it on guests account in PMS. 
The perfect example is [integration with Cloudbeds](https://joinposter.com/en/support/apps/marketplace/692). 

![Plugin workflow](https://raw.githubusercontent.com/joinposter/pos-platform-boilerplate/master/examples/pms/demo.gif)


## Integration guide

First things first, launch our [POS Platform](/en/docs/v3/pos/index) boilerplate. 
In `example/pms` folder, you will find an example which you can adapt for your PMS. 

!> [Integration code on GitHub](https://github.com/joinposter/pos-platform-boilerplate/tree/master/examples/pms)
  

### Show all checked in guests

1. Add button **Assign hotel guest** to the order context menu ••• with [Poster.showApplicationIconAt](/en/docs/v3/pos/interfaces/interface-showApplicationIconAt) method
2. Subscribe to the button's click with [Poster.on](/en/docs/v3/pos/events/on) method
3. Show your interface in the pop-up when the button was clicked, with [Poster.interface.popup](/en/docs/v3/pos/interfaces/interface-popup) method
4. Make an HTTP request to your backend to get all checked in guests in the hotel with [Poster.makeRequest](/en/docs/v3/pos/requests/makeRequest) method
5. Render your web interface with all guests where the cashier can assign a guest to the order

```js
// Adds button to ••• menu
Poster.interface.showApplicationIconAt({
    order: 'Assign hotel guest',
});

// Will be triggered on button click
Poster.on('applicationIconClicked', (data) => {
    // Show the window with all checked in guests
    Poster.interface.popup({
        width: 600,
        height: 500,
        title: "Assign hotel guest"
    });
});
```

### Assign guest to the order

In the pop-up window you should render all checked in guests in the hotel. 
Give an ability to search through guests with guest name or room number. 
When cashiers select the room and click **Apply** you save bond between guest and the order in this way:

1. Get current order with the [Poster.orders.getActive](/en/docs/v3/pos/orders/orders-getActive) method
2. Save order ID and reservation ID to the local storage
3. Add a comment to the order with a [Poster.orders.setOrderComment](/en/docs/v3/pos/orders/orders-setOrderComment), so that cashier could distinguish assigned orders

```js
async function onReservationApply(reservation) {
    const res = await Poster.orders.getActive();
    const activeOrder = res.order;

    localStorage.setItem(`order${activeOrder.id}`, reservation.id);
    Poster.orders.setOrderComment(activeOrder.id, `Order assigned to the reservation ${reservation.id}`)
}
```

### Send the order to PMS

When cashier closes the order show pop-up window where he can choose how the guest will pay for his order. 
He can pay here, in a venue, or on the front desk, in order to do so:

1. Subscribe to the [beforeOrderClose](/en/docs/v3/pos/events/beforeOrderClose) event with the [Poster.on](/en/docs/v3/pos/events/on) method
2. Save the callback function `next()`, you will need it later to proceed to order checkout
3. Show your pop-up where the cashier will select the place, where he would like to pay


```js
// Will be triggered when cashier press Pay
Poster.on('beforeOrderClose', (data, next) => {
    const { order } = data;
    
    const reservation = localStorage.getItem(`order${order.id}`);
    if (!reservation) {
        console.warn('skipped order reservation for order', order.id);
        next();
        return;
    }
    
    // Save callback for the future 
    window.nextCallback = next;
    
    Poster.interface.popup({
        title: 'Choose payment place',
        width: 500,
        height: 370,
    });
});
```


**Guest pays on front desk scenario:**

1. Get a current order with the [Poster.orders.getActive](/en/docs/v3/pos/orders/orders-getActive) method 
2. Get all products and dishes names with the [Poster.products.getFullName](/en/docs/v3/pos/products/products-getFullName)
3. Send the order to PMS with the [Poster.makeRequest](/en/docs/v3/pos/requests/makeRequest)
4. Close the order in Poster with the [Poster.orders.closeOrder](/en/docs/v3/pos/orders/orders-closeOrder)


**Guest pays here scenario:**

1. Call `next()` function which you have saved before to proceed to the regular Poster checkout window
2. Subscribe to the [afterOrderClose](/en/docs/v3/pos/events/afterOrderClose) event and send it to PMS

In this scenario guest already payed for the order and additional charges shouldn’t be applied

