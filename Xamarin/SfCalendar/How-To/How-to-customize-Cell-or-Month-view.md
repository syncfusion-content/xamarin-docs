---
layout: post
title: Interactive Selection modes in Syncfusion Calendar control for Xamarin.Forms
description: How to customize Cell or Month view
platform: Xamarin
control: Calendar
documentation: ug
---

# How to customize Cell or Month view?

`OnMonthCellLoaded` event allows us to customize calendar control. It returns MonthCell args

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>Args</td>
<td>Carries details about MonthCell</td>
</tr>
</table>

{% highlight c# %}

	sfcalendar.OnMonthCellLoaded += (object sender, Syncfusion.SfCalendar.XForms.MonthCell args) =>
	{
			if ((args.Date.DayOfWeek == DayOfWeek.Sunday || args.Date.DayOfWeek == DayOfWeek.Saturday))
			{
				args.BackgroundColor = Color.Gray;
				args.TextColor = Color.Red;
			}
	};
{% endhighlight %}