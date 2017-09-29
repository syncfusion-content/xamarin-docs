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

![](SfDataGrid_images/PixelLine.gif)

### Line

`ScrollingMode.Line`, will allow to scroll its contents based on lines. i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

![](SfDataGrid_images/Line.gif)

### Pixel

`ScrollingMode.Pixel`, will allow to scroll its contents based on pixel values. i.e., the view will be updated each pixel change of the offsets and rows or columns will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

![](SfDataGrid_images/Pixel.gif)

## Programmatic Scrolling

SfDataGrid allow you to scroll to particular Row and Column index from programmatically

### Scroll to Row and Column Index

* You can scroll programmatically to particular Row and Column using [SfDataGrid.ScrollToRowColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowColumnIndex.html) method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

//For example 
dataGrid.ScrollToRowColumnIndex(20, 6);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowColumnIndex.gif)

### Scroll to Row Index

* You can scroll programmatically to particular Row [SfDataGrid.ScrollToRowIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowIndex.html) method by passing row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

//For example 
dataGrid.ScrollToRowIndex(20);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowIndex.gif)

### Scroll to Column Index

* You can scroll programmatically to particular Column [SfDataGrid.ScrollToColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToColumnIndex.html) method by passing column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

//For example
dataGrid.ScrollToColumnIndex(7);

{% endhighlight %}

![](SfDataGrid_images/ScrollToColumnIndex.gif)

### Vertical Over Scroll Mode
[SfDataGrid.VerticalOverScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) property allows you to customize the bouncing behavior of the SfDataGrid.

 `SfDataGrid.VerticalOverScrollMode` is of type [VerticalScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) which has the below two modes. 

 * Bounce
 * None

#### Bounce
 Bounce allows the SfDataGrid to have bouncing effect. The default value of `SfDataGrid.VerticalOverScrollMode` is `Bounce` .

The below code example illustrates the how to customize the bouncing effect in SfDataGrid. 
{% tabs %}
{% highlight C# %}

dataGrid.VerticalOverScrollMode = VerticalOverScrollMode.Bounce;

{% endhighlight %}
{% highlight xaml %}

  <sfgrid:SfDataGrid x:Name="dataGrid"
                     ColumnSizer="Star"
                     VerticalOverScrollMode="Bounce"
                     ItemsSource="{Binding OrdersInfo}">  
  </sfgrid:SfDataGrid>

{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/VerticalOverScrollMode_Bounce.gif)

#### None
None disables the bouncing effect in SfDataGrid.

The below code example illustrates the how to customize the bouncing effect in SfDataGrid. 
{% tabs %}
{% highlight C# %}

dataGrid.VerticalOverScrollMode = VerticalOverScrollMode.None;

{% endhighlight %}
{% highlight xaml %}

  <sfgrid:SfDataGrid x:Name="dataGrid"
                     ColumnSizer="Star"
                     VerticalOverScrollMode="None"
                     ItemsSource="{Binding OrdersInfo}">  
  </sfgrid:SfDataGrid>

{% endhighlight %}
{% endtabs %}



![](SfDataGrid_images/VerticalOverScrollMode_none.gif)

## How to

### Scrolling customization using Slider

SfDataGrid allows you to scroll to a particular row by passing the row index to the `ScrollToRowIndex` method. To scroll the SfDataGrid when interacting on a `Slider`, you need to pass the `Slider.Value` as row index to the `ScrollToRowIndex` method.

The below code illustrates how to customize the SfDataGrid scrolling programmatically using a `Slider`.

{% highlight C# %}

Slider slider = new Slider();

slider.ValueChanged += Slider_ValueChanged;
private void Slider_ValueChanged(object sender, ValueChangedEventArgs e)
{
    dataGrid.ScrollToRowIndex((int)(e.NewValue));
}
{% endhighlight %}


![](SfDataGrid_images/Slider.gif)