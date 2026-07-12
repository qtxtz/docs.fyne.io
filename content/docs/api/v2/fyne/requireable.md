---
tags: [api]
title: fyne.Requireable
slug: requireable

aliases:
- /api//requireable
- /api//requireable.html
- /api/v2.0//requireable
- /api/v2.0//requireable.html
- /api/v2.1//requireable
- /api/v2.1//requireable.html
- /api/v2.2//requireable
- /api/v2.2//requireable.html
- /api/v2.3//requireable
- /api/v2.3//requireable.html
- /api/v2.4//requireable
- /api/v2.4//requireable.html
- /api/v2.5//requireable
- /api/v2.5//requireable.html
- /api/v2.6//requireable
- /api/v2.6//requireable.html
- /api/v2.7//requireable
- /api/v2.7//requireable.html

package: fyne.io/fyne/v2
---


---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type Requireable

```go
type Requireable interface {
	HasValue() bool

	// SetOnRequiredChanged is used to set the callback that will be triggered when the required state changes.
	// The function might be overwritten by a parent that cares about child validation (e.g. widget.Form).
	SetOnRequiredChanged(func(bool))
}
```

Requireable is implemented by any widgets that want to support the [Required] field of a [FormItem]


<div class="since">Since: <code>
2.8</code></div>
