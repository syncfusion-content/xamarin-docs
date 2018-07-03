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

## Adding shapes (Rectangle, Circle, Arrow, etc.) over an image

### From Toolbar

You can add the shapes from the toolbar over an image by clicking the toolbar `Shapes` icon. When tapping the `Shapes` icon, a sub toolbar will appear on top of that toolbar. From that sub toolbar, you can choose the desired shape(`Rectangle`, `Circle`, and `Arrow`). Click the desired shape, and the shape will be added on the center of the image. Added shape will contains the handle on each edges, which helps you to resize it to the desired size, and  move it to the desired position by dragging the shape.

#### Change Color and Fill options of the shape

When the shape is clicked, the current toolbar menu with the shapes list will be hidden, and new menu with the options such as `Stroke`, `Fill`, and `Colors` will appear. 

If the selected shape is in `Stroke` mode, then the menu will appear with `StrokeThickness`, `Color` and `Opacity` options so that you can customize the selected shape appearance with these options. 

If the selected shape is in `Fill` mode, then the menu will appear with `FillColor` and `Opacity` options. So, you can customize the selected shape appearance with these options. 

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

#### Bounds

`Bounds` property allows you to set frame for the newly added shapes(rectangle and circle) and you can position the shapes wherever you want on the image. The value of the shapes frame should be in percentage(maximum - 100 & minimum - 0).

{% highlight C# %}

  edit.AddShape(ShapeType.Circle, new PenSettings() { Bounds = new Rectangle(20,20,35,35) });

{% endhighlight %}

![SfImageEditor](ImageEditor_images/path.gif)

## Deleting the shape or text from the view

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
