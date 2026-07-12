---
tags: [api]
title: fyne.ScheduledNotification
slug: schedulednotification

aliases:
- /api//schedulednotification
- /api//schedulednotification.html
- /api/v2.0//schedulednotification
- /api/v2.0//schedulednotification.html
- /api/v2.1//schedulednotification
- /api/v2.1//schedulednotification.html
- /api/v2.2//schedulednotification
- /api/v2.2//schedulednotification.html
- /api/v2.3//schedulednotification
- /api/v2.3//schedulednotification.html
- /api/v2.4//schedulednotification
- /api/v2.4//schedulednotification.html
- /api/v2.5//schedulednotification
- /api/v2.5//schedulednotification.html
- /api/v2.6//schedulednotification
- /api/v2.6//schedulednotification.html
- /api/v2.7//schedulednotification
- /api/v2.7//schedulednotification.html

package: fyne.io/fyne/v2
---


---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type ScheduledNotification

```go
type ScheduledNotification struct {
	*Notification

	// DeliveryTime is the time at which the notification is scheduled to be delivered.
	DeliveryTime time.Time
}
```

ScheduledNotification represents a notification that has been queued for delivery at a future time. Instances are returned from [App.ScheduleNotification] and can be cancelled using the ID with [App.CancelScheduledNotification].


<div class="since">Since: <code>
2.8</code></div>

#### func  NewScheduledNotification

```go
func NewScheduledNotification(id string, n *Notification, deliverAt time.Time) *ScheduledNotification
```
NewScheduledNotification builds a scheduled notification record with a known ID. Application code should not normally call this directly - prefer [App.ScheduleNotification] which assigns an ID and arranges delivery.

This is exposed for use by app implementations and advanced testing.


<div class="since">Since: <code>
2.8</code></div>

#### func (*ScheduledNotification) Cancel

```go
func (s *ScheduledNotification) Cancel() error
```
Cancel will remove this scheduled notification from future posting. If your application might want to cancel a future notification after it has been restarted you should persist the `ID` value and then use `CancelScheduledNotification`.

#### func (*ScheduledNotification) ID

```go
func (s *ScheduledNotification) ID() string
```
ID returns the unique identifier for this scheduled notification. Pass this value to [App.CancelScheduledNotification] to cancel a pending delivery.
