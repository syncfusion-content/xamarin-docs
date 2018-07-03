---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to move shapes in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Moving shapes Front and Back

ImageEditor allows us to change the position of shapes/Edits which are arranged over the editor. This can be achieved with the help of following methods. 

1)BringToFront
2)SendToBack
3)BringForward
4)SendToBackward

## BringToFront

BringToFront is a method which is used to bring the selected shapes/text to the front of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## SendToBack

SendToBack is a method which is used to Send the selected shapes/text to the back of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendToBack();

{% endhighlight %}

{% endtabs %}

## BringForward

BringForward is a method which is used to bring the selected shapes/text to one step front of a group of elements over an image

{% tabs %}

{% highlight C# %}

   editor.BringForward();

{% endhighlight %}

{% endtabs %}

## SendToBackward

SendToBackward is a method which is used to send the selected shapes/text to one step backward of a group of elements over an image.

{% tabs %}

{% highlight C# %}

   editor.SendToBackward();

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/BringToFront.gif)