---
layout: post
title: Automation in Syncfusion segmented control for Xamarin.Forms
description: Learn how to automate the segmented control
platform: Xamarin
control: SfSegmentedControl
documentation: ug
---

# AutomationId

The segmented control supports automating each segment item in control using the  `AutomationId` property. The AutomationId value given for control will be appended with each segment item's text value, and it can be used for writing automation scripts. The following code snippet explains how to set AutomationId value to the segmented control.

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

The following table shows that the AutomationId value is set to each segment item in control for the above code snippet.

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
