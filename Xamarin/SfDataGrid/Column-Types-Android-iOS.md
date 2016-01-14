---
layout: post
title: Column Types - Android & iOS | SfDataGrid | Xamarin | Syncfusion
description: What are all the different types of column and it's properties and customizations in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Column Types in Xamarin.Android & Xamarin.iOS

This section explains you the different types of column and the customizations that can done for a column.

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) contains two types of column each with its own functionalities. You can use any column based on your requirements.
 
The below table describes you the types of column and its purpose of usage in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

<table>
<tr>
<th>Column Type</th>
<th>Description</th>
</tr>
<tr>
<td>GridColumn</td>
<td>Abstract class. Base column type of all the columns in the {{ '**SfDataGrid**' | markdownify }}.</td>
</tr>
<tr>
<td>GridTextColumn</td>
<td>To be used to display string or numbers in each row.</td>
</tr>
<tr>
<td>TemplateColumn (i.e. GridTextColumn with UserCellType)</td>
<td>To be used when you want to customize your column based on your requirements.</td>
</tr>
</table>


## GridColumn

[GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) is the base column type of all the columns in the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), hence [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) properties are used by all the columns. The following sub-sections explains you about the properties in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) and the customizations that can be done using those properties.

### MappingName

[GridColumn.MappingName](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~MappingName.html) associates the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) with a property available in the underlying data source. While setting MappingName alone to the [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), [GridColumn.DisplayBinding](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~DisplayBinding.html) will be automatically generated based on the MappingName. Data Manipulation operations like sorting, filtering, grouping will be done based on the MappingName property.

### Header customizations

#### HeaderCellTextSize

The FontSize for the content of header cell in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) can be customized by using the [GridColumn.HeaderCellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderCellTextSize.html) property. The default font size of the header cells in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is 14.

#### HeaderFont

The FontFamily for the content of header cell in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) can be customized by using the [GridColumn.HeaderFont](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderFont.html) property. The default value font used in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is “Roboto-Bold” for Android and “Helvetica-Bold” in iOS.

#### HeaderText

[GridColumn.HeaderText](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderText.html) specifies the text displayed in the column header. If HeaderText is not defined, the [GridColumn.MappingName](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~MappingName.html) will be assigned to the HeaderText and will be displayed as column header.

#### HeaderTextAlignment
You can get or set the TextAlignment of the header cell in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) by using the [GridColumn.HeaderTextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderTextAlignment.html) property. The default alignment for the header cells in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is “Center”.


## GridTextColumn

[GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html) is derived from [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) and hence it inherits all the properties of [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html). Each of the record cells in [GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html) displays text based on the MappingName which associates the column with a property in the data source.

The following code example creates [GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html).

{% highlight c# %}
dataGrid.Columns.Add(new GridTextColumn() { MappingName = "OrderID" });
{% endhighlight %}

The below topics explain you about the customizations that can be done in the [GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html) in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html).

### Formatting

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to format the value displayed in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) by using the [GridColumn.Format](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~Format.html) property. Assign the FormatString to this property based on the type of the property the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) is associated with to format the value. You can use different [StringFormats](http://msdn.microsoft.com/en-us/library/fbxft59x(v=vs.90).aspx) to customize the value displayed in the record cells.

The following code example shows you how to apply formatting for a [GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html) in code.

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

N> For AutoGenerated columns the Formatting can be applied by handling the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGeneratingColumn_EV.html) event.

#### Formatting GridTextColumn with different Culture

[SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) allows you to apply different [CultureInfo](https://developer.xamarin.com/api/type/System.Globalization.CultureInfo/) for the GridColumns by using the [GridColumn.CultureInfo](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CultureInfo.html) property. Assign the FormatString to this property based on the type of the property the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) is associated with to format the value. You can use different [StringFormats](http://msdn.microsoft.com/en-us/library/fbxft59x(v=vs.90).aspx) to customize the value displayed in the record cells.

The following code example shows you how to apply different cultures for a GridColumns.

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

For auto generated columns this is achievable by handling the [SfDataGrid.AutoGeneratingColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AutoGeneratingColumn_EV.html) event. The following code example shows you how to apply different cultures for auto generated GridColumns.

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

The FontSize for the content of record cells in [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) can be customized by using the [GridColumn.CellTextSize](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CellTextSize.html) property. The default font size of the record cells in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is 14.

#### RecordFont

The FontFamily for the content of header cell in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) can be customized by using the [GridColumn.RecordFont](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~RecordFont.html) property. The default value font used in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is “Roboto-Regular” for Android and “HelveticaNeue” for iOS.

#### TextAlignment

You can get or set the TextAlignment of the header cell in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) by using the [GridColumn.TextAlignment](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~TextAlignment.html) property. The default alignment for the record cells in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html) is “Center”.


## TemplateColumn

TemplateColumn is actually the [GridTextColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTextColumn.html) with **UserCellType** specified and hence it inherits all the properties of [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html). It allows you to extend the functionality of GridColumns with your own view by creating custom GridCell to render in the column.

The following code example shows how to create a TemplateColumn.

{% highlight c# %}
GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.UserCellType = typeof(CustomCell);
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";
dataGrid.Columns.Add(customerIdColumn);
{% endhighlight %}

In order to create a template column in [SfDataGrid](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid.html), you need to specify the UserCellType of the column. UserCellType is the type of the view to be used in the [GridColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) and it must be derived from the [GridCell](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCell.html). (i.e. a custom [GridCell](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCell.html) which hosts the view of your own requirement).
 
The following code example shows you how to create a custom [GridCell](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCell.html) and use it in a template column.

{% highlight c# %}
//Creating a Template Column 
GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.UserCellType = typeof(CustomCell);
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";
dataGrid.Columns.Add(customerIdColumn);

//Creating Custom GridCell in Android 
public class CustomCell : GridCell
{
    TextView textView;

    public CustomCell (Context context) : base (context)
    {
        textView = new TextView (this.Context);
        this.AddView (textView);
        this.CanRenderUnLoad = false;
    }

    protected override void UnLoad ()
    {
        if (this.Parent != null)
        (this.Parent as VirtualizingCellsControl).RemoveView (this);
    }

    protected override void OnLayout(bool change, int l, int t, int r, int b)
    {
        this.textView.Layout (0, 0, this.Width, this.Height);
    }

    protected override void OnDraw (Canvas canvas)
    {
        base.OnDraw (canvas);
        this.textView.Text = DataColumn.CellValue.ToString ();
    }
}

//Creating Custom GridCell in iOS
public class CustomCell : GridCell
{
    UILabel label;

    public CustomCell ()
    {
        label = new UILabel ();
        this.Add (label);
        this.CanRenderUnLoad = false;
    }

    protected override void UnLoad ()
    {
        this.RemoveFromSuperview (this);
    }

    protected override void LayoutSubviews ()
    {
        base.LayoutSubviews ();
        this.label.Frame (Bounds.Left, Bounds.Top, Bounds.Width, Bounds.Height);
        this.label.Text = DataColumn.CellValue.ToString ();
    }
}
{% endhighlight %}

