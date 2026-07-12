---
tags: [api]
title: fyne.Cache
slug: cache

aliases:
- /api//cache
- /api//cache.html
- /api/v2.0//cache
- /api/v2.0//cache.html
- /api/v2.1//cache
- /api/v2.1//cache.html
- /api/v2.2//cache
- /api/v2.2//cache.html
- /api/v2.3//cache
- /api/v2.3//cache.html
- /api/v2.4//cache
- /api/v2.4//cache.html
- /api/v2.5//cache
- /api/v2.5//cache.html
- /api/v2.6//cache
- /api/v2.6//cache.html
- /api/v2.7//cache
- /api/v2.7//cache.html

package: fyne.io/fyne/v2
---


---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type Cache

```go
type Cache interface {
	RootURI() URI

	Exists(name string) bool
	Read(name string) (io.ReadCloser, error)
	Write(name string) (io.WriteCloser, error)
	Remove(name string) error
}
```

Cache is used to manage cache storage inside an application sandbox. The files managed by this interface are unique to the current application and may be deleted by the operating system to clear space


<div class="since">Since: <code>
2.8</code></div>
