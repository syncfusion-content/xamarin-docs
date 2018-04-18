---
layout : post
title : Transformation in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to perform transformations in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Transformation

The image editor control can perform the image transformations such as `rotation` and `flip`. The transformations can be achieved in the following two ways:

* From Toolbar
* Using Code

## Rotation

### From Toolbar

You can rotate the image from the toolbar by clicking the `Rotate` button in the submenu of the `Transforms` button in the toolbar. Clicking the button results in rotating the image to 90 degrees clockwise from the current state.

### Using Code

Programmatically, you can make use of the `Rotate` method in the SfImageEditor control to rotate the image.

N> Angle cannot be specified in code to alter the rotation angle of the image.

{% tabs %}

{% highlight C# %}

editor.Rotate();

{% endhighlight %}

{% endtabs %}

## Flip

### From Toolbar

The Image Editor control can show the mirror image. You can get the mirror image of the loaded image by clicking the `Flip` button in the submenu of the `Transforms` button in the toolbar. Clicking the button results in the image being flipped horizontally.

### Using Code

The `Flip` method flips the image horizontally or vertically based on the `FlipDirection` specified as argument for the Flip method.

N> The default flip direction is horizontal.

{% tabs %}

{% highlight C# %}

editor.Flip(FlipDirection.Horizontal);

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Flip.gif)