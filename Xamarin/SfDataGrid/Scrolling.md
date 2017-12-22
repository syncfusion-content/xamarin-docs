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

The SfDataGrid provide three types of scrolling modes customized using the [SfDataGrid.ScrollingMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollingMode.html) property. By default, the control will scroll its content based on pixel values. The scrolling modes are as follows: 

 * PixelLine
 * Line
 * Pixel

N> The SfDataGrid supports for the vertical and horizontal scrollbar in UWP. In addition to that, mouse scrolling is also supporting in UWP desktop application.

### PixelLine

The `ScrollingMode.PixelLine` will allow to scroll its contents like an excel sheet. i.e whenever a row or a column is clipped on the top, the particular row or column will be auto scrolled to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

![](SfDataGrid_images/PixelLine.gif)

### Line

The `ScrollingMode.Line` will allow to scroll its contents based on lines. i.e the view will be updated only when the offset values reaches the origin of a row or column in the bound collection.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

![](SfDataGrid_images/Line.gif)

### Pixel

The `ScrollingMode.Pixel` will allow to scroll its contents based on pixel values. i.e the view will update each pixel change of the offsets, and rows or columns will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

![](SfDataGrid_images/Pixel.gif)

## Programmatic Scrolling

The SfDataGrid allows scrolling to a particular row and column index programmatically.

### Scroll to row and column index

Scroll programmatically to a particular row and column using the [SfDataGrid.ScrollToRowColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowColumnIndex.html) method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

//For example, 
dataGrid.ScrollToRowColumnIndex(20, 6);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowColumnIndex.gif)

### Scroll to row index

Scroll programmatically to a particular row using the [SfDataGrid.ScrollToRowIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToRowIndex.html) method by passing row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

//For example, 
dataGrid.ScrollToRowIndex(20);

{% endhighlight %}

![](SfDataGrid_images/ScrollToRowIndex.gif)

### Scroll to column index

Scroll programmatically to a particular column using the [SfDataGrid.ScrollToColumnIndex](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~ScrollToColumnIndex.html) method by passing column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

//For example,
dataGrid.ScrollToColumnIndex(7);

{% endhighlight %}

![](SfDataGrid_images/ScrollToColumnIndex.gif)

## Vertical Over Scroll Mode
[SfDataGrid.VerticalOverScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) property allows you to customize the bouncing behavior of the SfDataGrid.

The [SfDataGrid.VerticalOverScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) property allows customizing the bouncing behavior of the SfDataGrid.

The `SfDataGrid.VerticalOverScrollMode` is of [VerticalScrollMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~VerticalOverScrollMode.html) type having the following two modes: 

 * Bounce
 * None

### Bounce
 
Bounce allows the SfDataGrid to have bouncing effect. The default value of `SfDataGrid.VerticalOverScrollMode` is `Bounce` .

To customize the bouncing effect in the SfDataGrid, follow the code example:

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

None disables the bouncing effect in the SfDataGrid.

To customize the bouncing effect in the SfDataGrid, follow the code example:

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

The SfDataGrid allows scrolling to a particular row by passing the row index to the `ScrollToRowIndex` method. To scroll the control when interacting on a `Slider`, pass the `Slider.Value` as row index to the `ScrollToRowIndex` method.

To customize the SfDataGrid scrolling programmatically using a `Slider`, follow the code example:

{% highlight C# %}

Slider slider = new Slider();

slider.ValueChanged += Slider_ValueChanged;
private void Slider_ValueChanged(object sender, ValueChangedEventArgs e)
{
    dataGrid.ScrollToRowIndex((int)(e.NewValue));
}
{% endhighlight %}


![](SfDataGrid_images/Slider.gif)