---
layout: post
title: Freeze Panes | SfDataGrid | Xamarin | Syncfusion
description: How to freeze rows and columns in a SfDataGrid.
platform: xamarin.iOS
control: SfDataGrid
documentation: UG
---

# Freeze panes

This section explains you how to set Freeze panes in SfDataGrid. 


## Freeze Rows

SfDataGrid provides extensive support to freeze the rows at the top of the view below the header row by setting the [SfDataGrid.FrozenRowsCount](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~FrozenRowsCount.html) property. 

The following code example illustrates freezing two rows in SfDataGrid.

{% highlight c# %}
//Setting number of rows to freeze in SfDataGrid
dataGrid.FrozenRowsCount = 2; 
{% endhighlight %}

### Limitation

* `FrozenRowsCount` should be lesser than the number of rows that is displayed in View.
* For example: 
If you have 10 rows in view, then you set `FrozenRowsCount` to a maximum value of 9.

N> Header row is frozen by default and works regardless of the `FrozenRowsCount` property.


## Freeze Columns

SfDataGrid also provides support to freeze the columns at the left of the view by setting the [SfDataGrid.FrozenColumnsCount](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~FrozenColumnsCount.html) property. 

The following code example illustrates freezing two columns in SfDataGrid.

{% highlight c# %}
//Setting number of columns to freeze in SfDataGrid
dataGrid.FrozenColumnsCount = 2;  
{% endhighlight %}

### Limitation

* `FrozenColumnsCount` should be lesser than number of columns displayed in View.
* For example: 
If you have 5 columns in view, then you can set `FrozenColumnsCount` to a maximum value of 4.

N> RowHeader is frozen by default and works regardless of the `FrozenColumnsCount` property.
