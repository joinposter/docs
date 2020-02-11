## notificationClick: Click on a Popup Message

```javascript
Poster.on('notificationClick', (notification) => {
	console.log("Notification clicked", notification);
});
```

The event is triggered by clicking on a popup message. The notification can be shown using the [interface.showNotification](/en/docs/v3/pos/interfaces/interface-showNotification) method. As an argument, the `notification` object comes to the handler with the following parameters.

Parameter | Description
--------- | -----------
id | The new notification ID
date | Date of notification creation in milliseconds
title | Notification header
message | Notification message
icon | Application icon
status | Notification status: 0—not read, 1—output, but not read, 2—read
waiter | The ID of an employee the notification has been sent to

