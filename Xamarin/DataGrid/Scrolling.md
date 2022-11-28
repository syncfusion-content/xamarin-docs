---
layout: post
title: Scrolling in Xamarin DataGrid control | Syncfusion
description: Learn here all about Scrolling support in Syncfusion Xamarin DataGrid (SfDataGrid) control and more.
platform: xamarin
control: SfDataGrid
documentation: ug
---
# Scrolling in Xamarin DataGrid (SfDataGrid)

## Scrolling mode

The data grid provides three types of scrolling mode that can be customized by using the [SfDataGrid.ScrollingMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollingMode) property. By default, the control will scroll the content based on pixel values. The scrolling modes are as follows: 

 * PixelLine
 * Line
 * Pixel

N> The data grid supports for the vertical and horizontal scrollbars in UWP. In addition to that, mouse scrolling is also supporting in UWP desktop application.

### PixelLine

The `ScrollingMode.PixelLine` allows you to scroll its contents like an excel sheet i.e., whenever a row or a column is clipped on the top, the particular row or column will auto scroll to display fully in view.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.PixelLine; 
{% endhighlight %}

![DataGrid with pixel line scrolling mode](SfDataGrid_images/PixelLine.gif)

### Line

The `ScrollingMode.Line` allows you to scroll its contents based on lines i.e., the view will be updated only when the offset values reaches the origin of a row or column in the bound collection.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Line; 
{% endhighlight %}

![DataGrid with line scrolling mode](SfDataGrid_images/Line.gif)

N> [ScrollingMode.Line](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.ScrollingMode.html#Syncfusion_SfDataGrid_XForms_ScrollingMode_Line) will not be worked as expected when row height is customized through [SfDataGrid.QueryRowHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_QueryRowHeight) event , applies width for the columns using the [SfDataGrid.ColumnSizer.Auto](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.ColumnSizer.html#Syncfusion_SfDataGrid_XForms_ColumnSizer_Auto) and [SfDataGrid.ColumnSizer.SizeToHeader](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.ColumnSizer.html#Syncfusion_SfDataGrid_XForms_ColumnSizer_SizeToHeader) options.

### Pixel

The `ScrollingMode.Pixel` allows you to scroll its contents based on pixel values i.e., the view will update each pixel change of the offsets, and row or column will appear clipped when offset exceeds the origin of the row or column.

{% highlight c# %}
dataGrid.ScrollingMode = ScrollingMode.Pixel; 
{% endhighlight %}

![DataGrid with pixel scrolling mode](SfDataGrid_images/Pixel.gif)

## Programmatic scrolling

The data grid scrolls to a particular row and column index programmatically.

### Scroll to row and column index

Scroll programmatically to a particular row and column using the [SfDataGrid.ScrollToRowColumnIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollToRowColumnIndex_System_Int32_System_Int32_System_Boolean_Xamarin_Forms_ScrollToPosition_Xamarin_Forms_ScrollToPosition_) method by passing row and column indexes.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

//For example, 
dataGrid.ScrollToRowColumnIndex(20, 6);

{% endhighlight %}

![DataGrid with programmatic scrolling](SfDataGrid_images/ScrollToRowColumnIndex.gif)

### Scroll to row index

Scroll programmatically to a particular row using the [SfDataGrid.ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollToRowIndex_System_Int32_System_Boolean_Xamarin_Forms_ScrollToPosition_) method by passing the row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

//For example, 
dataGrid.ScrollToRowIndex(20);

{% endhighlight %}

![DataGrid with programmatically scrolling to a row](SfDataGrid_images/ScrollToRowIndex.gif)

### Scroll to column index

Scroll programmatically to a particular column using the [SfDataGrid.ScrollToColumnIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollToColumnIndex_System_Int32_System_Boolean_Xamarin_Forms_ScrollToPosition_) method by passing the column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

//For example,
dataGrid.ScrollToColumnIndex(7);

{% endhighlight %}

![DataGrid with programmatically scrolling to a column](SfDataGrid_images/ScrollToColumnIndex.gif)

### Scroll a row/column to a specific position

The SfDataGrid allows to position the scrolled row/column in the datagrid by passing [ScrollToPosition](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.scrolltoposition?view=xamarin-forms) as parameter to the `ScrollToRowColumnIndex`, `ScrollToRowIndex`, `ScrollToColumnIndex` methods. The scrolled row/column can take either of the four positions as explained below. The default position is `Start`.

* MakeVisible: Scroll to make a specified row/column visible in datagrid. If the specified row/column is already in view, scrolling will not occur.
* Start: Scroll to make the row/column positioned at the start of the datagrid.
* Center: Scroll to make the row/column positioned at the center of the datagrid.
* End: Scroll to make the row/column positioned at the end of the datagrid. 

Refer the below code snippet to scroll a column/row to a specific position.

{% highlight C# %}

// To scroll a column to a particular position,
dataGrid.ScrollToColumnIndex(7,scrollToColumnPosition: ScrollToPosition.Center);

// To scroll a row to a particular position,
dataGrid.ScrollToRowIndex(7,scrollToColumnPosition: ScrollToPosition.Center);

// To scroll a cell to a particular position,
dataGrid.ScrollToRowColumnIndex(7, 7, scrollToColumnPosition: ScrollToPosition.Center, scrollToRowPosition: ScrollToPosition.Center);

{% endhighlight %}

N> Programmatic scrolling is not applicable for rows and columns that are frozen in view.

## Diagonal scrolling 

By default, `SfDataGrid` supports diagonal scrolling(both vertical and horizontal scrolling simultaneously). Setting false to [SfDataGrid.AllowDiagonalScrolling](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_AllowDiagonalScrolling) disables diagonal scrolling and scrolls the data grid in either horizontal or vertical direction but not simultaneously.

{% tabs %}
{% highlight xaml %}
  <syncfusion:SfDataGrid x:Name="dataGrid"
                           ItemsSource="{Binding OrdersInfo,Mode=TwoWay}"
                           AllowDiagonalScrolling="False">
  </syncfusion:SfDataGrid>
{% endhighlight %}

{% highlight c# %}
this.dataGrid.AllowDiagonalScrolling = false;
{% endhighlight %}
{% endtabs %}

## Vertical Over Scroll Mode

The [SfDataGrid.VerticalOverScrollMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_VerticalOverScrollMode) property customizes the bouncing behavior of the data grid.

The `SfDataGrid.VerticalOverScrollMode` is of [VerticalScrollMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_VerticalOverScrollMode) type having the following two modes: 

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

![DataGrid with bouncing effect](SfDataGrid_images/VerticalOverScrollMode_Bounce.gif)

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

![DataGrid without bouncing effect](SfDataGrid_images/VerticalOverScrollMode_none.gif)

## Scrollbar Visibility

You can change the visibility of the horizontal and vertical scrollbar using [SfDataGrid.HorizontalScrollBarVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_HorizontalScrollBarVisibility) and [SfDataGrid.VerticalScrollBarVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_VerticalScrollBarVisibility) properties respectively. By default, the visibility of both the horizontal and vertical scrollbar is `true`.

{% tabs %}
{% highlight xaml %}

using Syncfusion.SfDataGrid.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public partial class DataGridPage : ContentPage
    {
        ViewModel viewModel;
        SfDataGrid dataGrid;
        public DataGridPage()
        {
            InitializeComponent();
            viewModel = new ViewModel();
            dataGrid = new SfDataGrid();
            dataGrid.ItemsSource = viewModel.OrdersInfo;   
            dataGrid.HorizontalScrollBarVisibility = false;
            dataGrid.VerticalScrollBarVisibility = false;
            this.Content = dataGrid;
        }
    }
}

{% endhighlight %}
{% highlight C# %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="GettingStarted.DataGridPage">

    <ContentPage.BindingContext>
        <local:ViewModel/>
    </ContentPage.BindingContext>
    
    <sfgrid:SfDataGrid x:Name="dataGrid"                                       
                       ItemsSource="{Binding OrdersInfo}"         
                       HorizontalScrollBarVisibility="False"
                       VerticalScrollBarVisibility="False">   
        </sfgrid:SfDataGrid> 
</ContentPage>

{% endhighlight %}
{% endtabs %}

N> These properties does not have any effect when the datagrid has no scrollable content in its respective direction. In such cases scroll bar will not be displayed

## Identifying scroll state changes

The `SfDataGrid` will notify the scrolling state changes via the [ScrollStateChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event.

Following states will be notified through the [ScrollState](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.ScrollStateChangedEventArgs.html#Syncfusion_SfDataGrid_XForms_ScrollStateChangedEventArgs__ctor_Syncfusion_SfDataGrid_XForms_ScrollState_) property in the event argument.

* Dragging: Specifies that `SfDataGrid` is currently being dragged in the view.
* Fling: Specifies that fling action is performed on the `SfDataGrid`.
* Idle: Specifies that `SfDataGrid` is not scrolling currently.
* Programmatic: Specifies that scrolling is performed by using [ScrollToColumnIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollToColumnIndex_System_Int32_System_Boolean_Xamarin_Forms_ScrollToPosition_) or [ScrollToRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ScrollToRowIndex_System_Int32_System_Boolean_Xamarin_Forms_ScrollToPosition_) method.

{% tabs %}
{% highlight c# %}

dataGrid.ScrollStateChanged += DataGrid_ScrollStateChanged;

   private void DataGrid_ScrollStateChanged(object sender, ScrollStateChangedEventArgs e)   
    {
        if (e.ScrollState == ScrollState.Idle)
        {              
            DisplayAlert("ScrollState", "Scrolling has stopped", "OK");
        }
    }

{% endhighlight %}
{% endtabs %}

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


![DataGrid with programmatic scrolling using a slider](SfDataGrid_images/Slider.gif)

## Retain scroll position

To retain the scroll position when [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ItemsSource) changes, set the [SfDataGrid.CanMaintainScrollPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_CanMaintainScrollPosition) to true. If you set [SfDataGrid.CanMaintainScrollPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_CanMaintainScrollPosition) to true then on changing `ItemsSource`, the newly added `ItemsSource` will be loaded with the previous ItemsSource's [ScrollOffset](https://help.syncfusion.com/cr/xamarin/Syncfusion.GridCommon.ScrollAxis.VisibleLineInfo.html#Syncfusion_GridCommon_ScrollAxis_VisibleLineInfo_ScrollOffset).

{% highlight C# %}
dataGrid.CanMaintainScrollPosition = true;
{% endhighlight %}
