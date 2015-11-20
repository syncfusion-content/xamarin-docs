---
layout: post
title: Summary | SfDataGrid | Xamarin | Syncfusion
description: Summary
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Summary

This section explains you how to show the summarizing information of grouped data and how to customize the format of the summary information in **SfDataGrid**.

**SfDataGrid** displays the summaries for each Group using the CaptionSummaryRow. The CaptionSummaryRow carries the information about a particular Group like the Group name, number of items (records) in the Group, etc.

**SfDataGrid** also supports setting custom GroupCaptionTextFormat for CaptionSummaryRows. By default the group caption text will be in the format "{ColumnName} : {Key} - {ItemsCount} Items".
 
* ColumnName : Displays the grouped column name.
* Key : Displays the group key value.
* ItemsCount : Displays the number of items in group.

You can customize this group caption text format by setting the **SfDataGrid.GroupCaptionTextFormat** property. The following code example illustrates how to customize GroupCaptionText in **SfDataGrid**.

{% highlight c# %}
//Customized GroupCaptionText in German
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key} - {ItemsCount} Produkte"; 
{% endhighlight %}
