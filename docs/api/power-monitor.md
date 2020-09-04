# powerMonitor

> Monitor power state changes.

Process: [Main](../glossary.md#main-process)

## Events

The `powerMonitor` module emits the following events:

### Event: 'suspend' _macOS_ _Windows_

Emitted when the system is suspending.

### Event: 'resume' _macOS_ _Windows_

Emitted when system is resuming.

### Event: 'on-ac' _macOS_ _Windows_

Emitted when the system changes to AC power.

### Event: 'on-battery' _macOS_  _Windows_

Emitted when system changes to battery power.

### Event: 'shutdown' _Linux_ _macOS_

Emitted when the system is about to reboot or shut down. If the event handler
invokes `e.preventDefault()`, Electron will attempt to delay system shutdown in
order for the app to exit cleanly. If `e.preventDefault()` is called, the app
should exit as soon as possible by calling something like `app.quit()`.

### Event: 'lock-screen' _macOS_ _Windows_

Emitted when the system is about to lock the screen.

### Event: 'unlock-screen' _macOS_ _Windows_

Emitted as soon as the systems screen is unlocked.

### Event: 'user-became-active' _macOS_

Emitted when a login session is activated. See [documentation](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPMultipleUsers/Concepts/UserSwitchNotifications.html#//apple_ref/doc/uid/20002210-CJBJDAGF) for more information.

### Event: 'user-became-inactive' _macOS_

Emitted when a login session is deactivated. See [documentation](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPMultipleUsers/Concepts/UserSwitchNotifications.html#//apple_ref/doc/uid/20002210-CJBJDAGF) for more information.

## Methods

The `powerMonitor` module has the following methods:

### `powerMonitor.getSystemIdleState(idleThreshold)`

* `idleThreshold` Integer

Returns `String` - The system's current state. Can be `active`, `idle`, `locked` or `unknown`.

Calculate the system idle state. `idleThreshold` is the amount of time (in seconds)
before considered idle.  `locked` is available on supported systems only.

### `powerMonitor.getSystemIdleTime()`

Returns `Integer` - Idle time in seconds

Calculate system idle time in seconds.
