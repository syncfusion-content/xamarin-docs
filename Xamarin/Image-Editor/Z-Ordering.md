---
layout: post
title: Z-Ordering in Xamarin Image Editor control | Syncfusion
description: Learn here all about Z-Ordering support in Syncfusion Xamarin Image Editor (SfImageEditor) control and more.
platform: xamarin
control: ImageEditor
documentation: ug
---

# Z-Ordering in Xamarin Image Editor (SfImageEditor)

The image editor control allows to change the position of shapes/edits that are arranged over the editor. This can be achieved using the following methods:

1. BringToFront
2. SendToBack
3. BringForward
4. SendBackward

## BringToFront

The [`BringToFront`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_BringToFront) method is used to bring the selected shapes/text to the front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## SendToBack

The [`SendToBack`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_SendToBack) method is used to send the selected shapes/text to the back of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendToBack();

{% endhighlight %}

{% endtabs %}

## BringForward

The [`BringForward`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_BringForward) method is used to bring the selected shapes/text to one step front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringForward();

{% endhighlight %}

{% endtabs %}

## SendBackward

The [`SendBackward`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_SendBackward) method is used to send the selected shapes/text to one step backward of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendBackward();

{% endhighlight %}

{% endtabs %}

