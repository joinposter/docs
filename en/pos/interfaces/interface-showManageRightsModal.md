## interface.showManageRightsModal: Show Admin password Modal Window

> Request example: 
```javascript
Poster.interface.showManageRightsModal({
  askRights: true,
  enableLogging: false,
})
```

The method displays an admin password modal window. Used to confirm dangerous actions.

### Arguments

An argument is an object with the parameters:

Argument | Description
-------- | --------
askRights | true — show modal window, false — do not show
enableLogging | always false

### Response

The function returns Promise with result of a request