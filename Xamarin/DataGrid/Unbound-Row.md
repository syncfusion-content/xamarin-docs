---
layout: post
title: UnboundRow | SfDataGrid | Xamarin | Syncfusion
description: Create and use Unbound Rows in Xamarin.Forms DataGrid. Describes how to populate data for unbound rows using event.
platform: xamarin
control: SfDataGrid
documentation: ug
---


# Unbound Rows 

The Xamarin.Forms DataGrid allows you to add **additional rows** at top and also bottom of the DataGrid which are **not bound with data object** of underlying data source. You can add unbound rows using [SfDataGrid.UnboundRows](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.UnboundRows.html) collection property. You can add any no of unbound rows to the DataGrid. Unbound rows can also be exported to pdf and excel documents.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"  ItemsSource="{Binding OrdersInfo}">
   <syncfusion:SfDataGrid.UnboundRows>
        <syncfusion:GridUnboundRow Position="Top" />
   </syncfusion:SfDataGrid.UnboundRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.UnboundRows.Add(new GridUnboundRow() { Position = UnboundRowsPosition.Top });
{% endhighlight %}
{% endtabs %}

![Unbound Rows](SfDataGrid_images\UnboundRows.png)


## Positioning unbound rows

Unbound row can be placed in top or bottom of the DataGrid by setting the desired value to the [GridUnboundRow.Position](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundRow.html#Syncfusion_SfDataGrid_XForms_GridUnboundRow_Position) property.

Below table shows the available unbound row positions.

<table>
<tr>
<th>
UnboundRowPosition
</th>
<th>
Position in DataGrid
</th>
</tr>
<tr>
<td>
FixedTop
</td>
<td>
Unbound row placed at top, right below the Header row. In this position, unbound row is not selectable, <b>not editable</b> and <b>frozen</b> when scrolling.
</td>
</tr>
<tr>
<td>
Top
</td>
<td>
Unbound row placed at top, right above the record rows. In this position, unbound row is selectable, <b>editable</b> and <b>scrollable</b>.
</td>
</tr>
<tr>
<td>
Bottom
</td>
<td>
Unbound row placed at bottom, right below record rows. In this position, unbound row is selectable, <b>editable</b> and <b>scrollable</b>.
</td>
</tr>
<tr>
<td>
FixedBottom
</td>
<td>
Unbound row placed at bottom of SfDataGrid. In this position, unbound row is not selectable, <b>not editable</b> and <b>frozen</b> when scrolling.
</td>
</tr>
</table>

Below screenshot shows different unbound rows placed in all possible positions.

![Positioning unbound rows](SfDataGrid_images\Positioning_unboundrows.png)

## Populating data for unbound rows

You can populate data for the unbound row by handling [QueryUnboundRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event of Xamarin.Forms DataGrid. This event is fired for each cell of the unbound rows whenever the row gets refreshed or comes to view. 
[GridUnboundRowEventsArgs](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundRowEventArgs.html) of the `QueryUnboundRow` event provides information about the cell that triggered this event.

You can get or set the [GridUnboundRowEventsArgs.Value](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundRowEventArgs.html#Syncfusion_SfDataGrid_XForms_GridUnboundRowEventArgs_Value) property based on the [UnboundAction](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundRowEventArgs.html#Syncfusion_SfDataGrid_XForms_GridUnboundRowEventArgs_UnboundAction). If `UnboundAction` is `QueryData` then you can set the value to be displayed. If the `UnboundAction` is `CommitData` then you can get the edited value.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" 
                       ItemsSource="{Binding Orders}"                         
                       SelectionMode="Multiple" >                        
      <syncfusion:SfDataGrid.UnboundRows>
        <syncfusion:GridUnboundRow Position="Top" />
   </syncfusion:SfDataGrid.UnboundRows>                                 
</syncfusion:SfDataGrid>
{% endhighlight %}
{% endtabs %}

For example, now unbound row populated based on selected items in SfDataGrid.


{% tabs %}
{% highlight c# %}
dataGrid.GridViewCreated += DataGrid_GridViewCreated;
dataGrid.QueryUnboundRow += DataGrid_QueryUnboundRow;

private void DataGrid_GridViewCreated(object sender, GridViewCreatedEventArgs e)
{
    dataGrid.SelectedItems.Add(viewModel.OrdersInfo[3]); 
}

private void DataGrid_QueryUnboundRow(object sender, GridUnboundRowEventArgs e)
{
    if (e.UnboundAction == UnboundActions.QueryData)
    {
        if (e.RowColumnIndex.ColumnIndex == 0)
        {
         e.Value = (dataGrid.CurrentItem as OrderInfo).OrderID;
         e.Handled = true;
        }
        else if (e.RowColumnIndex.ColumnIndex == 1)
        {
         e.Value = (dataGrid.CurrentItem as OrderInfo).LastName;
        }
        else if (e.RowColumnIndex.ColumnIndex == 2)
        {
          e.Value = (dataGrid.CurrentItem as OrderInfo).Freight;
          e.Handled = true;
        }
        else if (e.RowColumnIndex.ColumnIndex == 3)
        {
           e.Value = (dataGrid.CurrentItem as OrderInfo).ShipCountry;
           e.Handled = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![Populating data for unbound rows](SfDataGrid_images\PopulatingUnboundRow.png)

## Refreshing the Unbound Rows at runtime


### Add/Remove unbound rows

You can add or remove unbound rows using [SfDataGrid.UnboundRows](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.UnboundRows.html) property which reflects in UI immediately.
 
### Trigger QueryUnboundRow event programmatically
 
You can trigger the [QueryUnboundRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event for the unbound row cells at runtime by calling [SfDataGrid.InvalidateUnboundRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_InvalidateUnboundRow_Syncfusion_SfDataGrid_XForms_GridUnboundRow_System_Boolean_) method which invalidates the unbound row at the given index.

Here in the below code example, we have invalidated the unbound rows whenever selection is changed in the DataGrid.

{% tabs %}
{% highlight c# %}
this.dataGrid.SelectionChanged += dataGrid_SelectionChanged;
private void dataGrid_SelectionChanged(object sender, GridSelectionChangedEventArgs e)
{
    this.dataGrid.InvalidateUnboundRow(this.dataGrid.UnboundRows[0]);
}
{% endhighlight %}
{% endtabs %}

![Refreshing the Unbound Rows at runtime](SfDataGrid_images\UnboundRowRuntime.png)

## Editing in unbound rows

### Cancel the editing for unbound row cell

You can cancel the editing of unbound row cell in the event handler of  [SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event with the help of [SfDataGrid.GetUnboundRowAtRowIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridIndexResolver.html#Syncfusion_SfDataGrid_XForms_GridIndexResolver_GetUnboundRowAtRowIndex_Syncfusion_SfDataGrid_XForms_SfDataGrid_System_Int32_) method and row index.


{% tabs %}
{% highlight c# %}
using Syncfusion.SfDataGrid.XForms;
this.dataGrid.CurrentCellBeginEdit += DataGrid_CurrentCellBeginEdit;

private void DataGrid_CurrentCellBeginEdit(object sender, GridCurrentCellBeginEditEventArgs e)
{
    var unboundRow = dataGrid.GetUnboundRowAtRowIndex(e.RowColumnIndex.RowIndex);

    if (unboundRow == null)
        return;
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

### Saving edited unbound row cell value to external source

You can get the edited value of unbound row cell from [GridUnboundRowEventsArgs.Value](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridUnboundRowEventArgs.html#Syncfusion_SfDataGrid_XForms_GridUnboundRowEventArgs_Value) property of [QueryUnboundRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event when `UnboundAction` is `CommitData`.

{% tabs %}
{% highlight c# %}
 private void DataGrid_QueryUnboundRow(object sender, GridUnboundRowEventArgs e)
{
    if (e.UnboundAction == UnboundActions.CommitData)
    {
       var editedValue = e.Value;
    }
}
{% endhighlight %}
{% endtabs %}

## Styling in Unbound rows

### Override DataGrid style
The Xamarin.Forms DataGrid applies style for unboundRow elements by writing a Style class overriding from DataGridStyle, and assigning it to the [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) property.

To apply custom style for UnboundRow, follow the code example:

{% tabs %}
{% highlight c# %}
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.GridStyle = new Dark ();

public class UnboundRowStyle : DataGridStyle

{
    public UnboundRowStyle()
    {
    }

    public override Color GetUnboundRowForegroundColor()
    {
        return Color.Red;
    }

    public override Color GetUnboundRowBackgroundColor()
    {
        return Color.Yellow;
    }

    public override FontAttributes GetUnboundRowFontAttribute()
        {
            return FontAttributes.Bold;
        }
}
{% endhighlight %}
{% endtabs %}

![Styling in Unbound rows](SfDataGrid_images\UnboundRowStyle.png)

N> You can also apply style to the unbound row using the `SfDataGrid.QueryCellStyle` and `SfDataGrid.QueryRowStyle` event by referring this [link](https://help.syncfusion.com/xamarin/sfdatagrid/conditional-styles#styling-cells-using-querycellstyle-event).

## Changing unbound row height

You can change the height of unbound row using [SfDataGrid.QueryRowHeight](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html) event.


{% tabs %}
{% highlight c# %}
using Syncfusion.SfDataGrid.XForms;
this.dataGrid.QueryRowHeight += DataGrid_QueryRowHeight;        

private void DataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs e)
{

    if (dataGrid.IsUnboundRow(e.RowIndex))
    {
        e.Height = 60;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}

![Changing unbound row height](SfDataGrid_images\UnboundRowHeight.png)

## Get unbound rows

You can get the unbound row at the specified row index using [GetUnboundRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridIndexResolver.html#Syncfusion_SfDataGrid_XForms_GridIndexResolver_GetUnboundRowAtRowIndex_Syncfusion_SfDataGrid_XForms_SfDataGrid_System_Int32_) method.

{% tabs %}
{% highlight c# %}
using Syncfusion.SfDataGrid.XForms;
var unboundRow = dataGrid.GetUnboundRowAtRowIndex(1);
{% endhighlight %}
{% endtabs %}

