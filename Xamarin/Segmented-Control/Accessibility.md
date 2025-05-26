---
layout: post
title: Accessibility in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Explore comprehensive details about the accessibility support in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl).
platform: Xamarin
control: SfSegmentedControl
documentation: ug
---

# Accessibility in Xamarin Segmented Control (SfSegmentedControl)

The segmented control supports automation for each segment item by leveraging the `AutomationId` property. The specified `AutomationId` value for the control is appended with each segment item’s text, facilitating the creation of precise automation scripts. The code snippet below demonstrates the assignment of an `AutomationId` value to the segmented control.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSegmentedControl AutomationId="SegmentedControl1" ItemsSource="{Binding Segments}" />

{% endhighlight %}

{% highlight c# %}

ViewModel viewModel = new ViewModel();
SfSegmentedControl sfSegmented = new SfSegmentedControl();
sfSegmented.AutomationId = "SegmentedControl1";
sfSegmented.ItemsSource = viewModel.Segments;

public class ViewModel
{
    public ObservableCollection<SfSegmentItem> Segments { get; set; }

    public ViewModel()
    {
        Segments = new ObservableCollection<SfSegmentItem>();
        Segments.Add(new SfSegmentItem() { Text = "Max" });
        Segments.Add(new SfSegmentItem() { Text = "Roger" });
        Segments.Add(new SfSegmentItem() { Text = "Evans" });
        Segments.Add(new SfSegmentItem() { Text = "John" });
        Segments.Add(new SfSegmentItem() { Text = "Peter" });
        Segments.Add(new SfSegmentItem() { Text = "Mike" });
    }    
}

{% endhighlight %}

{% endtabs %}

The table below illustrates the `AutomationId` value assigned to each segment item in the control, based on the code snippet provided:

<table>
<tr>
<th>Segment item</th>
<th>AutomationId</th>
</tr>

<tr>
<td>Max</td>
<td>SegmentedControl1_Max</td>
</tr>

<tr>
<td>Roger</td>
<td>SegmentedControl1_Roger</td>
</tr>

<tr>
<td>Evans</td>
<td>SegmentedControl1_Evans</td>
</tr>

<tr>
<td>John</td>
<td>SegmentedControl1_John</td>
</tr>

<tr>
<td>Peter</td>
<td>SegmentedControl1_Peter</td>
</tr>

<tr>
<td>Mike</td>
<td>SegmentedControl1_Mike</td>
</tr>

</table>
