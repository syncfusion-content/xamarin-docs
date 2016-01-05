---
layout: post
title: Summary | SfDataGrid | Xamarin | Syncfusion
description: How to show summary information and it's customizations in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Summary

This section explains you how to show the summarizing information of grouped data and how to customize the format of the summary information in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) displays the summaries for each Group using the CaptionSummaryRow. The CaptionSummaryRow carries the information about a particular Group like the Group name, number of items (records) in the Group, etc.

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) also supports setting custom GroupCaptionTextFormat for CaptionSummaryRows. By default the group caption text will be in the format "{ColumnName} : {Key} - {ItemsCount} Items".
 
* ColumnName : Displays the grouped column name.
* Key : Displays the group key value.
* ItemsCount : Displays the number of items in group.

You can customize this group caption text format by setting the **SfDataGrid.GroupCaptionTextFormat** property. The following code example illustrates how to customize GroupCaptionText in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

{% highlight c# %}
//Customized GroupCaptionText in German
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key} - {ItemsCount} Produkte"; 
{% endhighlight %}
