# POS Events: Events

As the waiter works with the Poster cash program, the platform notifies applications of events in the system. The examples of events:

- The waiter has entered the system under his pin code.
- The waiter is going to close the order.
- The order is closed.

```javascript
Poster.on('beforeOrderClose', (data, next) => {
	alert("Alert before order close");
	next();
});
```

An application on the platform can subscribe to events using the `Poster.on` method and transmit a handler function that will be called when the event is triggered. For example →

The platform will transmit the `data` argument to the handler function. `data` contains information associated with this particular event.

For events that interrupt the standard execution thread (these are usually the events with names that begin with “before”), the `next` argument is additionally transmitted. This is a function that the application should call when it finishes processing the event. After `next` is called, the thread execution will return to Poster.

If several applications are subscribed to one event, their handlers will be called in turn; after `next` is called in the handler of one application, the handler of the second application will be called.

The platform expects that for events that transmit `next` to the handler, the application will call`next()` within five seconds after the handler has been triggered or will display the interface the user has to interact with (for example, using the `Poster.interface.popup` method). In case the application does not finish processing the event for five seconds, the platform will reload the application and continue the thread execution.

