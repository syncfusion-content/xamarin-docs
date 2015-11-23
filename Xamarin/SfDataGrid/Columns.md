---
layout: post
title: Columns | SfDataGrid | Xamarin | Syncfusion
description: Columns
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Columns 

This section explains you about how to create and add columns, different ways to create columns and about the customizations that can done for a column.
**SfDataGrid** allows you to create and add Columns in two ways:

* Automatic Columns generation based on the underlying collection.
* Manually defining columns in XAML or C#.

## Automatic Columns Generation

The **SfDataGrid** creates columns automatically based on the property **SfDataGrid.AutoGenerateColumns**. **SfDataGrid.AutoGenerateColumns** is a bindable property and it decides columns generation for **SfDataGrid** based on the **SfDataGrid.AutoGenerateColumnsMode** property. 
**SfDataGrid.AutoGenerateColumnsMode** decides a way to create columns when **SfDataGrid.AutoGenerateColumns** is set to ‘true’. This enum type has the following four options.

* Reset: Retains the columns defined explicitly in application level and creates columns newly for all the other properties in a Data Source.
* ResetAll: When changing ItemsSource, the columns for previous data are cleared and it creates new columns. Even when columns are explicitly defined it does not consider the defined columns and creates column based on the underlying collection.
* RetainOld: Creates columns for all fields in a Data Source when the Grid does not have any explicit definition for columns. When columns are defined explicitly, then the defined columns alone are retained and new columns are not created.
* SmartReset: Retains the columns defined explicitly in application level and the columns with MappingName identical to properties in a Data Source. Creates columns newly for all the other properties in the Data Source.
* None: Stores only the columns that are defined in **SfDataGrid.Columns** collection.

The default value of **SfDataGrid.AutoGenerateColumns** property is true and **SfDataGrid.AutoGenerateColumnsMode** is Reset. Hence by default **SfDataGrid** creates columns automatically for every non-explicitly defined public property in the underlying collection bound to its ItemsSource property.

N> When you change items source for **SfDataGrid** during run time, then the columns are generated on the basis of option set for AutoGenerateColumnsMode.

### Customize Automatically Generated Columns

When AutoGenerateColumns is true, then **SfDataGrid.AutoGeneratingColumn** event is raised for each column. This event receives two arguments namely sender which is the **SfDataGrid** and AutoGeneratingColumnArgs.
The AutoGeneratingColumnArgs object contains the following property:

* Column: This property returns the created column using which you can customize the column.
* Cancel: This property cancels the column creation.

You can skip generating a column by handling the **SfDataGrid.AutoGeneratingColumn** event as shown below.

{% highlight c# %}
dataGrid.AutoGeneratingColumn += GridAutoGeneratingColumns; 

void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "EmployeeID")
    e.Cancel = true;
}
{% endhighlight %}

You can also apply formatting for auto generated column as shown below.

{% highlight c# %}
void GridAutoGeneratingColumns(object sender, AutoGeneratingColumnArgs e)
{
    if (e.Column.MappingName == "Freight") {
        e.Column.Format = "C";
        e.Column.CultureInfo = new CultureInfo ("en-US");
    } else if (e.Column.MappingName == "ShippingDate")
        e.Column.Format = "dd/MM/yyyy";
} 
{% endhighlight %}

You can also customize a column’s header text, sorting, alignment, padding, etc. by handling the **SfDataGrid.AutoGeneratingEvent**.

## Manually generate Columns

**SfDataGrid** also allows you to define the columns manually by adding the GridColumn objects to the **SfDataGrid.Columns** collection. In case if you want only the manually defined columns to be in view, then you can achieve it by setting the **SfDataGrid.AutoGenerateColumns** property to false. There are different [types of columns](#Column-Types-–-Forms) available in **SfDataGrid** and you can create any column based on your requirements from both XAML and code.
 
The following code example illustrates about creating columns manually using XAML.

{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
            ColumnSizer="Star"
            AutoGenerateColumns="False"
            ItemsSource="{Binding OrderInfoCollection}">

    <syncfusion:SfDataGrid.Columns x:TypeArguments="syncfusion:Columns">
        <syncfusion:GridTextColumn HeaderText="Order ID" 
                                   MappingName="OrderID" />
        <syncfusion:GridTextColumn HeaderText="Customer ID"
                                   MappingName="CustomerID" />
        <syncfusion:GridTextColumn MappingName="Customer" />
        <syncfusion:GridTextColumn HeaderText="Ship Country"
                                   MappingName="ShipCountry" />
    </syncfusion:SfDataGrid.Columns>
</syncfusion:SfDataGrid>
{% endhighlight %}

The following code example illustrates about creating columns manually through C#.

{% highlight c# %}
dataGrid.AutoGenerateColumns = false;

GridTextColumn orderIdColumn = new GridTextColumn ();
orderIdColumn.MappingName = "OrderID";
orderIdColumn.HeaderText = "Order ID";

GridTextColumn customerIdColumn = new GridTextColumn ();
customerIdColumn.MappingName = "CustomerID";
customerIdColumn.HeaderText = "Customer ID";

GridTextColumn customerColumn = new GridTextColumn ();
customerColumn.MappingName = "Customer";

GridTextColumn countryColumn = new GridTextColumn ();
countryColumn.MappingName = "ShipCountry";
countryColumn.HeaderText = "Ship Country";

dataGrid.Columns.Add (orderIdColumn);
dataGrid.Columns.Add (customerIdColumn);
dataGrid.Columns.Add (customerColumn);
dataGrid.Columns.Add (countryColumn); 
{% endhighlight %}
