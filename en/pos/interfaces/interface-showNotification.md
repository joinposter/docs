## interface.showNotification: Show a Popup Notification

> Request example:

```javascript
Poster.interface.showNotification({
    title: 'Online order',
    message: 'New order on 5th table',
    icon: 'https://joinposter.com/upload/apps/icons/posterboss-ios.png',
}).then((notification) => {
    console.log('new notification', notification);
});
```

The method displays a popup notification in the upper-right corner of the register. Clicking on the notification will trigger a [notificationClick](/en/docs/v3/pos/events/notificationClick) event.

### Arguments

Argument | Description
-------- | -----------
1st, notification | An object that contains the following notification parameters:

Parameter | Description
--------- | -----------
title | Notification header
message | Notification message
icon | Link to an application icon, for example, `https://joinposter.com/upload/apps/icons/posterboss-ios.png`
waiter | The ID of an employee to send a notification to. The notification will be available for all employees to see, but only this employee will see it in the list of notifications on My Notifications tab.

### Response

The function returns Promise, the result of which is an object with the following parameters

Parameter | Description
--------- | -----------
id | The new notification ID
date | Date of notification creation in milliseconds
title | Notification header
message | Notification message
icon | Application icon
status | Notification status: 0—not read, 1—output, but not read, 2—read
waiter | The ID of an employee the notification has been sent to

