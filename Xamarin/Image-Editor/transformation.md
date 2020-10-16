---
layout: post
title: Transformation in Syncfusion SfImageEditor control in Xamarin.Forms
description: Learn how to perform transformations such as rotation and flip in SfImageEditor control for Xamarin.Forms
platform: xamarin.forms
control: ImageEditor
documentation: ug
---

# Transformation in SfImageEditor

The image editor control is capable of performing the image transformations such as `rotation` and `flip`.

## Rotation

You can use the [`Rotate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Rotate) method of the image editor to rotate a image. For each rotation, image will be rotated to 90 degrees towards clockwise direction.

N> Angle cannot be specified in code to alter the rotation angle of the image.

{% tabs %}

{% highlight C# %}

editor.Rotate();

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/rotate.jpeg)

## Flip

The image editor control is capable of showing the mirror image. The [`Flip`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Flip_Syncfusion_SfImageEditor_XForms_FlipDirection_) method flips the image horizontally or vertically based on the [`FlipDirection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.FlipDirection.html) specified as argument of the flip method.

N> The default flip direction is horizontal.

{% tabs %}

{% highlight C# %}

editor.Flip(FlipDirection.Horizontal);

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/flip.jpeg)

## See also

[How to resolve image rotated when loading image / after saving image in iOS device](https://www.syncfusion.com/kb/9632/how-to-resolve-image-rotated-when-loading-image-after-saving-image-in-ios-device)
