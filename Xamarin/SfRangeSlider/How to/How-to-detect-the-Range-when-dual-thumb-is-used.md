---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to populate events in RangeSlider control
platform: xamarin
control: RangeSlider 
documentation: ug
---

# How to detect the Range when dual thumb is used?

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

{% tabs %}

{% highlight c# %}

	rangeSlider.RangeChanging+= (object sender, RangeEventArgs e) =>
			{
				float rangestart = e.Start;
				float rangeend = e.End;
				SfRangeSlider rangeSlider = e.RangeSlider;
			};	

{% endhighlight %}

{% endtabs %}
                                                

                                    
