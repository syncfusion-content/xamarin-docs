---
layout: post
title: Scroll to Row Column Index | SfDataGrid | Xamarin | Syncfusion
description: How to scroll programmatically to particular Row and Column in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---
# Scrolling 

## ScrollingMode

SfDataGrid provides three types of scrolling mode which can be customized using the [SfDataGrid.ScrollingMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollingMode.html) property. By default, the SfDataGrid will scroll its content based on pixel values.

* PixelLine
* Line
* Pixel

N> SfDataGrid provides support for the vertical and horizontal scrollbar in UWP. In addition to that, mouse scrolling support is also provided in UWP Desktop application.

### PixelLine

`ScrollingMode.PixelLine`, will allow to scroll its contents like an excel sheet. i.e., whenever a row or a column is clipped on the top, the particular row or column will be auto scrolled to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

### Line

`ScrollingMode.Line`, will allow to scroll its contents based on lines. i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

### Pixel

`ScrollingMode.Pixel`, will allow to scroll its contents based on pixel values. i.e., the view will be updated each pixel change of the offsets and rows or columns will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

## Programmatic Scrolling

SfDataGrid allow you to scroll to particular Row and Column index from programmatically

### Scroll to Row and Column Index

* You can scroll programmatically to particular Row and Column using `SfDataGrid.ScrollToRowColumnIndex` method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

{% endhighlight %}

### Scroll to Row Index

* You can scroll programmatically to particular Row `SfDataGrid.ScrollToRowIndex` method by passing row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

{% endhighlight %}

### Scroll to Column Index

* You can scroll programmatically to particular Column `SfDataGrid.ScrollToColumnIndex` method by passing column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

{% endhighlight %}

### Vertical Over Scroll Mode
[VerticalOverScrollMode](https://help.syncfusion.com/cr/xamarin/sfdatagrid) property allows you to enable or disable the bouncing effect in the SfDataGrid. By Default, `SfDataGrid.VerticalOverScrollMode` value is `Bounce` which enables the bouncing effect. And `SfDataGrid.VerticalOverScrollMode. None` disables the bouncing effect.

The below code illustrates the how to enable the bouncing effect in SfDataGrid. 
{% tabs %}
{% highlight C# %}

dataGrid.VerticalOverScrollMode = VerticalOverScrollMode.Bounce;

{% endhighlight %}
{% highlight xaml %}

  <sfgrid:SfDataGrid x:Name="dataGrid"
                     ColumnSizer="Star"
                     VerticalOverScrollMode="None"
                     ItemsSource="{Binding OrdersInfo}">  
  </sfgrid:SfDataGrid>

{% endhighlight %}
{% endtabs %}
