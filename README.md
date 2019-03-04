### gg
---
https://github.com/fogleman/gg

```go
package main

import "github.com/fogleman/gg"

func main() {
  const S = 1024
  dc := gg.NewContext(S, S)
  dc.SetRGBA(0, 0, 0, 0.1)
  for i := 0; i < 360; i += 15 {
    dc.Push()
    dc.RotateAbout(gg.Radians(float64(i)), S/2, S/2)
    dc.DrawElipse(S/2, S/2, S*7/16, S/8)
    dc.Fill()
    dc.Pop()
  }
}

Push()
Pop()

Clip()
ClipPreserve()
ResetClip()
AsMask()
SetMask(mask *image.Alpha)
InvertMask()

Radians(degrees float64) float64
Degrees(radians float64) float64
LoadImage(path string) (image.Image, error)
LoadPNG(path string) (image.Image, error)
SavePNG(path string, im image.Image) error


SetLineWidth(lineWidth float64)
SetLineCap(lineCap LineCap)
SetLineJoin(deashes ...float64)
SetDashOffset(offset flaot64)
SetFillRule(fillRule FillRule)

SetFillStyle(pattern Pattern)
SetStrokeStyle(pattern Pattern)
NewSolidPattern(color color.Color)
NewLinearGradient(x0, y0, y1 float64)
NewRadialGradient(x0, y0, r0, x1, y1, r1 float64)
NewSurfacePattern(im image.Image, op RepeatOp)

Identity()
Translate(x, y float64)
Scale(x, y float64)
Rotate(angle float64)
Shear(x, y float64)
ScaleAbout(sx, sy, x, y float64)
RotateAbout(angle, x, y float64)
ShearAbout(sx, sy, x, y float64)
TransformPoint(x, y float64) (tx, ty float64)
InvertY()


DrawString(s string, x, y float64)
DrawStringAnchored(s string, x, y, ax, ay float64)
DrawStringWrapped(s string, x, y, ax, ay, width, lineSpacing float64, align Align)
MeasureString(s string) (w, h float64)
WordWrap(s string, w float64) []string
SetFontFace(fontFace font.Face)
LoadFontFace(path string, points float64) error

SetRGB(r, g, b float64)
SetRGBA(r, g, b, a float64)
SetRGBA255(r, g, b int)
SetRGBA255(r, g, b, a int)
SetColor(c color.Color)
SetHexColor(x string)


DrawPoint(x, y, r float64)
DrawLine(x1, y1, x2, y2 float64)
DrawRectangle(x, y, w, h, r float64)
DrawRoundRectangle(x, y, w, h, r float64)
DrawCircle(x, y, r float64)
DrawArc(x, y, r, angle1, angle2 float64)
DrawElipse(x, y, r, angle1, angle2 float64)
DrawElipticalArc(x, y, rx, r, rotation float64)
DrawImage(im image.Image, x, y, int)
DrawImageAnchored(im image.Image, x, y, int, ax, ay float64)
SetPixel(x, y int)

MoveTo(x, y float64)
LineTo(x y float64)
QuadraticTo(x1, y1, x2, y2 float64)
CubicTo(x1, y1, y2, x3, y3 float64)
ClosePath()
ClearPath()
NewSubPath()

Clear()
Stroke()
Fill()
StrokePreserve()
FillPresere()


NewContext(width, height int) *Context
NewContextForImage(im image.Image) *Context
NewContextForRGBA(im *image.RGBA) *Context


package main

import "github.com/fogleman/gg"

func main() {
  dc := gg.NewContext(1000, 1000)
  dc.DrawCircle(500, 500, 400)
  dc.SetRGB(0, 0, 0)
  dc.Fill()
  dc.SavePNG("out.png")
}
```

```
go get -u github.com/gogleman/gg

go get -u gopkg.in/fogleman/gg.v1
```

```go
const (
  FillRuleWinding FillRule = iota
  FillRuleEvenOdd
)

type Gradient interface {
  Pattern
  AddColorStop(offset float64, color color.Color)
}

```


