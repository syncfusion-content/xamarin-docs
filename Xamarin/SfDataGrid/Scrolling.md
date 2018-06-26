---
layout: post
title: Scroll to Row Column Index | SfDataGrid | Xamarin | Syncfusion
description: How to scroll programmatically to particular Row and Column in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---
# Scrolling 

## Scrolling mode

The data grid provides three types of scrolling mode that can be customized by using the [SfDataGrid.ScrollingMode](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollingMode.html) property. By default, the control will scroll the content based on pixel values. The scrolling modes are as follows: 

 * PixelLine
 * Line
 * Pixel

N> The data grid supports for the vertical and horizontal scrollbars in UWP. In addition to that, mouse scrolling is also supporting in UWP desktop application.

### PixelLine

The `ScrollingMode.PixelLine` allows you to scroll its contents like an excel sheet i.e., whenever a row or a column is clipped on the top, the particular row or column will auto scroll to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

![](SfDataGrid_images/PixelLine.gif)

### Line

The `ScrollingMode.Line` allows you to scroll its contents based on lines i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

![](SfDataGrid_images/Line.gif)

### Pixel

The `ScrollingMode.Pixel` allows you to scroll its contents based on pixel values i.e., the view will update each pixel change of the offsets, and row or column will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

![](SfDataGrid_images/Pixel.gif)

## Programmatic scrolling

The data grid scrolls to a particular row and column index programmatically.

### Scroll to row and column index

Scroll programmatically to a particular row and column using the [SfDataGrid.ScrollToRowColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowColumnIndex.html) method by passing row and column indexes.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

//For example, 
dataGrid.ScrollToRowColumnIndex(20, 6);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowColumnIndex.gif)

### Scroll to row index

Scroll programmatically to a particular row using the [SfDataGrid.ScrollToRowIndex](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowIndex.html) method by passing the row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

//For example, 
dataGrid.ScrollToRowIndex(20);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowIndex.gif)

### Scroll to column index

Scroll programmatically to a particular column using the [SfDataGrid.ScrollToColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToColumnIndex.html) method by passing the column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

//For example,
dataGrid.ScrollToColumnIndex(7);

{% endhighlight %}

![](SfDataGrid_images/ScrollToColumnIndex.gif)

## Vertical Over Scroll Mode

The [SfDataGrid.VerticalOverScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) property customizes the bouncing behavior of the data grid.

The `SfDataGrid.VerticalOverScrollMode` is of [VerticalScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) type having the following two modes: 

 * Bounce
 * None

### Bounce
 
The `Bounce` mode allows the data grid to have bouncing effect. Default value of `SfDataGrid.VerticalOverScrollMode` is `Bounce` .

To customize the bouncing effect in the data grid, follow the code example:

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

### None

The `None` mode disables the bouncing effect in the data grid.

To customize the bouncing effect in the data grid, follow the code example:

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

## Scrolling customization using Slider

The data grid allows scrolling to a particular row by passing the row index to the `ScrollToRowIndex` method. To scroll the control when interacting with `Slider`, pass the `Slider.Value` as the row index to the `ScrollToRowIndex` method.

To customize the data grid scrolling programmatically using `Slider`, follow the code example:

{% highlight C# %}

Slider slider = new Slider();

slider.ValueChanged += Slider_ValueChanged;
private void Slider_ValueChanged(object sender, ValueChangedEventArgs e)
{
    dataGrid.ScrollToRowIndex((int)(e.NewValue));
}
{% endhighlight %}


![](SfDataGrid_images/Slider.gif)