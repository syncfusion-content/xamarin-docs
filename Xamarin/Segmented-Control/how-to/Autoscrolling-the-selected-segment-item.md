---
layout: post
title: Auto Scrolling in the Syncfusion Segmented Control for Xamarin.Forms
description: Learn how to enable automatic scrolling for the selected index in the Syncfusion segmented control (SfSegmentedControl) for Xamarin.Forms.
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Auto Scrolling the Selected Segment Item

Enable automatic scrolling for the selected item by setting the [`AutoScrollSelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_AutoScrollSelectedItem) property to true. Define the scroll position of the segment item using the [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollToPosition) property. By default, [`AutoScrollSelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_AutoScrollSelectedItem) is set to false, and [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollToPosition) defaults to [`MakeVisible`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ScrollToPosition.html#Syncfusion_XForms_Buttons_ScrollToPosition_MakeVisible). Available options for [`ScrollToPosition`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_ScrollToPosition) include:
	
- [`MakeVisible`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ScrollToPosition.html#Syncfusion_XForms_Buttons_ScrollToPosition_MakeVisible): Scrolls the selected segment item to ensure visibility within the control. If the item is already visible, no scrolling occurs.
- [`Start`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ScrollToPosition.html#Syncfusion_XForms_Buttons_ScrollToPosition_Start): Scrolls the selected segment item to the start of the control.
- [`Center`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ScrollToPosition.html#Syncfusion_XForms_Buttons_ScrollToPosition_Center): Centers the selected segment item within the control.
- [`End`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.ScrollToPosition.html#Syncfusion_XForms_Buttons_ScrollToPosition_End): Scrolls the selected segment item to the end of the control.

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
