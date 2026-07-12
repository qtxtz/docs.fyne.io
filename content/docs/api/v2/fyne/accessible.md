---
tags: [api]
title: fyne.Accessible
slug: accessible

aliases:
- /api//accessible
- /api//accessible.html
- /api/v2.0//accessible
- /api/v2.0//accessible.html
- /api/v2.1//accessible
- /api/v2.1//accessible.html
- /api/v2.2//accessible
- /api/v2.2//accessible.html
- /api/v2.3//accessible
- /api/v2.3//accessible.html
- /api/v2.4//accessible
- /api/v2.4//accessible.html
- /api/v2.5//accessible
- /api/v2.5//accessible.html
- /api/v2.6//accessible
- /api/v2.6//accessible.html
- /api/v2.7//accessible
- /api/v2.7//accessible.html

package: fyne.io/fyne/v2
---


---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type Accessible

```go
type Accessible interface {
	AccessibilityLabel() string
	AccessibilityRole() AccessibleRole
}
```

Accessible interface should be implemented for a widget that should be accessible


<div class="since">Since: <code>
2.8</code></div>
