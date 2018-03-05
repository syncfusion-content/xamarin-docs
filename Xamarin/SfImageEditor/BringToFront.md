---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to move shapes in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

We already have support to annotate shapes like rectangle, circle & arrow. These shapes arrange one over the other in chronological order when we add it
to the image so there will be a need to change this order while customizing the edits you can bring the required shape to front or back as desire.

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