---
tags: [api]
title: driver.Painter
slug: painter

aliases:
- /api/driver/painter
- /api/driver/painter.html
- /api/v2.0/driver/painter
- /api/v2.0/driver/painter.html
- /api/v2.1/driver/painter
- /api/v2.1/driver/painter.html
- /api/v2.2/driver/painter
- /api/v2.2/driver/painter.html
- /api/v2.3/driver/painter
- /api/v2.3/driver/painter.html
- /api/v2.4/driver/painter
- /api/v2.4/driver/painter.html
- /api/v2.5/driver/painter
- /api/v2.5/driver/painter.html
- /api/v2.6/driver/painter
- /api/v2.6/driver/painter.html
- /api/v2.7/driver/painter
- /api/v2.7/driver/painter.html

package: fyne.io/fyne/v2/driver
---


---
```go
import "fyne.io/fyne/v2/driver"
```

## Usage

#### type Painter

```go
type Painter interface {
	Paint(fyne.Canvas) image.Image
}
```

Painter describes a simple type that can render canvases


<div class="since">Since: <code>
2.9</code></div>
