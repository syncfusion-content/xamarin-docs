---
layout: post
title: selection changed in Syncfusion segmented control for Xamarin.Forms
description: Learn how to handle selection changed in segmented control
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Selection changed

The selection changed event occurs when there is a change from one segment item to another in the segmented control. It can be handled by two ways.

## User interface

When users navigate from one item to another, selection is changed, so that the `SelectedIndex` value is updated to the new index of the item. The segmented control provides the `SelectionChanged` event, which is triggered when the selection is changed with the `SelectionChangedEventArgs`.

`Index` - Gets the current index value of the selected item.

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl x:Name = "segmentedControl" SelectionChanged="Handle_SelectionChanged"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectionChanged += Handle_SelectionChanged;
void Handle_SelectionChanged(object sender, SelectionChangedEventArgs e)
    {
       segmentedControl.BorderColor = UIColor.Red;
    }

{% endhighlight %}

{% endtabs %}

## Selected Index through programmatically.

Users can set the default value programmatically for the selection to be placed. The selection is updated based on the index value given for the `SelectedIndex`. 

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl SelectedIndex="2"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectedIndex = 2;

{% endhighlight %}

{% endtabs %}


![](images/Selection-changed/selectionchange.png)


