---
layout: post
title: Automation in Syncfusion segmented control for Xamarin.Forms
description: Learn how to automate the segmented control
platform: Xamarin
control: SfSegmentedControl
documentation: ug
---

# Automation

The segmented control supports for automating the each segment item in the control using the  `AutomationId` property. The AutomationId value given for control will appends with the each segment item's text value and it can be used for writing automation scripts. The below code snippet explains how to set AutomationId value for segmented control.

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
        Segments.Add(new SfSegmentItem() { Text = "Riya" });
        Segments.Add(new SfSegmentItem() { Text = "Evans" });
        Segments.Add(new SfSegmentItem() { Text = "John" });
        Segments.Add(new SfSegmentItem() { Text = "Peter" });
        Segments.Add(new SfSegmentItem() { Text = "Mike" });
    }    
}

{% endhighlight %}

{% endtabs %}

The below table describes how to set the AutomationId for the above code snippet for each segment item in the control.

<table>
<tr>
<th>Segment item</th>
<th>AutomationId</th>
<tr>

<tr>
<td>Max</td>
<td>SegmentedControl1_Max</td>
<tr>

<tr>
<td>Riya</td>
<td>SegmentedControl1_Riya</td>
<tr>

<tr>
<td>Evans</td>
<td>SegmentedControl1_Evans</td>
<tr>

<tr>
<td>John</td>
<td>SegmentedControl1_John</td>
<tr>

<tr>
<td>Peter</td>
<td>SegmentedControl1_Peter</td>
<tr>

<tr>
<td>Mike</td>
<td>SegmentedControl1_Mike</td>
<tr>

</table>
