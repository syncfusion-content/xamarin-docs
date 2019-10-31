---
layout: post
title: Auto scrolling the Syncfusion segmented control for Xamarin.Forms
description: Learn how to auto scroll the selected index in the segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Autoscrolling the selected segment item

Auto scrolling for selected item change can be enabled by setting the value of [`AutoScrollSelectedItem`]() property to true. You can set the scroll position of segment item using the [`ScrollToPosition`]() property. The default value for [`AutoScrollSelectedItem`]() is false, and the default value for [`ScrollToPosition`]() is [`MakeVisible`](). The following options are available in [`ScrollToPosition`]():
	
* [`MakeVisible`]() -  Scrolls to the selected segment item to make it visible in the control. If the item is already visible, scrolling will not occur.
* [`Start`]() -  Scrolls to the selected segment item at the start of the control.
* [`Center`]() - Scrolls to the selected segment item at the center of the control.
* [`End`]() - Scrolls to selected segment item at the end of the control.

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl x:Name = "segmentedControl" SelectedIndex="5" AutoScrollSelectedItem="True" ScrollToPosition="Center"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectedIndex = 5;

segmentedControl.AutoScrollSelectedItem = true;

segmentedControl.ScrollToPosition = Syncfusion.XForms.Buttons.ScrollToPosition.Center;

{% endhighlight %}

{% endtabs %}
