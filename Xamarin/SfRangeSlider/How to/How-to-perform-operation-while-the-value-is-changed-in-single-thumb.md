---
layout: post
title: Events in Syncfusion RangeSlider control for Xamarin.Forms
description: Learn how to populate events in RangeSlider control
platform: xamarin
control: RangeSlider 
documentation: ug
---

# How to perform operation while the value is changed in single thumb?

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

{% tabs %}

{% highlight c# %}

	rangeSlider.ValueChanging  += (object sender, ValueEventArgs e) => 
			{
				float range = e.Value;
				SfRangeSlider rangeSlider = e.RangeSlider;
			};
	

{% endhighlight %}

{% endtabs %}

                           

                                    
