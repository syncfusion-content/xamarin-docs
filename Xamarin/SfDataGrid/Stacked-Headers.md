---
layout: post
title: Mutiple/Multi-level column headers | SfDataGrid | Xamarin | Syncfusion
description: Display and customize multiple / multi-level column headers in Xamarin.Forms DataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Stacked Headers 
The SfDataGrid supports displaying additional unbound, multiple/multi-level header rows known as `StackedHeaderRows` that span across the DataGrid columns. You can group one or more columns under each stacked header.

Each `StackedHeaderRow` contains `StackedColumns` which contains a number of child columns. The `StackedColumn.ChildColumns` property contains the columns grouped under the stacked header row. The `StackedColumn.MappingName` is a unique name used for mapping a specific child column that is grouped under the same stacked header row whereas, the `StackedColumn.Text` contains the text displayed in the stacked header row.

### Adding Stacked header
The stacked headers can be added by using the below steps,

1. Create an object of `StackedHeaderRow` for adding stacked columns.

2. Add the columns using `ChildColumns` property of `StackedColumn`.

3. Add the `StackedColumn` to `StackedColumns` collection.

4. Finally add the `StackedHeaderRow` to `StackedHeaderRows` collection of the SfDataGrid. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"         
                       ItemsSource="{Binding Orders}">
     <syncfusion:SfDataGrid.StackedHeaderRows>
            <syncfusion:StackedHeaderRow>
                <syncfusion:StackedHeaderRow.StackedColumns>
                    <syncfusion:StackedColumn
                            ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                            Text="Order Shipment Details"
                            MappingName="SalesDetails"
                            FontAttribute="Bold"
                            TextAlignment="Center"
                            />
                </syncfusion:StackedHeaderRow.StackedColumns>
            </syncfusion:StackedHeaderRow>
            <syncfusion:StackedHeaderRow>
                <syncfusion:StackedHeaderRow.StackedColumns>
                    <syncfusion:StackedColumn
                            ChildColumns="OrderID,OrderDate"
                            Text="Order Details"
                            MappingName="OrderDetails"
                            FontAttribute="Bold"
                            TextAlignment="Center"
                            />
                    <syncfusion:StackedColumn
                            ChildColumns="CustomerID,ContactName"
                            Text="Customer Details"
                            MappingName="CustomerDetails"
                            FontAttribute="Bold"
                            TextAlignment="Center"
                            />
                </syncfusion:StackedHeaderRow.StackedColumns>
            </syncfusion:StackedHeaderRow>
        </syncfusion:SfDataGrid.StackedHeaderRows>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
var stackedHeaderRow = new StackedHeaderRow();
stackedHeaderRow.StackedColumns.Add(new StackedColumn()
{
	ChildColumns = "OrderID" + "," + "OrderDate" + "," + "CustomerID" + "," + "ContactName",
	Text = "Order Shipment Details",
	MappingName = "SalesDetails",
	FontAttribute = FontAttributes.Bold,
	TextAlignment = TextAlignment.Center,
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);

var stackedHeaderRow1 = new StackedHeaderRow();
stackedHeaderRow1.StackedColumns.Add(new StackedColumn()
{
	ChildColumns = "OrderID" + "," + "OrderDate",
	Text = "Order Details",
	MappingName = "OrderDetails",
	FontAttribute = FontAttributes.Bold,
	TextAlignment = TextAlignment.Center
});
stackedHeaderRow1.StackedColumns.Add(new StackedColumn()
{
	ChildColumns = "CustomerID" + "," + "ContactName",
	Text = "Customer Details",
	MappingName = "CustomerDetails",
	FontAttribute = FontAttributes.Bold, 
	TextAlignment = TextAlignment.Center
});
this.dataGrid.StackedHeaderRows.Add(stackedHeaderRow1);
{% endhighlight %}
{% endtabs %}

![Multi-lelvel/Multiple headers in Xamarin.Forms datagrid](SfDataGrid_images/StackedHeader.png)

## Adding ChildColumns
You can add the child columns to a particular stacked header row directly using the below code snippet.

{% tabs %}
{% highlight c# %}
var childColumn = dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns;
dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns = childColumn + "," + "OrderDate";
{% endhighlight %}
{% endtabs %}

## Removing ChildColumns
Similarly, you can remove the child columns from a particular stacked header row directly using the below code snippet.

{% tabs %}
{% highlight c# %}
var removingColumns = this.dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns.Split(',').ToList<string>();   
string childColumns = string.Empty;

foreach(var stackedColumnName in removingColumns.ToList())
{
    if (stackedColumnName.Equals("OrderID"))
    {
        removingColumns.Remove(stackedColumnName);
    }
    else
    {
        childColumns = childColumns + stackedColumnName + ",";
    }
}
dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns = childColumns;
{% endhighlight %}
{% endtabs %}

## Changing stacked header row height
You can change the height of StackedHeaderRows by using `SfDataGrid.HeaderRowHeight` property.

{% tabs %}
{% highlight c# %}
dataGrid.HeaderRowHeight = 50;
{% endhighlight %}
{% endtabs %}

You can also change the height of stacked header rows using `SfDataGrid.QueryRowHeight` event.

{% tabs %}
{% highlight c# %}
dataGrid.QueryRowHeight += dataGrid_QueryRowHeight;
void dataGrid_QueryRowHeight(object sender, QueryRowHeightEventArgs  e)
{
    if(e.RowIndex < this.dataGrid.GetHeaderIndex())
    {
        // Using below code you can set a desired height based on the row index. 
        e.Height = 50;
        // Uncomment the below line of code to apply auto fit height based on the contents of the stacked header row.
        //e.Height = dataGrid.GetRowHeight(e.RowIndex);
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}

## Appearance
### Font customization

Customize the FontSize, FontFamily and the FontAttribute of the text displayed in stacked header column using the `StackedColumn.TextSize`, `StackedColumn.Font` and `StackedColumn.FontAttribute` property respectively. The default font size and font attribute are 14 and normal respectively.

Refer the below code snippet to customize the font of the text in stacked columns.

{% tabs %}
{% highlight xaml %}
<syncfusion:StackedHeaderRow>
    <syncfusion:StackedHeaderRow.StackedColumns>
        <syncfusion:StackedColumn
                ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                Text="Order Shipment Details"
                MappingName="SalesDetails"
                TextSize = 16
                Font="Helvetica Neue"
                FontAttribute="Bold"
                />
    </syncfusion:StackedHeaderRow.StackedColumns>
</syncfusion:StackedHeaderRow>
{% endhighlight %}
{% highlight c# %}
var stackedHeaderRow = new StackedHeaderRow();
stackedHeaderRow.StackedColumns.Add(new StackedColumn()
{
	ChildColumns = "OrderID" + "," + "OrderDate" + "," + "CustomerID" + "," + "ContactName",
	Text = "Order Shipment Details",
	MappingName = "SalesDetails",
    TextSize = 14,
    Font = "Helvetica Neue",
    FontAttribute = FontAttributes.Bold
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
{% endhighlight %}
{% endtabs %}

###	Foreground & Background customization
The appearance of stacked header row can be customized by returning a desired color in the `GetStackedHeaderBackgroundColor()` and `GetStackedHeaderForegroundColor()` overrides of the  custom written style class derived from `DataGridStyle`, and assigning it to the `SfDataGrid.GridStyle` property. 

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local ="clr-namespace:DataGridSample;assembly=DataGridSample"
             x:Class="DataGridSample.Sample">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:Dark x:Key="dark" />
        </ResourceDictionary>
    </ContentPage.Resources>

    <syncfusion:SfDataGrid x:Name="dataGrid"
                GridStyle="{StaticResource dark}"
                ItemsSource="{Binding OrdersInfo}" />
</ContentPage> 
{% endhighlight %}
{% highlight c# %}
//Apply custom style to SfDataGrid from code
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.GridStyle = new Dark ();
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
//Custom style class
public class Dark : DataGridStyle
{
    public Dark ()
    {
    }

    public override Color GetStackedHeaderBackgroundColor(int rowIndex)
    {
        return Color.FromRgb(15, 15, 15);
    }

    public override Color GetStackedHeaderForegroundColor(int rowIndex)
    {
        return Color.FromRgb(255, 255, 255);
    }  
} 
{% endhighlight %}

![Customize appearance of stacked header row](SfDataGrid_images/StackedHeader.png)

### Conditional styling

The SfDataGrid also allows to customize the appearance of stacked header rows based on its row index. Refer the below code snippet to achieve the same.

{% highlight c# %}
//Custom style class
public class Dark : DataGridStyle
{
    public Dark ()
    {
    }

    public override Color GetStackedHeaderBackgroundColor(int rowIndex)
    {
        if (rowIndex == 0)
        {
            return Color.FromRgb(15, 15, 15);
        }
        else
        {
            return Color.FromRgb(43, 43, 43);
        }
    }

    public override Color GetStackedHeaderForegroundColor(int rowIndex)
    {
        if (rowIndex == 0)
        {
            return Color.FromRgb(255, 255, 255);
        }
        else
        {
            return Color.FromRgb(43, 43, 43);
        }
    } 
} 
{% endhighlight %}

![Customize background of stacked header row based on index](SfDataGrid_images/StackedHeader.png)

## Loading template in stacked column

The SfDataGrid allows you to load any desired view inside a `StackedColumn` using the `StackedColumn.Template` property. Refer the below code snippet to load a custom view inside a stacked column header.

{% tabs %}
{% highlight xaml %}
<syncfusion:StackedHeaderRow>
    <syncfusion:StackedHeaderRow.StackedColumns>
        <syncfusion:StackedColumn 
                ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                Text="Order Shipment Details"
                MappingName="SalesDetails">
                <syncfusion:StackedColumn.Template>
                    <DataTemplate>
                        <Label Text="Order Details" BackgroundColor="Red"/>
                    </DataTemplate>
                </syncfusion:StackedColumn.Template>
        </syncfusion:StackedColumn>  
    </syncfusion:StackedHeaderRow.StackedColumns>
</syncfusion:StackedHeaderRow>
{% endhighlight %}
{% highlight c# %}
var stackedHeaderRow = new StackedHeaderRow();
stackedHeaderRow.StackedColumns.Add(new StackedColumn()
{
    ChildColumns = "OrderID" + "," + "OrderDate" + "," + "CustomerID" + "," + "ContactName",
    Text = "Order Shipment Details",
    MappingName = "SalesDetails",
    Template = new DataTemplate(()=>{
        return new Label() { BackgroundColor = Color.Red, Text = " Order Details" };
    })
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
{% endhighlight %}
{% endtabs %}

![Load template in stacked header rows](SfDataGrid_images/StackedHeader.png)

