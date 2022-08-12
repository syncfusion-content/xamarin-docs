---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to populate events in Syncfusion Essential Xamarin RangeSlider Control, its elements, and more.
platform: xamarin
control: RangeSlider 
documentation: ug
---

# How to Perform an Action while Selecting a Value?

[`ValueChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ValueChanging) event will be triggered when value is changed with single thumb. [`ValueEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueEventArgs.html) has [`RangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueEventArgs.html#Syncfusion_SfRangeSlider_XForms_ValueEventArgs_RangeSlider) and [`RangeValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.ValueEventArgs.html#Syncfusion_SfRangeSlider_XForms_ValueEventArgs_Value) of the control.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>RangeSlider</td>
<td>Displays the native control.</td>
</tr>
<tr>
<td>Value</td>
<td>Displays the value when moved with single thumb.</td>
</tr>
</table>


{% highlight c# %}

	rangeSlider.ValueChanging  += (object sender, ValueEventArgs e) => 
			{
				float range = e.Value;
				SfRangeSlider rangeSlider = e.RangeSlider;
			};
	

{% endhighlight %}



## How to Perform an Action when the Range Get Changing?

[`RangeChanging`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeChanging) event will be triggered when either [`RangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeStart) or [`RangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeEnd) values are changed. [`RangeEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.RangeEventArgs.html) has [`RangeStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeStart) and [`RangeEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_RangeEnd) value of [`SfRangeSlider`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html).

N> [`ShowRange`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ShowRange) value must be true.
<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>RangeSlider</td>
<td>Displays the native control</td>
</tr>
<tr>
<td>Start</td>
<td>It shows the start value when moved with thumb</td>
</tr>
<tr>
<td>End</td>
<td>It shows the end value when moved with thumb</td>
</tr>
</table>


{% highlight c# %}

	rangeSlider.RangeChanging+= (object sender, RangeEventArgs e) =>
			{
				float rangeStart = e.Start;
				float rangeEnd = e.End;
				SfRangeSlider rangeSlider = e.RangeSlider;
			};	

{% endhighlight %}


## How to get notifications when a thumb drag is started and completed?

The [`DragStarted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_DragStarted) event is raised when a thumb is dragged. After the thumb releases the pointer capture, the [`DragCompleted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_DragCompleted) event is raised. The [`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) property of the [`DragThumbEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html) returns a boolean value, which indicates the thumb used for performing drag operations.

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>IsStartThumb</td>
<td>Indicates the thumb used for performing drag operations.</td>
</tr>
</table>

                                                

{% highlight c# %}

	rangeSlider.DragStarted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

	rangeSlider.DragCompleted+=(object sender, DragThumbEventArgs e) =>
	{
         //perform the operation
	};

{% endhighlight %}

## How to trigger the ThumbTouchDown event?

The [`ThumbTouchDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ThumbTouchDown) event occurs when touching the thumb. The argument contains the state of the thumb.

[`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) - Gets the state whether thumb touch down position is start or end. If the thumb touch down position is start, then [`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) state is true. If it's end, then [`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) state is false. It is a read only property.

{% highlight c# %}
        private void Rangeslider_ThumbTouchDown(object sender, Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs e)
        {
          var isStartThumb =  e.IsStartThumb;
        }
{% endhighlight %}

## How to trigger the ThumbTouchUp event?

[`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) - Gets the state whether thumb touch up position is start or end. If the thumb touch up position is start, then [`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) state is true. If it's end, then [`IsStartThumb`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs.html#Syncfusion_SfRangeSlider_XForms_DragThumbEventArgs_IsStartThumb) state is false. It is a read only property.

{% highlight c# %}
        private void Rangeslider_ThumbTouchUp(object sender, Syncfusion.SfRangeSlider.XForms.DragThumbEventArgs e)
        {
          var isStartThumb=  e.IsStartThumb;
        }
{% endhighlight %}

N> [`ThumbTouchDown`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ThumbTouchDown) and [`ThumbTouchUp`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRangeSlider.XForms.SfRangeSlider.html#Syncfusion_SfRangeSlider_XForms_SfRangeSlider_ThumbTouchUp) events applicable only for Android, iOS platform and not for UWP.
