---
layout: post
title: Select the Range of SfDateTimeRangeNavigator
description: Selecting Range
platform: xamarin
control: SfDateTimeRangeNavigator
documentation: ug
---

# Selecting Range

The left and right thumb of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) are used to indicate the selected range in the large collection of data. Following are the ways you can select a range.

* By dragging the thumbs.
* By tapping on the minor and major labels.
* By setting the [`ViewRangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeStartDate) and [`ViewRangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeEndDate) properties.

Following code example shows how to configure the selected range using [`ViewRangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeStartDate) and [`ViewRangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeEndDate) properties of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html).

{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator x:Name ="dateTime" Minimum="1/1/2015" 
	Maximum="1/1/2017" ViewRangeStart="5/1/2015" ViewRangeEnd="10/1/2016"/>
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator(); 

dateTime.ViewRangeStart = new DateTime(2015, 5, 1);

dateTime.ViewRangeEnd = new DateTime(2016, 10, 1);
{% endhighlight %}
{% endtabs %}

![](range_images/range_img1.png)

## Selected Data

The [`SelectedData`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_SelectedData) property of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) used to get the underlying data collection of the selected range. You can directly bind this property to other data visualization control to visualize the selected range of data.

## Overlay Color

The [`OverlayColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_OverlayColor) property of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) is used to customize the color of unselected area in date-time range navigator.

## Deferred Update

[`RangeChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) event will be fired whenever you drag the thumbs. If you are doing some long running tasks in this event handler, then dragging the thumbs will not be smooth. You can delay this event by enabling [`EnableDeferredUpdate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_EnableDeferredUpdate) property. If this property is set to true, the [`RangeChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) event will get fired only when you stop dragging or if the thumb is held for more than 500 milliseconds. If it is false, the range will be updated for every movement of the thumb. However, It is true by default.

The delay of update is 500 milliseconds by default. However, it can be changed using [`DeferredUpdateDelay`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html#Syncfusion_RangeNavigator_XForms_SfDateTimeRangeNavigator_DeferredUpdateDelay) property of [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html).

{% tabs %}
{% highlight xaml %}
<rangenavigator:SfDateTimeRangeNavigator x:Name ="dateTime" Minimum="1/1/2015" 
	Maximum="1/1/2017" EnableDeferredUpdate="False" DeferredUpdateDelay="600" />
{% endhighlight %}

{% highlight c# %}
SfDateTimeRangeNavigator dateTime = new SfDateTimeRangeNavigator(); 

dateTime.EnableDeferredUpdate = false;

dateTime.DeferredUpdateDelay = 600;
{% endhighlight %}
{% endtabs %}

## RangeChanged Event

This event is triggered when the selected range of the [`SfDateTimeRangeNavigator`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.SfDateTimeRangeNavigator.html) is changed. The argument contains the following information.

* [`ViewRangeStartDate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeStartDate) – used to get the start date of the selected range.
* [`ViewRangeEndDate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.RangeNavigator.XForms.RangeChangedEventArgs.html#Syncfusion_RangeNavigator_XForms_RangeChangedEventArgs_ViewRangeEndDate) – used to get the end date of the selected range.