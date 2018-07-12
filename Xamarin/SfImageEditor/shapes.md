---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to add shapes, text, and draw over an Image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

## Shapes

You can annotate any shapes over an image with the help of `AddShape` method. The list of available shapes are,

* Circle
* Rectangle
* Arrow
* Path

### Selecting shape type

`ShapeType` is an enum type with values `Rectangle`, `Circle`, `Arrow`, and `Path`. You can give the desired shape type as an argument to the AddShape method.

{% highlight C# %}

      editor.AddShape(ShapeType.Circle);

{% endhighlight %}

## Customize shapes with pen settings

You can customize the appearance of each shape with the help of `PenSettings` properties.

## PenSettings

PenSettings consist of the following properties,

[`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~Color.html) - You can specify desired stroke color to the shape.

[`FillColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~FillColor.html) - You can specify desired fill color to the shape.

[`StrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~StrokeWidth.html) - This allows to denote the stroke width for the desired shape.

[`Mode`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~Mode.html) - Enum value which decides whether the shape color mode is `Fill` or `Stroke`

[`Opacity`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~Opacity.html) - Denotes the opacity for the desired shapes.

[`Bounds`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.PenSettings~Bounds.html) - This property allows you to set frame for the newly added shapes(rectangle and circle) and you can position the shapes wherever you want on the image. The value of the shape frame should be ranges from 0 to 100.

N> `FillColor` property is applicable only if the ShapeType is `Rectangle` or `Circle`.

   * To add a rectangle, circle, or arrow over an image, specify the ShapeType as well as the desired PenSettings as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Circle, new PenSettings() {Color = Color.Red, Mode= Mode.Stroke, Opacity=1f, Bounds = new Rectangle(20,20,35,35)});

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Shapes.gif)

   * You can annotate any path on an image by using free hand drawing as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Path, new PenSettings() { StrokeWidth = 10 });

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/path.gif)

## Deleting the shape or text from the view

You can delete the selected shape by using the `Delete` method as shown in the following code snippet.


{% tabs %}

{% highlight C# %}

    editor.Delete();

{% endhighlight %}

{% endtabs %}

N>You cannot delete Path.


