---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to populate events in RangeSlider control
platform: xamarin
control: RangeSlider 
documentation: ug
---

## How to Perform an Action while Selecting a Value?

ValueChanging event will be triggered when value is changed with single thumb. ValueEventArgs has RangeSlider and RangeValue of the control.

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

RangeChanging event will be triggered when either RangeStart or RangeEnd values are changed. RangeEventArgs has RangeStart and RangeEnd value of SfRangeSlider.

N> `ShowRange` value must be true.
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

The `DragStarted` event is raised when a thumb is dragged. After the thumb releases the pointer capture, the `DragCompleted` event is raised. The `IsStartThumb` property of the `DragThumbEventArgs` returns a boolean value, which indicates the thumb used for performing drag operations.

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

                                    
