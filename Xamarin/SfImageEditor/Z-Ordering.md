---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to move shapes in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Moving shapes to front and back

The image editor control allows to change the position of shapes/edits that are arranged over the editor. This can be achieved using the following methods:

1. BringToFront
2. SendToBack
3. BringForward
4. SendBackward

## BringToFront

The BringToFront method is used to bring the selected shapes/text to the front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## SendToBack

The SendToBack method is used to send the selected shapes/text to the back of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendToBack();

{% endhighlight %}

{% endtabs %}

## BringForward

The BringForward method is used to bring the selected shapes/text to one step front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringForward();

{% endhighlight %}

{% endtabs %}

## SendBackward

The SendBackward method is used to send the selected shapes/text to one step backward of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendBackward();

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/BringToFront.gif)
