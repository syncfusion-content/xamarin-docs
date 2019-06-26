---
layout: post
title: Stacked Headers | SfDataGrid | Xamarin | Syncfusion
description: Creating and adding multi level headers to columns, features and customizations available in multi level headers in Xamarin.Forms DataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Stacked Headers 
The SfDataGrid supports additional unbound multi-level header rows known as `stacked header rows` that span across the DataGrid columns using `StackedHeaderRows`. You can group one or more columns under each stacked header.

Each `StackedHeaderRow` contains `StackedColumns` where each `StackedColumn` contains a number of child columns. The `StackedColumn.ChildColumns` property returns the columns grouped under the stacked header row. The `StackedColumn.MappingName` is a unique name used for mapping a specific child columns grouped under the same stacked header row whereas, the `StackedColumn.Text` returns the text displayed in the stacked header row.

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

![DataGrid shown with stacked header rows](SfDataGrid_images/StackedHeader.png)
## Adding ChildColumns
You can add the child columns in particular stacked header directly.

{% tabs %}
{% highlight c# %}
var childColumn = dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns;
dataGrid.StackedHeaderRows[0].StackedColumns[0].ChildColumns = childColumn + "," + "OrderDate";
{% endhighlight %}
{% endtabs %}
## Removing ChildColumns
Similarly, you can remove the child columns from particular stacked header directly.

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
        e.Height = 50;
        e.Handled = true;
    }
}
{% endhighlight %}
{% endtabs %}
## Appearance
### Font customization
#### Size
The FontSize can be customized using the dataGrid.StackedHeaderRows[0].StackedColumns[0].TextSize property. The default font size is 14.

{% tabs %}
{% highlight xaml %}
<syncfusion:StackedHeaderRow>
    <syncfusion:StackedHeaderRow.StackedColumns>
        <syncfusion:StackedColumn
                ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                Text="Order Shipment Details"
                MappingName="SalesDetails"
                TextSize = 16
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
    TextSize = 14
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
{% endhighlight %}
{% endtabs %}
#### Style
The FontFamily can be customized using the dataGrid.StackedHeaderRows[0].StackedColumns[0].Font property. The default font value is HelveticaNeue LT 55 Roman.

{% tabs %}
{% highlight xaml %}
<syncfusion:StackedHeaderRow>
    <syncfusion:StackedHeaderRow.StackedColumns>
        <syncfusion:StackedColumn
                ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                Text="Order Shipment Details"
                MappingName="SalesDetails"
                Font="Helvetica Neue"
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
    Font = "Helvetica Neue"
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
{% endhighlight %}
{% endtabs %}

#### Attribute
The FontAttribute can be customized using the dataGrid.StackedHeaderRows[0].StackedColumns[0].FontAttribute property. The default value of this property is None. It can be customized as Bold or Italic.

{% tabs %}
{% highlight xaml %}
<syncfusion:StackedHeaderRow>
    <syncfusion:StackedHeaderRow.StackedColumns>
        <syncfusion:StackedColumn
                ChildColumns="OrderID,OrderDate,CustomerID,ContactName"
                Text="Order Shipment Details"
                MappingName="SalesDetails"
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
	FontAttribute = FontAttributes.Bold
});
dataGrid.StackedHeaderRows.Add(stackedHeaderRow);
{% endhighlight %}
{% endtabs %}
###	Foreground & Background customization
The appearance of stacked header row can be customized by writing a Style class overriding from `DataGridStyle`, and assigning it to the `SfDataGrid.GridStyle` property. 

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

![DataGrid showing stacked header rows with style applied](SfDataGrid_images/StackedHeader.png)
### Conditional styling
An appearance of the stacked header row can be customized by overriding from `DataGridStyle`. The SfDataGrid allow to check the row index for stacked header row by getting the property from e.RowIndex. 

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

![DataGrid showing stacked header rows with style applied](SfDataGrid_images/StackedHeader.png)
## Loading template in stacked column

The SfDataGrid allows you to set template for each `StackedColumn` using dataGrid.StackedHeaderRows[0].StackedColumns[0].Template property.

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

![DataGrid showing stacked header rows loaded with template in each stacked column](SfDataGrid_images/StackedHeader.png)

