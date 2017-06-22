---
layout : post
title : Transformation in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to perform transformations in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Transformation

The image editor control is capable of performing the image transformations such as `rotation` and `flip`. The transformations can be achieved in two ways:

* From Toolbar
* Using Code

## Rotation

### From Toolbar

You can rotate the image from the toolbar by clicking on the `Rotate` button available in the submenu of the `Transforms` button in the toolbar. The button click results in rotating the image to 90 degrees clockwise from the current state.

### Using Code

Programmatically, you can make use of the `Rotate` method in the SfImageEditor control to rotate the image.

N> Angle cannot be specified in code to alter the rotation angle of the image

{% tabs %}

{% highlight C# %}

editor.Rotate();

{% endhighlight %}

{% endtabs %}



## Flip

### From Toolbar

The Image Editor control has the capability of showing the mirror image. You can get the mirror image of the loaded image by clicking on the `Flip` button available in the submenu of the `Transforms` button in the toolbar. The button click results in the image being flipped horizontally.

### Using Code

The `Flip` method flips the image horizontally or vertically based on the `FlipDirection` specified as argument for the Flip method.

N> The default flip direction is horizontal.

{% tabs %}

{% highlight C# %}

editor.Flip(FlipDirection.Horizontal);

{% endhighlight %}

{% endtabs %}

