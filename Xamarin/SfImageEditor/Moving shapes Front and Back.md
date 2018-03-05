---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to move shapes in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Moving shapes Front and Back

ImageEditor allow us to change the position of shapes/Edits which are arranged over the editor. This can be achieved with the help of following methods. 

1)BringToFront
2)SendToBack
3)BringForward
4)SendToBackward

# BringToFront

You can bring the desired shape into front over the all shapes by calling BringToFront method in SfImageEditor control.

{% tabs %}

{% highlight C# %}

   editor.BringToFront();

{% endhighlight %}

{% endtabs %}

## SendToBack

You can send the desired shape into back over the all shapes by calling SendToBack method in SfImageEditor control.

{% tabs %}

{% highlight C# %}

   editor.SendToBack();

{% endhighlight %}

{% endtabs %}

### BringForward

You can bring the desired shape into forward by one step over the all shapes by calling BringToForward method in SfImageEditor control.

{% tabs %}

{% highlight C# %}

   editor.BringForward();

{% endhighlight %}

{% endtabs %}

#### SendToBackward

You can send the desired shape into backward by one step over the all shapes by calling SendToBackward method in SfImageEditor control.

{% tabs %}

{% highlight C# %}

   editor.SendToBackward();

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/BringToFront.gif)