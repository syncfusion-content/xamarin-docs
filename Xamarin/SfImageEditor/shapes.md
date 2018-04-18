---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to add shapes, text, and draw over an Image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Shapes

You can annotate any path on an image by using free hand drawing, and adding shapes such as rectangle, circle, etc., over the image. The shapes can be added in following two ways:

* From Toolbar
* Using Code

## How to add a shape (Rectangle, Circle, Arrow, etc.) over an image

### From Toolbar

You can add the shapes from the toolbar by clicking the `Shapes` icon in the toolbar below the image. When the `Shapes` icon is tapped, a sub toolbar will appear on top of that toolbar. From that sub toolbar, you can choose the shape(`Rectangle`, `Circle`, and `Arrow`). Click the desired shape, and the shape will be added on the center of the image. The shapes has the handles on each edges, which helps you to resize it to the desired size, and  move it to the desired position by dragging the shape.

#### Change Color and Fill options of the shape

When the shape is clicked, the current toolbar menu with the shapes list will be hidden, and new menu with the options such as `Stroke`, `Fill`, and `Colors` will appear. The `Stroke` and `Fill` buttons will toggle the stroke, and fill option of the shapes whereas the colors menu will helps you to change the color of the shape.

I> By default, the shapes has `Red` stroke with `Transparent` fill.

### Using Code

The `AddShape` method in the SfImageEditor control is used to add the shapes based on the `ShapeType` and `PenSettings`.

#### ShapeType

ShapeType is an enum type with values `Rectangle`, `Circle`, `Arrow`, and `Path`.

#### PenSettings

PenSettings is defined to set the values for `StrokeColor`, `FillColor`, and `StrokeWidth`.

N> `FillColor` property is applicable only if the ShapeType is `Rectangle` or `Circle`, and `StrokeWidth` is used only for `Path`.

   * To add a rectangle, circle, or arrow over the image, specify the ShapeType as well as the desired PenSettings as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Circle, new PenSettings() {Color = Color.Red});

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

## How to delete a shape or text from the view

You can delete a selected shape or text from the view in the following two ways:

* From Toolbar
* Using Code

N> You cannot delete Path.

### From Toolbar

When a shape is selected, a circular floating button with `Delete` icon will appear above the bottom toolbar. Clicking the button will delete the selected shape from the view.

### Using Code

You can delete the selected shape programmatically by using the `Delete` method as shown in the following code snippet.


{% tabs %}

{% highlight C# %}

    editor.Delete();

{% endhighlight %}

{% endtabs %}
