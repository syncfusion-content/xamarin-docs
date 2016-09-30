---
layout: post
title: Column Types | SfDataGrid | Xamarin | Syncfusion
description: What are all the different types of column and it's properties and customizations in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Column Types 

SfDataGrid contains different types of column each with its own functionalities as implied by its name. You can use any column based on your requirements. 

The below table describes you the types of column and its purpose of usage in SfDataGrid.

<table>
<tr>
<th>Column Type</th>
<th>Description</th>
</tr>
<tr>
<td>GridColumn</td>
<td>Abstract class. Base column type of all the columns in the SfDataGrid.</td>
</tr>
<tr>
<td>GridTextColumn</td>
<td>To be used to display string or numbers in each row.</td>
</tr>
<tr>
<td>GridSwitchColumn</td>
<td>To be used when you want to display switch in each row.</td>
</tr>
<tr>
<td>GridImageColumn</td>
<td>To be used when you want to display an image in each row.</td>
</tr>
<tr>
<td>GridTemplateColumn</td>
<td>To be used when you want to customize your column based on your requirements.</td>
</tr>
</table>


## GridColumn

GridColumn is the base column type of all the columns in the SfDataGrid, hence GridColumn properties are used by all the columns. The following sub-sections explains you about the properties in the GridColumn and the customizations that can be done using those properties for all the types of GridColumns available in SfDataGrid.

### Binding options

The display content of GridColumn is determined from [GridColumn.DisplayBinding](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~DisplayBinding.html) property. It gets and sets the binding that associates the GridColumn with a property in the data source. 

#### MappingName

[GridColumn.MappingName](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~MappingName.html) associates the GridColumn with a property available in the underlying data source. While setting MappingName alone to the SfDataGrid the `GridColumn.DisplayBinding` will be automatically generated based on the MappingName. Data Manipulation operations like sorting, filtering, grouping will be done based on the MappingName property.

If you want to format the cell content, you can use the Converter of the `GridColumn.DisplayBinding` to customize the cell content. The following code example appends the text “Customer” along with the Customer ID.

{% highlight xaml %}
<ContentPage.Resources>
    <ResourceDictionary>
        <local:DisplayBindingConverter x:Key="displayBindingConverter" />
    </ResourceDictionary>
</ContentPage.Resources> 

<syncfusion:SfDataGrid x:Name="dataGrid"
                       ItemsSource="{Binding OrdersInfo}">

    <syncfusion:SfDataGrid.Columns>
        <syncfusion:GridTextColumn MappingName="CustomerID" 
                                   DisplayBinding="{Binding CustomerID, 
                                   Converter={StaticResource displayBindingConverter}}" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid> 
{% endhighlight %}

{% highlight c# %}
public class DisplayBindingConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        if (value != null)
            return "Customer:" + value.ToString();
        return null;
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        return value.ToString().Substring(9);
    }
}
{% endhighlight %}

### Header customizations

#### HeaderCellTextSize

The FontSize for the content of header cell in the GridColumn can be customized by using the [GridColumn.HeaderCellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderCellTextSize.html) property. The default font size of the header cells in SfDataGrid is 14.

#### HeaderFont

The FontFamily for the content of header cell in the GridColumn can be customized by using the [GridColumn.HeaderFont](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderFont.html) property. The default value font used in SfDataGrid is `HelveticaNeue LT 55 Roman`.

#### HeaderFontAttribute

The FontAttribute for the content of the header cell in the GridColumn can be customized by using the [GridColumn.HeaderFontAttribute](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderFontAttribute.html) property. The default value of this property is `None` and you can customize this to `Bold` or `Italic`.

#### HeaderText

SfDataGrid allows you to customize the display content of the header cell using the [GridColumn.HeaderText](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderText.html) property. It specifies the text displayed in the column header. If header text is not defined, then `GridColumn.MappingName` will be assigned to the header text and will be displayed as column header.

#### HeaderTextAlignment

You can get or set the TextAlignment of the header cell in the GridColumn by using the [GridColumn.HeaderTextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderTextAlignment.html) property. The default alignment for the header cells in SfDataGrid is `Center` and you can customize this to `Start` or `End`.

#### HeaderTemplate

SfDataGrid allows you to customize the header cell based on your requirement by using the [GridColumn.HeaderTemplate](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderTemplate.html) property. The following code example shows you how to customize the header cell by loading a template in the header cell.

{% highlight xaml %}
<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn MappingName="OrderID">
        <syncfusion:GridTextColumn.HeaderTemplate>
            <DataTemplate>
                <Label x:Name="OrderID" Text="OrderID" TextColor="Black" 
                       BackgroundColor="Yellow" YAlign="Center" />
            </DataTemplate>
        </syncfusion:GridTextColumn.HeaderTemplate>
    </syncfusion:GridTextColumn>
</syncfusion:SfDataGrid.Columns> 
{% endhighlight %}

### Column Width

SfDataGrid allows you to customize the width of each GridColumn in the [SfDataGrid.Columns](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~Columns.html) collection. You can customize the column width by using the [GridColumn.Width](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~Width.html) property. By default this property will not be assigned any value and the GridColumn renders in view based on the value of [DefaultColumnWidth](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~DefaultColumnWidth.html) property in SfDataGrid.

Customizing the width for auto generated columns in both XAML and code behind as shown below.

{% tabs %}
{% highlight xaml %}
<sfgrid:SfDataGrid x:Name="dataGrid"
                   AutoGenerateColumns="false"
    <sfgrid:SfDataGrid.Columns x:TypeArguments="sfgrid:Columns">
      <sfgrid:GridTextColumn MappingName="OrderID"
                             Width="100"/>
      </sfgrid:SfDataGrid.Columns > 
  </sfgrid:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
void dataGrid_AutoGeneratingColumn(object sender, AutoGeneratingColumnArgs e){
if (e.Column.MappingName == "OrderID") {
    e.Column.Width = 100;
    }
}
{% endhighlight %}
{% endtabs %}

## GridTextColumn

GridTextColumn is derived from GridColumn and hence it inherits all the properties of GridColumn. It is used to host the textual content in the record cells. Each of the record cells in GridTextColumn displays the text based on the `MappingName` that associates the column with a property in the data source.

The following code example creates GridTextColumn.

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn MappingName="OrderID" /> 
{% endhighlight %}
{% highlight c# %}
dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
{% endhighlight %}
{% endtabs %}

The below topics explain you about the customizations that can be done in the GridTextColumn in SfDataGrid.

### Formatting

SfDataGrid allows you to format the value displayed in the GridColumn by using the [GridColumn.Format](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~Format.html) property. Assign the FormatString to this property based on the type of the property the GridColumn is associated with to format the value. You can use different [StringFormats](http://msdn.microsoft.com/en-us/library/fbxft59x(v=vs.90).aspx) to customize the value displayed in the record cells.

The following code example shows you how to apply formatting for a GridTextColumn.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid.Columns>
    <syncfusion:GridTextColumn MappingName="Freight" Format="C" />
    <syncfusion:GridTextColumn MappingName="ShippingDate" Format="dd/MM/yyyy" />
</syncfusion:SfDataGrid.Columns> 
{% endhighlight %}
{% highlight c# %}
dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "Freight",
    Format = "C"
});

dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "ShippingDate",
    Format = "dd/MM/yyyy"
});
{% endhighlight %}
{% endtabs %}

N> For AutoGenerated columns the Formatting can be applied by handling the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGeneratingColumn_EV.html) event.

#### Formatting GridTextColumn with different Culture

SfDataGrid allows you to apply different [CultureInfo](https://developer.xamarin.com/api/type/System.Globalization.CultureInfo/) for the GridColumns by using the [GridColumn.CultureInfo](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CultureInfo.html) property. Assign the FormatString to this property based on the type of the property the column is associated with to format the value. You can use different `StringFormats` to customize the value displayed in the record cells.

The following code example shows you how to apply different cultures for the GridColumns.

{% highlight c# %}
dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "Freight",
    Format = "C",
    CultureInfo = new CultureInfo("en-US")
});

dataGrid.Columns.Add (new GridTextColumn () { 
    MappingName = "OrderID",
    Format = "C",
    CultureInfo = new CultureInfo("en-GB")
}); 
{% endhighlight %}

For auto generated columns this is achievable by handling the `SfDataGrid.AutoGeneratingColumn` event. The following code example shows you how to apply different cultures for auto generated GridColumns.

{% highlight c# %}
void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "Freight") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-US");
    } else if (e.Column.MappingName == "OrderID") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-GB");
    }
} 
{% endhighlight %}

### Font and Alignment options

#### CellTextSize

The FontSize for the content of record cells in GridColumn can be customized by using the [GridColumn.CellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CellTextSize.html) property. The default font size of the record cells in SfDataGrid is 14.

#### RecordFont

The FontFamily for the content of header cell in the GridColumn can be customized by using the [GridColumn.RecordFont](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~RecordFont.html) property. The default value font used in SfDataGrid is `Helvetica Neue`.

#### TextAlignment

You can get or set the TextAlignment of the header cell in the GridColumn by using the [GridColumn.TextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~TextAlignment.html) property. The default alignment for the record cells in SfDataGrid is `Center` and you can customize this to `Start` or `End`.

#### LineBreakMode

You can wrap the record cell value when the text for the record cells exceeds the content area by setting [GridColumn.LineBreakMode](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~LineBreakMode.html) as `LineBreakMode.WordWrap` 

The following code example shows how to use GridSwitchColumn.
 
{% tabs %}
{% highlight c# %}
dataGrid.Columns[0].LineBreakMode=LineBreakMode.WordWrap; 
{% endhighlight %}
{% endtabs %}

## GridSwitchColumn

GridSwitchColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn. It loads a switch as a content of record cells in the column and responds to value changes in it. You can change the underlying data source that toggles the values shown in the switch. The SfDataGrid automatically generates GridSwitchColumn if the property in the underlying collection of type bool.

The following code example shows how to use GridSwitchColumn.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:GridSwitchColumn MappingName="IsClosed" />  
{% endhighlight %}
{% highlight c# %}
dataGrid.Columns.Add(new GridSwitchColumn() { MappingName = "IsClosed" }); 
{% endhighlight %}
{% endtabs %}


## GridImageColumn

GridImageColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn. It displays images which as content of record cells in the column. The images loaded inside this column should be added as EmbeddedResource. To create GridImageColumn in SfDataGrid the property corresponding to the column in the underlying collection must be of type ImageSource.

The following code example shows how to use GridImageColumn.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:GridImageColumn MappingName="DealerImage" />  
{% endhighlight %}
{% highlight c# %}
dataGrid.Columns.Add(new GridImageColumn() { MappingName = "DealerImage" });  
{% endhighlight %}
{% endtabs %}


## GridTemplateColumn

GridTemplateColumn is derived from GridColumn, and hence it inherits all the properties of GridColumn. It allows you to extend the functionality of GridColumn with your own view by creating the `CellTemplate` of GridTemplateColumn.

The below table provides the list of properties in GridTemplateColumn.

<table>
<tr>
<th>Property</th>
<th>Type</th>
<th>Description</th>
<th>Default Value</th>
</tr>
<tr>
<td>CellTemplate</td>
<td>DataTemplate</td>
<td>Gets or sets the template that is used to display the contents of the record cells.</td>
<td>Null</td>
</tr>
</table>

The following code example shows templating of GridTemplateColumn. Underlying record will be the BindingContext for the `CellTemplate`.

{% highlight xaml %}
<syncfusion:GridTemplateColumn MappingName="CustomerID">
    <syncfusion:GridTemplateColumn.CellTemplate>
        <DataTemplate>
            <Label Text="{Binding CustomerID}" TextColor="Black" 
                   XAlign="Center" YAlign="Center" />
        </DataTemplate>
    </syncfusion:GridTemplateColumn.CellTemplate>
</syncfusion:GridTemplateColumn> 
{% endhighlight %}

The following code example illustrates how template column can be used to load a stock cell inside it.

{% highlight xaml %}
<ContentPage.Resources>
    <ResourceDictionary>
        <local:ImageConverter x:Key="imageConverter" /> 
    </ResourceDictionary>
</ContentPage.Resources>

<ContentPage.ContentView>
    <syncfusion:SfDataGrid x:Name="dataGrid"
                           ColumnSizer="Star">

        <syncfusion:SfDataGrid.Columns>
            <syncfusion:GridTemplateColumn HeaderText="Stock Change"
                                           MappingName="StockChange">
                <syncfusion:GridTemplateColumn.CellTemplate>
                    <DataTemplate>
                        <Grid>
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="Auto" />
                                <ColumnDefinition Width="*" />
                            </Grid.ColumnDefinitions>
                            <Image Grid.Column="0"
                                   Source="{Binding StockChange,
                                   Converter={StaticResource imageConverter}}" />
                            <Label x:Name="changeValue" Grid.Column="1"
                                   Text="{Binding StockChange}" TextColor="Black"
                                   XAlign="Center" YAlign="Center">
                            </Label>
                        </Grid>
                    </DataTemplate>
                </syncfusion:GridTemplateColumn.CellTemplate>
            </syncfusion:GridTemplateColumn>
        </syncfusion:SfDataGrid.Columns>
    </syncfusion:SfDataGrid>
</ContentPage.ContentView>
{% endhighlight %}

In order to get the above code example working, you need to write a converter to load the images inside GridCell based on the CellValue. The images that has to be loaded inside the GridCell must be added as EmbeddedResource.

The following code example shows you converter code for loading the images in a template column.

{% highlight c# %}
public class ImageConverter:IValueConverter
{
    public object Convert (object value, Type targetType, object parameter, CultureInfo culture)
    {
        var data = value as double?;
        if (data != null && data > 0)
            return ImageSource.FromResource("DataGridSample.Icons.Green.png");
        else
            return ImageSource.FromResource("DataGridSample.Icons.Red.png");
    }

    public object ConvertBack (object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException ();
    }
} 
{% endhighlight %}

The following screenshot shows the different types of columns in SfDataGrid
![](SfDataGrid_images/SfDataGrid-Xamarin_showcase1.png)

![](SfDataGrid_images/TemplateColumns2.png)

