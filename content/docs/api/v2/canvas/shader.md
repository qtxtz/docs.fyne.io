---
tags: [api]
title: canvas.Shader
slug: shader

aliases:
- /api/canvas/shader
- /api/canvas/shader.html
- /api/v2.0/canvas/shader
- /api/v2.0/canvas/shader.html
- /api/v2.1/canvas/shader
- /api/v2.1/canvas/shader.html
- /api/v2.2/canvas/shader
- /api/v2.2/canvas/shader.html
- /api/v2.3/canvas/shader
- /api/v2.3/canvas/shader.html
- /api/v2.4/canvas/shader
- /api/v2.4/canvas/shader.html
- /api/v2.5/canvas/shader
- /api/v2.5/canvas/shader.html
- /api/v2.6/canvas/shader
- /api/v2.6/canvas/shader.html
- /api/v2.7/canvas/shader
- /api/v2.7/canvas/shader.html

package: fyne.io/fyne/v2/canvas
---


---
```go
import "fyne.io/fyne/v2/canvas"
```

## Usage

#### type Shader

```go
type Shader struct {

	// Name identifies this shader. Shaders that share a Name may share a
	// compiled program, so it should be unique per distinct shader source.
	Name string

	// Source is the GLSL fragment shader used on desktop OpenGL (core profile).
	Source []byte

	// SourceES is the GLSL fragment shader used on OpenGL ES, mobile and web.
	SourceES []byte

	// Textures supplies named images to the shader. Each entry is uploaded to
	// the GPU and exposed to the fragment shader as a "uniform sampler2D <name>".
	// Images are uploaded once and reused; replacing an entry with a different
	// image updates the GPU copy on the next paint, so static textures cost
	// nothing per frame.
	Textures map[string]image.Image

	// Uniforms supplies named scalar values to the shader, each exposed to the
	// fragment shader as a "uniform float <name>". They are applied every paint,
	// so an application can drive a shader's parameters - for example animating a
	// transition - by updating an entry and calling Refresh. The "time" entry is
	// supplied by NewShaderAnimation while a shader is animating; setting it
	// directly lets a static shader pick an arbitrary frame.
	Uniforms map[string]float32
}
```

Shader describes a canvas object that is drawn using a custom GLSL fragment shader. The shader is rendered inside the object's bounds, respecting the position and size set on it just like any other canvas primitive.

The supplied fragment shader must follow the same conventions as Fyne's internal vector shaders. It is provided with the following uniforms:

```go
    uniform vec2 frame;   // the size of the output frame, in pixels
    uniform vec4 bounds;  // this object's bounds (x1, y1, x2, y2), in pixels
    uniform float time;   // elapsed animation time in seconds (see NewShaderAnimation)
```

and should compute its color from gl_FragCoord, as the built-in shapes do. Any images set in Textures are additionally exposed as "uniform sampler2D" values, and any values in Uniforms as "uniform float", named by their map key.

Two source variants are held so that the object renders on both desktop OpenGL (core profile) and OpenGL ES / mobile / web targets.


<div class="since">Since: <code>
2.8</code></div>

#### func  NewShader

```go
func NewShader(name string, source, sourceES []byte) *Shader
```
NewShader returns a new Shader instance using the specified fragment shader sources. The name should uniquely identify the shader, source is used on desktop (OpenGL core profile) and sourceES is used on mobile and web targets.


<div class="since">Since: <code>
2.8</code></div>

#### func (*Shader) Hide

```go
func (s *Shader) Hide()
```
Hide will set this shader to not be visible.

#### func (*Shader) MinSize

```go
func (o *Shader) MinSize() fyne.Size
```
MinSize returns the specified minimum size, if set, or {1, 1} otherwise.

#### func (*Shader) Move

```go
func (s *Shader) Move(pos fyne.Position)
```
Move the shader object to a new position, relative to its parent / canvas.

#### func (*Shader) Position

```go
func (o *Shader) Position() fyne.Position
```
Position gets the current position of this canvas object, relative to its parent.

#### func (*Shader) Refresh

```go
func (s *Shader) Refresh()
```
Refresh causes this shader to be redrawn with its current state.

#### func (*Shader) Resize

```go
func (s *Shader) Resize(size fyne.Size)
```
Resize on a shader updates the new size of this object.

#### func (*Shader) SetMinSize

```go
func (o *Shader) SetMinSize(size fyne.Size)
```
SetMinSize specifies the smallest size this object should be.

#### func (*Shader) Show

```go
func (o *Shader) Show()
```
Show will set this object to be visible.

#### func (*Shader) Size

```go
func (o *Shader) Size() fyne.Size
```
Size returns the current size of this canvas object.

#### func (*Shader) Visible

```go
func (o *Shader) Visible() bool
```
Visible returns true if this object is visible, false otherwise.
