---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to populate events in RangeSlider control
platform: Xamarin.Forms
control: RangeSlider 
documentation: ug
---

# RangeSlider Events

The events of the RangeSlider control are as follows.

<table>
<tr>
<th>RangeSlider Events</th>
<th>Description</th>
</tr>
<tr>
<td>ValueChanging</td>
<td>Triggered when value changed with single thumb.</td>
</tr>
<tr>
<td>RangeChanging</td>
<td>Triggered when either RangeStart or RangeEnd changed when ShowRange is true.</td>
</tr>
</table>


## ValueChanging

Triggered when value changed with single thumb.

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

{% tabs %}

{% highlight c# %}

	sfRangeSlider.ValueChanging  += (object sender, ValueEventArgs e) => 
			{
				float range = e.Value;
				SfRangeSlider rangeslider = e.RangeSlider;
			};
	

{% endhighlight %}

{% endtabs %}

## RangeChanging

Triggered when either RangeStart or RangeEnd changed when ShowRange is true.

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

{% tabs %}

{% highlight c# %}

	sfRangeSlider.RangeChanging+= (object sender, RangeEventArgs e) =>
			{
				float rangestart = e.Start;
				float rangeend = e.End;
				SfRangeSlider rangeslider = e.RangeSlider;
			};	

{% endhighlight %}

{% endtabs %}
                                                

                                    
