---
layout: post
title: Summary | SfDataGrid | Xamarin | Syncfusion
description: How to apply summaries for the elements in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Summary

SfDataGrid provides support to display the concise information about the bound data objects using summaries. SfDataGrid provides below summary types.

* **Table Summary** - Used to display the summary information of SfDataGrid either at top or bottom or at both of SfDataGrid.

* **Caption Summary** - Used to display the summary information in the caption of the group.

![](SfDataGrid_images/Summary_img1.png)

Summary rows are represented by using [GridSummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow.html) and each `GridSummaryRow` hold summary information of columns in [SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~SummaryColumns.html) property . The `SummaryColumns` contains the collection of [GridSummaryColumn](http://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn.html) which carries the name of column ,format and its summary aggregate type.

You can derive additional information from your data like sum, average, maximum, minimum and count using summaries in SfDataGrid. These summary values are computed for groups or total SfDataGrid using `GridSummaryRow` and `GridSummaryColumn` that implements [ISummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ISummaryRow.html) and [ISummaryColumn](http://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ISummaryColumn.html) interface.

N> Summary does not refresh with data. To update the summary for the newly added row or column, set the `SfDataGrid.View.LiveDataUpdateMode` to `LiveDataUpdateMode.AllowSummaryUpdate`.

## Table Summaries

SfDataGrid provides built-in support for table summaries. The table summary value calculated based on all the records in SfDataGrid. SfDataGrid allows you to add any number of table summary rows either at top or bottom or at both of SfDataGrid.

You can add table summary row in SfDataGrid by adding `GridTableSummaryRow` to `TableSummaryRows` collection.

Below screenshot illustrates the table summary rows in SfDataGrid.

![](SfDataGrid_images/Summary_img2.png)

You can also able to add more than one table summary rows either at top or bottom or at both positions in SfDataGrid.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.TableSummaryRows>
    <sfgrid:GridTableSummaryRow Title="Total Salary :{TotalSalary} for {ProductCount} members"
                                Position="Top"
                                ShowSummaryInRow="True">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            <sfgrid:GridSummaryColumn Name="ProductCount"
                                      Format="{}{Count}"
                                      MappingName="Salary"
                                      SummaryType="CountAggregate" />
            </sfgrid:GridTableSummaryRow.SummaryColumns>
        </sfgrid:GridTableSummaryRow>
    <sfgrid:GridTableSummaryRow Position="Top" ShowSummaryInRow="True">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            </sfgrid:GridTableSummaryRow.SummaryColumns>
        </sfgrid:GridTableSummaryRow>
</sfgrid:SfDataGrid.TableSummaryRows>
{% endhighlight %}

{% highlight c#%}
GridTableSummaryRow summaryRow1 = new GridTableSummaryRow();
summaryRow1.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow1.ShowSummaryInRow = true;
summaryRow1.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow1.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfgrid.TableSummaryRows.Add(summaryRow1);

GridTableSummaryRow summaryRow2 = new GridTableSummaryRow();
summaryRow2.ShowSummaryInRow = false;
summaryRow2.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.TableSummaryRows.Add(summaryRow2);
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Summary_img3.png)

### Defining summary for row

You can display summary information in a row by setting [GridTableSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~ShowSummaryInRow.html) to `true` and defining summary columns. You have to define [GridTableSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~Title.html) based on [GridSummaryColumn.Name](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~Name.html) property to format summary columns values in a row.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.TableSummaryRows>
    <sfgrid:GridTableSummaryRow Title="Total Salary :{TotalSalary} for {ProductCount} members"
                                ShowSummaryInRow="True">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            <sfgrid:GridSummaryColumn Name="ProductCount"
                                      Format="{}{Count}"
                                      MappingName="Salary"
                                      SummaryType="CountAggregate" />
            </sfgrid:GridTableSummaryRow.SummaryColumns>
        </sfgrid:GridTableSummaryRow>
</sfgrid:SfDataGrid.TableSummaryRows>
{% endhighlight %}

{% highlight c#%}
GridTableSummaryRow summaryRow = new GridTableSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfgrid.TableSummaryRows.Add(summaryRow);
{% endhighlight %}
{% endtabs %}

The following screenshot shows the table summary row if `ShowSummaryInRow` is `true`.

![](SfDataGrid_images/Summary_img4.png)

### Defining summary for column

You can display summary information in the column by setting `GridTableSummaryRow.ShowSummaryInRow` to `false` and defining summary columns. `GridSummaryColumn` is the object of [GridTableSummaryRow.SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~SummaryColumns.html) collection that contains the following important properties:

* [Name](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Name.html): Defines name of the `GridSummaryColumn` that helps to denote the `GridSummaryColumn` in `GridTableSummaryRow` with Title.

* [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~MappingName.html): The corresponding column name that is used for the summary calculation.

* [SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~SummaryType.html): It is the `SummaryType` (enum) property that helps to define the aggregate type for the summary calculation. SfDataGrid
control provides the following predefined aggregates.

  * CountAggregate
  * Int32Aggregate
  * DoubleAggregate

* [CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~CustomAggregate.html): Defines the `CustomAggregate` class object when the summary type is set as `Custom` that calculates the custom summaries.

* [Format](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Format.html): `String` property that formats the summary value and displays it. `Format` property contains two parts that are separated by a colon (:). First part denotes the aggregate function name and second part denotes display format of the summary value.

Refer [Formatting Summary](#_Formatting_Summary) section to know more about how to format summary and [Aggregate Types](#_Aggregate_Types) section to know about different summary types.

In the below code snippet, summary is defined for `Salary` column.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.TableSummaryRows>
    <sfgrid:GridTableSummaryRow Name="TableSummary" ShowSummaryInRow="False">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TableSummary"
                                      Format="{}{Sum}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
        </sfgrid:GridTableSummaryRow.SummaryColumns>
    </sfgrid:GridTableSummaryRow>
</sfgrid:SfDataGrid.TableSummaryRows>
{% endhighlight %}

{% highlight c#%}
GridTableSummaryRow summaryRow = new GridTableSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TableSummary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.TableSummaryRows.Add(summaryRow);
{% endhighlight c#%}
{% endtabs %}

The following screenshot shows the table summary row if `ShowSummaryInRow` is `false`.

![](SfDataGrid_images/Summary_img5.png)

### Positioning TableSummaryRows

SfDataGrid allows you to add table summary rows either at top or bottom positions using [GridTableSummaryRow.Position](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTableSummaryRow~Position.html) property.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.TableSummaryRows>
    <sfgrid:GridTableSummaryRow Position="Top"
                                ShowSummaryInRow="False">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            </sfgrid:GridTableSummaryRow.SummaryColumns>
        </sfgrid:GridTableSummaryRow>
    <sfgrid:GridTableSummaryRow Position="Bottom"
                                ShowSummaryInRow="True"
                                Title="Total Salary :{TotalSalary} for {ProductCount} members">
        <sfgrid:GridTableSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            <sfgrid:GridSummaryColumn Name="ProductCount"
                                      Format="{}{Count}"
                                      MappingName="Salary"
                                      SummaryType="CountAggregate" />
        </sfgrid:GridTableSummaryRow.SummaryColumns>
    </sfgrid:GridTableSummaryRow>
</sfgrid:SfDataGrid.TableSummaryRows>
{% endhighlight %}

{% highlight c#%}
GridTableSummaryRow topSummaryRow = new GridTableSummaryRow();
topSummaryRow.Position = Position.Top;
topSummaryRow.ShowSummaryInRow = false;
topSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.TableSummaryRows.Add(topSummaryRow);

GridTableSummaryRow bottomSummaryRow = new GridTableSummaryRow();
bottomSummaryRow.Position = Position.Bottom;
bottomSummaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
bottomSummaryRow.ShowSummaryInRow = true;
bottomSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
bottomSummaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfgrid.TableSummaryRows.Add(bottomSummaryRow);
{% endhighlight %}
{% endtabs %}

The below screenshot illustrates the positioning of table summary rows in SfDataGrid.

![](SfDataGrid_images/Summary_img6.png)


## Caption Summaries

SfDataGrid provides built-in support for caption summaries. The caption summary value calculated based on the records in a group and the summary information will be displayed in the caption of group.

Below screenshot shows the built-in caption summary of a group.

![](SfDataGrid_images/Summary_img7.png)


### Formatting built-in caption summary

By default, the summary value displayed in caption summary rows based on [SfDataGrid.GroupCaptionTextFormat](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupCaptionTextFormat.html) property.

The default group caption format is `{ColumnName}: {Key} - {ItemsCount} Items`.

* **ColumnName** - Displays the name of the column currently grouped.

* **Key** - Displays the key value of the group.

* **ItemsCount** - Displays the number of items in a group.

![](SfDataGrid_images/Summary_img8.png)

You can customize this group caption text format by setting the `SfDataGrid.GroupCaptionTextFormat` property. The following code example illustrates how to customize group caption text in SfDataGrid.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid x:Name="dataGrid"
                   AutoGenerateColumns="True"
                   ColumnSizer="Star"
                   GroupCaptionTextFormat="{}{ColumnName}: {Key}">
{% endhighlight %}

{% highlight c#%}
//Customized group caption text
dataGrid.GroupCaptionTextFormat = "{ColumnName} : {Key}";
{% endhighlight %}
{% endtabs %}

Below screenshot shows the final outcome of the above code.

![](SfDataGrid_images/Summary_img9.png)


### Defining summary for row

You can display summary information in a row by setting [GridSummaryRow.ShowSummaryInRow](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~ShowSummaryInRow.html) to `true` and defining summary columns. You have to define [GridSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~Title.html) based on [GridSummaryColumn.Name](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~Name.html) property to format summary columns values in a row.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow Title="Total Salary :{TotalSalary} for {ProductCount} members"
                           ShowSummaryInRow="True">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            <sfgrid:GridSummaryColumn Name="ProductCount"
                                      Format="{}{Count}"
                                      MappingName="Salary"
                                      SummaryType="CountAggregate" />
            </sfgrid:GridSummaryRow.SummaryColumns>
        </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.CountAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}
{% endtabs %}

The following screenshot shows the final outcome for both values of `ShowSummaryInRow` to `true`.

![](SfDataGrid_images/Summary_img10.png)


### Defining summary for column

You can display summary information in the column by setting `GridSummaryRow.ShowSummaryInRow` to `false` and defining summary columns. `SfDataGrid.GridSummaryColumn` is the object of [GridSummaryRow.SummaryColumns](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~SummaryColumns.html) collection that contains the following important properties:

* [Name](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Name.html): Defines name of the `GridSummaryColumn` that helps to denote the `GridSummaryColumn` in `GridSummaryRow` with Title.

* [MappingName](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~MappingName.html): The corresponding column name that is used for the summary calculation.

* [SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~SummaryType.html): It is the `SummaryType` (enum) property that helps to define the aggregate type for the summary calculation. `DataGrid` 
control provides the following predefined aggregates.

  * CountAggregate
  * Int32Aggregate
  * DoubleAggregate

* [CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~CustomAggregate.html): Defines the `CustomAggregate` class object when the summary type is set as `Custom` that calculates the custom summaries.

* [Format](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~Format.html): `String` property that formats the summary value and displays it. `Format` property contains two parts that are separated by a colon (:). First part denotes the aggregate function name and second part denotes display format of the summary value.

Refer [Formatting Summary](#_Formatting_Summary) section to know more about how to format summary and [Aggregate Types](#_Aggregate_Types) section to know about different summary types.

In the below code snippet, summary is defined for `Salary` column.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow Name="CaptionSummary" ShowSummaryInRow="False">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="CaptionSummary"
                                      Format="{}{Sum}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight c#%}
{% endtabs %}

![](SfDataGrid_images/Summary_img11.png)


## Formatting Summary

In the below sections formatting is explained using `CaptionSummary`.

### Defining Summary Function
In the below code snippet `Format` property is defined to display sum of `Salary` by specifying the function name inside curly braces.

N> `DoubleAggregate` is used as `SummaryType` which has the count, max, min, average and sum functions.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow ShowSummaryInRow="False">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="CaptionSummary"
                                      Format="{}{Sum}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight c#%}
{% endtabs %}

![](SfDataGrid_images/Summary_img12.png)


### Formatting Summary Value

You can format the summary value by setting the appropriate format after the aggregate function followed by a colon(:) in `GridSummaryColumn.Format` property.

In the below code snippet `Salary` column summary is formatted using `c` format specifier. Refer [here](https://msdn.microsoft.com/en-us/library/dwhawy9k.aspx?f=255&MSPPError=-2147217396) to know about how to set different format.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow ShowSummaryInRow="False">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="CaptionSummary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Summary_img13.png)


### Displaying additional Content in Summary

You can append additional content with summary value using `GridSummaryColumn.Format` property.

In the below code snippet `Total :` text is appended before summary value.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow ShowSummaryInRow="False">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="CaptionSummary"
                                      Format="Total: {Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.ShowSummaryInRow = false;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "CaptionSummary",
    MappingName = "Salary",
    Format = "Total:{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Summary_img14.png)

 
### Formatting Summary for Row using Title property

You can format the summary value for row using [GridSummaryRow.Title](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryRow~Title.html) when `ShowSummaryInRow` set to `true`.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow Title="Total Salary:{TotalSalary} for {ProductCount} members" ShowSummaryInRow="True">
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="TotalSalary"
                                      Format="{}{Sum:c}"
                                      MappingName="Salary"
                                      SummaryType="DoubleAggregate" />
            <sfgrid:GridSummaryColumn Name="ProductCount"
                                      Format="{}{Count}"
                                      MappingName="Salary"
                                       SummaryType="CountAggregate" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Total Salary:{TotalSalary} for {ProductCount} members";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "TotalSalary",
    MappingName = "Salary",
    Format = "{Sum:c}",
    SummaryType = SummaryType.DoubleAggregate
});
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
{
    Name = "ProductCount",
    MappingName = "Salary",
    Format = "{Count}",
    SummaryType = SummaryType.DoubleAggregate
});
sfgrid.CaptionSummaryRow= summaryRow;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Summary_img15.png)


## Aggregate Types

You can specify the different summary aggregate types by using [GridSummaryColumn.SummaryType](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~SummaryType.html) property and use the built-in function in `GridSummaryColumn.Format`.

The following are the list of predefined aggregate types and its built-in functions.

<table>
<tr>
<th>
Aggregate Type
</th>
<th>
Built-in function
</th>
</tr>
<tr>
<td>
CountAggregate
</td>
<td>
Count
</td>
</tr>
<tr>
<td>
Int32Aggregate
</td>
<td>
Count, Max, Min, Average and Sum
</td>
</tr>
<tr>
<td>
DoubleAggregate
</td>
<td>
Count, Max, Min, Average and Sum
</td>
</tr>
<tr>
<td>
Custom
</td>
<td>
Used for Custom Summaries
</td>
</tr>
</table>


## Custom Summaries

SfDataGrid allows you to implement your own aggregate functions, when the built-in aggregate functions do not meet your requirement.

You can calculate the summary values based on custom logic using [GridSummaryColumn.CustomAggregate](https://help.syncfusion.com/cr/cref_files/xamarin/sfdatagrid/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridSummaryColumn~CustomAggregate.html) property.


### Implementing custom aggregate

1. Create a custom aggregate class by deriving from [ISummaryAggregate](https://help.syncfusion.com/cr/cref_files/xamarin/data/Syncfusion.Data.Portable~Syncfusion.Data.ISummaryAggregate.html) interface.
2. In the `CalculateAggregateFunc()` method, you have to calculate the summary and assign it to the property.

In the below code snippet, `Standard Deviation` is calculated for quantity of products.

{% highlight c#%}
public class CustomAggregate : ISummaryAggregate
{
    public CustomAggregate()
    {
    }
    public double StdDev { get; set; }
    public Action<System.Collections.IEnumerable, string, System.ComponentModel.PropertyDescriptor> CalculateAggregateFunc()
    {
        return (items, property, pd) =>
        {
            var enumerableItems = items as IEnumerable<OrderInfo>;
            if (pd.Name == "StdDev")
            {
                this.StdDev = enumerableItems.StdDev<OrderInfo>(q => q.OrderID);
            }
        };
    }
}

public static class LinqExtensions
{
    public static double StdDev<T>(this IEnumerable<T> values, Func<T, double?> selector)
    {
        double ret = 0;
        var count = values.Count();
        if (count > 0)
        {
            double? avg = values.Average(selector);
            double sum = values.Select(selector).Sum(d =>
            {
                if (d.HasValue)
                {
                    return Math.Pow(d.Value - avg.Value, 2);
                }
                return 0.0;
            });
            ret = Math.Sqrt((sum) / (count - 1));
        }
        return ret;
    }
}
{% endhighlight %}

Assign the custom aggregate to `GridSummaryColumn.CustomAggregate` property and set the `SummaryType` as `Custom`. `GridSummaryColumn.Format` property is defined based on property name in custom aggregate `StdDev`.

{% tabs %}
{% highlight xaml%}
<sfgrid:SfDataGrid.CaptionSummaryRow>
    <sfgrid:GridSummaryRow Title="Standard Deviation:{CaptionSummary}" ShowSummaryInRow = "True">                                                     
        <sfgrid:GridSummaryRow.SummaryColumns>
            <sfgrid:GridSummaryColumn Name="CaptionSummary"
                                      CustomAggregate="{StaticResource customAggregate}"
                                      Format="{}{StdDev}"
                                      MappingName="OrderID"
                                      SummaryType="Custom" />
        </sfgrid:GridSummaryRow.SummaryColumns>
    </sfgrid:GridSummaryRow>
</sfgrid:SfDataGrid.CaptionSummaryRow>
{% endhighlight %}

{% highlight c#%}
GridSummaryRow summaryRow = new GridSummaryRow();
summaryRow.Title = "Standard Deviation:{CaptionSummary}";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn
{
    Name = "CaptionSummary",
    CustomAggregate  = new CustomAggregate(),
    MappingName = "OrderID",
    Format = "{StdDev}",
    SummaryType = Syncfusion.Data.SummaryType.Custom
});
dataGrid.CaptionSummaryRow = summaryRow;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Summary_img16.png)

You can download the sample demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SummaryDemo610629184) .
