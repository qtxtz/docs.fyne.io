---
tags: [api]
title: fyne.AccessibleRole
slug: accessiblerole

aliases:
- /api//accessiblerole
- /api//accessiblerole.html
- /api/v2.0//accessiblerole
- /api/v2.0//accessiblerole.html
- /api/v2.1//accessiblerole
- /api/v2.1//accessiblerole.html
- /api/v2.2//accessiblerole
- /api/v2.2//accessiblerole.html
- /api/v2.3//accessiblerole
- /api/v2.3//accessiblerole.html
- /api/v2.4//accessiblerole
- /api/v2.4//accessiblerole.html
- /api/v2.5//accessiblerole
- /api/v2.5//accessiblerole.html
- /api/v2.6//accessiblerole
- /api/v2.6//accessiblerole.html
- /api/v2.7//accessiblerole
- /api/v2.7//accessiblerole.html

package: fyne.io/fyne/v2
---


---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type AccessibleRole

```go
type AccessibleRole string
```

AccessibleRole describes the different roles an accessible element can take.


<div class="since">Since: <code>
2.8</code></div>

```go
const (
	AccessibleRoleButton    AccessibleRole = "button"
	AccessibleRoleContainer AccessibleRole = "container"
	AccessibleRoleLink      AccessibleRole = "link"
	AccessibleRoleText      AccessibleRole = "text"
)
```
