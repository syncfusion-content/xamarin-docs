---
layout: post
title: Freeze Panes | SfDataGrid | Xamarin | Syncfusion
description: Freeze rows and columns in a Xamarin.Forms DataGrid with support to customize the freeze count in the runtime. 
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Freeze Panes

The SfDataGrid allows to freeze the rows and columns when scrolling the grid.

## Freeze rows

The SfDataGrid provides extensive support to freeze the rows at the top of the view below the header row by setting the [SfDataGrid.FrozenRowsCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_FrozenRowsCount) property. 

The following code example illustrates freezing two rows:

{% highlight c# %}
//Setting number of rows to freeze in SfDataGrid
dataGrid.FrozenRowsCount = 2; 
{% endhighlight %}

### Limitation

 * `FrozenRowsCount` should be lesser than the number of rows displayed in view. For example, If you have 10 rows in view, then you set `FrozenRowsCount` to a maximum value of 9.

N> Header row is frozen by default and works regardless of the `FrozenRowsCount` property.

## Freeze columns

The SfDataGrid also supports to freeze the columns at the left of the view by setting the [SfDataGrid.FrozenColumnsCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_FrozenColumnsCount) property. 

The following code example illustrates freezing two columns:

{% highlight c# %}
//Setting number of columns to freeze in SfDataGrid
dataGrid.FrozenColumnsCount = 2;  
{% endhighlight %}

### Limitation

* `FrozenColumnsCount` should be lesser than number of columns displayed in view. For example, If you have 5 columns in view, then you can set `FrozenColumnsCount` to a maximum value of 4.

N> RowHeader is frozen by default and works regardless of the `FrozenColumnsCount` property.

The following GIF illustrates FrozenRows and FrozenColumns.

![DataGrid with row pinning and column pinning](SfDataGrid_images/FreezePanes.Gif)
