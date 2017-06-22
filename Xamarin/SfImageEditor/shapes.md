---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to add shapes, text and draw over an Image in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Shapes

You can annotate any path on an image using free hand drawing and add texts, shapes like rectangle, circle over the image. The shapes and text can be added in two ways:

* From Toolbar
* Using Code

## How to add a shape (Rectangle, Circle) over an image

### From Toolbar

You can add the shapes from the toolbar by clicking on the `Shapes` icon available in the toolbar below the image. When the `Shapes` icon is touched, a sub toolbar will appear on top of that toolbar from which we can choose either `Rectangle` or `Circle`. Click on the desired shape and the shape will be added on the center of the image. The shape will have the handles on each edges of the shape which help in resizing it to the desired size and you can move it to the desired position by dragging the shape.

#### Change Color and Fill Options of the Shape

While you click on a shape, the current toolbar menu with the shapes list will be hidden and new menu with the options such as `Stroke`, `Fill` and `Colors` will be appear. The `Stroke` and `Fill` buttons will toggle the stroke and fill option of the shapes whereas the colors menu will help to change the color of the shape.

I> By default, the shape will have `Red` stroke with `Transparent` fill.

### Using Code

The `AddShape` method in the SfImageEditor control is used to add shapes based on the `ShapeType` and `PenSettings`.

#### ShapeType

ShapeType is an enum type with values `Rectangle`, `Circle`, `Text` and `Path`.

#### PenSettings

PenSettings is defined to set the values for `StrokeColor`, `FillColor` and `StrokeWidth`.

N> FillColor property is applicable only if the ShapeType is `Rectangle` or `Circle` and `StrokeWidth` only used for `Path`.

To add a rectangle or a circle over the image, you need to specify the ShapeType as well as the desired PenSettings as in the below code snippet:

{% tabs %}

{% highlight C# %}

editor.AddShape(ShapeType.Circle, new PenSettings() {StrokeColor = Color.Red});

{% endhighlight %}

{% endtabs %}



## How to add text over the Image

### From Toolbar

You can add text from the toolbar by clicking on the `Text` icon available in the toolbar below the image. When the `Text` icon is touched, an editor will appear along with the soft keyboard. Type the desired text and click on `Accept` or `return` button of the keyboard or hide the keyboard using the `down` arrow soft button or `back` hard key or clicking on the image to lose focus. This will place the text on the center of the image. You can move the text to the desired place by dragging the text.

#### Change Color of the selected Text

To change the color of the selected text, select the desired text and click on the color buttons available in the sub menu.

### Using Code

You can also add the desired text elements over the image from the code programmatically. The `AddText` method in the SfImageEditor control is used to add text based on the string value and `TextSettings`.

N> The `Text` cannot be resized.

#### TextSettings

TextSettings is defined to set the values for `Color` and `FontSize`.


{% tabs %}

{% highlight C# %}

editor.AddText("New Text", new TextSettings(){Color = Color.Green, FontSize = 16d});

{% endhighlight %}

{% endtabs %}



## How to delete a shape or text from the view

You can delete a selected shape or text from the view in two ways:

* From Toolbar
* Using Code

### From Toolbar

When a shape is selected, a circular floating button with `Delete` icon will appear above the bottom toolbars. Clicking on the button will delete the selected shape from the view.

### Using Code

You can delete the selected shape programmatically using the `Delete` method as like in below code snippet:

{% tabs %}

{% highlight C# %}

editor.Delete();

{% endhighlight %}

{% endtabs %}
