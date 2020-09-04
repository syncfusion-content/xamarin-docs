---
layout: post
title: Filtering | SfDataGrid | Xamarin | Syncfusion
description: Filter the records in view using the properties in Xamarin.Forms DataGrid by simply setting a predicate to the view. 
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Filtering

The SfDataGrid supports to view filtering.

## View Filtering

The SfDataGrid supports to filter the records in view by setting `SfDataGrid.View.Filter` property where `Filter` is a `predicate`.

In order to filter the records, assign the filtered strings to the `ViewModel.FilterText` property which will be later applied in `FilterPredicate` that is assigned to `SfDataGrid.View.Filter` in OnFilterChanged() method.

N> To update filtering for newly added row or column, set the `SfDataGrid.View.LiveDataUpdateMode` to `LiveDataUpdateMode.AllowDataShaping`.

The following code example illustrates the delegate, properties, and methods used in the `ViewModel` class in order to perform filtering operation:

{% highlight c# %}
// ViewModel.cs

#region Filtering

#region Fields

private string filterText = "";
private string selectedColumn = "All Columns";
private string selectedCondition = "Equals";
internal delegate void FilterChanged();
internal FilterChanged filterTextChanged;

#endregion

#region Property

public string FilterText
{
    get { return filterText; }
    set
    {
        filterText = value;
        OnFilterTextChanged();
        RaisePropertyChanged("FilterText");
    }
}

public string SelectedCondition
{
    get { return selectedCondition; }
    set { selectedCondition = value; }
}

public string SelectedColumn
{
    get { return selectedColumn; }
    set { selectedColumn = value; }
}

#endregion

#region Private Methods

private void OnFilterTextChanged()
{
    filterTextChanged();
}

private bool MakeStringFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    exactValue = exactValue.ToString().ToLower();
    string text = FilterText.ToLower();
    var methods = typeof(string).GetMethods();
    if (methods.Count() != 0)
    {
        if (condition == "Contains")
        {
            var methodInfo = methods.FirstOrDefault(method => method.Name == condition);
            bool result1 = (bool)methodInfo.Invoke(exactValue, new object[] { text });
            return result1;
        }
        else if (exactValue.ToString() == text.ToString())
        {
            bool result1 = String.Equals(exactValue.ToString(), text.ToString());
            if (condition == "Equals")
                return result1;
            else if (condition == "NotEquals")
                return false;
        }
        else if (condition == "NotEquals")
        {
            return true;
        }
        return false;
    }
    else
        return false;
}

private bool MakeNumericFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    double res;
    bool checkNumeric = double.TryParse(exactValue.ToString(), out res);
    if (checkNumeric)
    {
        switch (condition)
        {
            case "Equals":
                try
                {
                    if (exactValue.ToString() == FilterText)
                    {
                        if (Convert.ToDouble(exactValue) == (Convert.ToDouble(FilterText)))
                            return true;
                    }
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                }
                break;
            case "NotEquals":
                try
                {
                    if (Convert.ToDouble(FilterText) != Convert.ToDouble(exactValue))
                        return true;
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                        return true;
                }
                break;
        }
    }
    return false;
}

#endregion

#region Public Methods

public bool FilerRecords(object o)
{
    double res;
    bool checkNumeric = double.TryParse(FilterText, out res);
    var item = o as OrderInfo;
    if (item != null && FilterText.Equals(""))
    {
        return true;
    }
    else
    {
        if (item != null)
        {
            if (checkNumeric && !SelectedColumn.Equals("All Columns"))
            {
                bool result = MakeNumericFilter(item, SelectedColumn, SelectedCondition);
                    return result;
            }
            else if (SelectedColumn.Equals("All Columns"))
            {
                if (item.CustomerID.ToLower().Contains(FilterText.ToLower()) ||
                    item.Country.ToLower().Contains(FilterText.ToLower()) || 
                    item.Freight.ToString().ToLower().Contains(FilterText.ToLower()) ||                           
                    item.OrderID.ToString().ToLower().Contains(FilterText.ToLower()))
                    return true;
                return false;
            }
            else
            {
                bool result = MakeStringFilter(item, SelectedColumn, SelectedCondition);
                return result;
            }
        }
    }
    return false;
}

#endregion

#endregion
{% endhighlight %}

To create a `SearchBar` and apply the filtered records to `ViewModel.FilterText` property in `SearchBar.TextChanged` event, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage.BindingContext>
    <local:ViewModel x:Name="viewModel" />
</ContentPage.BindingContext>

<SearchBar x:Name="filterText"
           Grid.Row="0"
           Grid.Column="0"
           IsVisible="true"
           Placeholder="Search here to Filter"
           TextChanged="OnFilterTextChanged" />
{% endhighlight %}
{% highlight c# %}
private void OnFilterTextChanged(object sender, TextChangedEventArgs e)
{
    if (e.NewTextValue == null)
        viewModel.FilterText = "";
    else
        viewModel.FilterText = e.NewTextValue;
}
{% endhighlight %}
{% endtabs %}

![DataGrid with filtered data](SfDataGrid_images/Filtering_Img1.png)

Once you create a `SearchBar` and a view model, filtering can be performed by setting `SfDataGrid.View.Filter` property. Call the `SfDataGrid.View.RefreshFilter()` method after setting the filtered records to the `SfDataGrid.View.Filter` property as in the following code example:

{% highlight c# %}
// Code-Behind

viewModel.filterTextChanged = OnFilterChanged; //where ‘filterTextChanged’ is a delegate declared in ViewModel class.

private void OnFilterChanged()
{
    if (dataGrid.View != null)
    {
        this.dataGrid.View.Filter = viewModel.FilerRecords;
        this.dataGrid.View.RefreshFilter();
    }
}
{% endhighlight %}

## Applying RowFilter of DataTable to DataGrid

To filter the rows in SfDataGrid using [DataView.RowFilter](https://docs.microsoft.com/en-us/dotnet/api/system.data.dataview.rowfilter?view=netframework-4.8) expression, set the value of [SfDataGrid.CanUseViewFilter](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_CanUseViewFilter) property to `true`. The default filter which created in DataView can be applied or canceled through this property. 

## Filter individual columns

To filter records in all the columns or in a particular column, use codes in OnColumnSelected() method. 

For example, the records can be filtered in `OrderID` or any other particular column alone. The following code example illustrates how to create a `Picker` for columns and how the records will be filtered based on the column selected:

{% tabs %}
{% highlight xaml %}
<Picker x:Name="ColumnsList"
        HorizontalOptions="Start"
        SelectedIndexChanged="OnColumnsSelectionChanged"
        WidthRequest="200">
    <Picker.Items>
        <x:String>All Columns</x:String>
        <x:String>CustomerID</x:String>
        <x:String>BookID</x:String>
        <x:String>FirstName</x:String>
        <x:String>LastName</x:String>
        <x:String>BookName</x:String>
    </Picker.Items>
</Picker>
{% endhighlight %}        
{% highlight c# %}
private void OnColumnsSelectionChanged(object sender, EventArgs e)
{
    Picker newPicker = (Picker)sender;
    viewModel.SelectedColumn = newPicker.Items[newPicker.SelectedIndex];
    if (viewModel.SelectedColumn == "All Columns")
    {
        viewModel.SelectedCondition = "Contains";
        OptionsList.IsVisible = false;
        this.OnFilterChanged();
    }
    else
    {
        OptionsList.IsVisible = true;
        foreach (var prop in typeof(OrderInfo).GetProperties())
        {
            // Records will be filtered based on selected column
            if (prop.Name == viewModel.SelectedColumn)
            {
                if (prop.PropertyType == typeof(string))
                {
                    OptionsList.Items.Clear();
                    OptionsList.Items.Add("Contains");
                    OptionsList.Items.Add("Equals");
                    OptionsList.Items.Add("NotEquals");
                    if (this.viewModel.SelectedCondition == "Equals")
                        OptionsList.SelectedIndex = 1;
                    else if (this.viewModel.SelectedCondition == "NotEquals")
                        OptionsList.SelectedIndex = 2;
                    else
                        OptionsList.SelectedIndex = 0;
                }
                else
                {
                    OptionsList.Items.Clear();
                    OptionsList.Items.Add("Equals");
                    OptionsList.Items.Add("NotEquals");
                    if (this.viewModel.SelectedCondition == "Equals")
                        OptionsList.SelectedIndex = 0;
                    else
                        OptionsList.SelectedIndex = 1;
                }
            }
        }
    }
}
{% endhighlight %}
{% endtabs %}

![DataGrid with data filtered based on columns](SfDataGrid_images/Filtering_Img2.png)

## Filter based on conditions

In addition to column based filtering, the records can be filtered based on some conditions. For example, the records can be filtered based on the given input or the records can be filtered contrast to the input. The condition based filtering can be achieved for all the columns or any particular column.

The records can be filtered in view based on any of the following conditions:

 * Equals
 * NotEquals
 * Contains

The above conditions are the mostly used conditions. However any other conditions can be added based on the requirement and alter the following code example based on the condition.

{% highlight c# %}
// ViewModel.cs

public bool FilerRecords(object o)
{
    double res;
    bool checkNumeric = double.TryParse(FilterText, out res);
    var item = o as OrderInfo;
    if (item != null && FilterText.Equals(""))
    {
        return true;
    }
    else
    {
        if (item != null)
        {
            if (checkNumeric && !SelectedColumn.Equals("All Columns"))
            {
                bool result = MakeNumericFilter(item, SelectedColumn, SelectedCondition);
                    return result;
            }
            else if (SelectedColumn.Equals("All Columns"))
            {
                if (item.CustomerID.ToLower().Contains(FilterText.ToLower()) ||
                    item.Country.ToLower().Contains(FilterText.ToLower()) || 
                    item.Freight.ToString().ToLower().Contains(FilterText.ToLower()) ||                            
                    item.OrderID.ToString().ToLower().Contains(FilterText.ToLower()))
                    return true;
                return false;
            }
            else
            {
                bool result = MakeStringFilter(item, SelectedColumn, SelectedCondition);
                return result;
            }
        }
    }
    return false;
}

private bool MakeStringFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    exactValue = exactValue.ToString().ToLower();
    string text = FilterText.ToLower();
    var methods = typeof(string).GetMethods();
    if (methods.Count() != 0)
    {
        if (condition == "Contains")
        {
            var methodInfo = methods.FirstOrDefault(method => method.Name == condition);
            bool result1 = (bool)methodInfo.Invoke(exactValue, new object[] { text });
            return result1;
        }
        else if (exactValue.ToString() == text.ToString())
        {
            bool result1 = String.Equals(exactValue.ToString(), text.ToString());
            if (condition == "Equals")
                return result1;
            else if (condition == "NotEquals")
                return false;
        }
        else if (condition == "NotEquals")
        {
            return true;
        }
        return false;
    }
    else
        return false;
}

private bool MakeNumericFilter(OrderInfo o, string option, string condition)
{
    var value = o.GetType().GetProperty(option);
    var exactValue = value.GetValue(o, null);
    double res;
    bool checkNumeric = double.TryParse(exactValue.ToString(), out res);
    if (checkNumeric)
    {
        switch (condition)
        {
            case "Equals":
                try
                {
                    if (exactValue.ToString() == FilterText)
                    {
                        if (Convert.ToDouble(exactValue) == (Convert.ToDouble(FilterText)))
                            return true;
                    }
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                }
                break;
            case "NotEquals":
                try
                {
                    if (Convert.ToDouble(FilterText) != Convert.ToDouble(exactValue))
                        return true;
                }
                catch (Exception e)
                {
                    Console.WriteLine(e);
                        return true;
                }
                break;
        }
    }
    return false;
}
{% endhighlight %}

The following code example illustrates how to create a `Picker` for conditions and add appropriate strings to that `Picker` and how the records will be filtered based on selected conditions:

{% tabs %}
{% highlight xaml %}
<Picker x:Name="OptionsList"
        HorizontalOptions="Start"
        IsVisible="False"
        SelectedIndexChanged="OnFilterOptionsChanged"
        WidthRequest="200">
    <Picker.Items>
        <x:String>Equals</x:String>
        <x:String>NotEquals</x:String>
        <x:String>Contains</x:String>
    </Picker.Items>
</Picker>
{% endhighlight %}
{% highlight c# %}
private void OnFilterOptionsChanged(object sender, EventArgs e)
{
    Picker newPicker = (Picker)sender;
    if (newPicker.SelectedIndex >= 0)
    {
        viewModel.SelectedCondition = newPicker.Items[newPicker.SelectedIndex];
        if (filterText.Text != null)
            this.OnFilterChanged();
    }
}
{% endhighlight %}
{% endtabs %}

Screenshot//

The following code example illustrates the complete `FilteringUI` and its operations:

{% tabs %}
{% highlight xaml %}
<StackLayout HorizontalOptions="FillAndExpand"
             Orientation="Vertical"
             VerticalOptions="FillAndExpand">
             
    <Grid HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
        
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
        </Grid.ColumnDefinitions>
        
        <SearchBar x:Name="filterText"
                   Grid.Row="0"
                   Grid.Column="0"
                   IsVisible="true"
                   Placeholder="Search here to Filter"
                   TextChanged="OnFilterTextChanged" />
        
        <syncfusion:SfDataGrid x:Name="dataGrid"
                               Grid.Row="1"
                               Grid.Column="0"
                               AutoGenerateColumns="false"
                               ColumnSizer="Star"
                               HorizontalOptions="FillAndExpand"
                               SelectionMode="Single"
                               VerticalOptions="FillAndExpand">
            <syncfusion:SfDataGrid.Columns>
                <syncfusion:GridTextColumn MappingName="OrderID" />
                <syncfusion:GridTextColumn MappingName="CustomerID" />
                <syncfusion:GridTextColumn MappingName="Freight" />
                <syncfusion:GridTextColumn MappingName="Country" />
            </syncfusion:SfDataGrid.Columns>
        </syncfusion:SfDataGrid>
    
    </Grid>
    
    <Grid ColumnSpacing="10" Padding="20">
    
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto" />
            <RowDefinition Height="Auto" />
        </Grid.RowDefinitions>
    
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="*" />
        </Grid.ColumnDefinitions>
    
        <Label x:Name="filterlabel"
               Grid.Row="0"
               Grid.Column="0"
               Grid.ColumnSpan="2"
               FontSize="15"
               HorizontalOptions="Start"
               Text="Filter Options"
               VerticalOptions="Center" />
    
        <Picker x:Name="ColumnsList"
                Grid.Row="1"
                Grid.Column="0"
                HorizontalOptions="Start"
                SelectedIndexChanged="OnColumnsSelectionChanged"
                WidthRequest="200">
            <Picker.Items>
                <x:String>All Columns</x:String>
                <x:String>CustomerID</x:String>
                <x:String>BookID</x:String>
                <x:String>FirstName</x:String>
                <x:String>LastName</x:String>
                <x:String>BookName</x:String>
            </Picker.Items>
        </Picker>
    
        <Picker x:Name="OptionsList"
                Grid.Row="1"
                Grid.Column="1"
                HorizontalOptions="Start"
                IsVisible="False"
                SelectedIndexChanged="OnFilterOptionsChanged"
                WidthRequest="200">
            <Picker.Items>
                <x:String>Equals</x:String>
                <x:String>NotEquals</x:String>
                <x:String>Contains</x:String>
            </Picker.Items>
        </Picker>
    
    </Grid>
</StackLayout>
{% endhighlight %}
{% highlight c# %}
this.dataGrid.ItemsSource = viewModel.OrdersInfo;
viewModel.filterTextChanged = OnFilterChanged;
ColumnsList.SelectedIndex = 0;

private void OnColumnsSelectionChanged(object sender, EventArgs e)
{
    Picker newPicker = (Picker)sender;
    viewModel.SelectedColumn = newPicker.Items[newPicker.SelectedIndex];
    if (viewModel.SelectedColumn == "All Columns")
    {
        viewModel.SelectedCondition = "Contains";
        OptionsList.IsVisible = false;
        this.OnFilterChanged();
    }
    else
    {
        OptionsList.IsVisible = true;
        foreach (var prop in typeof(OrderInfo).GetProperties())
        {
            if (prop.Name == viewModel.SelectedColumn)
            {
                if (prop.PropertyType == typeof(string))
                {
                    OptionsList.Items.Clear();
                    OptionsList.Items.Add("Contains");
                    OptionsList.Items.Add("Equals");
                    OptionsList.Items.Add("NotEquals");
                    if (this.viewModel.SelectedCondition == "Equals")
                        OptionsList.SelectedIndex = 1;
                    else if (this.viewModel.SelectedCondition == "NotEquals")
                        OptionsList.SelectedIndex = 2;
                    else
                        OptionsList.SelectedIndex = 0;
                }
                else
                {
                    OptionsList.Items.Clear();
                    OptionsList.Items.Add("Equals");
                    OptionsList.Items.Add("NotEquals");
                    if (this.viewModel.SelectedCondition == "Equals")
                        OptionsList.SelectedIndex = 0;
                    else
                        OptionsList.SelectedIndex = 1;
                }
            }
        }
    }
}

private void OnFilterOptionsChanged(object sender, EventArgs e)
{
    Picker newPicker = (Picker)sender;
    if (newPicker.SelectedIndex >= 0)
    {
        viewModel.SelectedCondition = newPicker.Items[newPicker.SelectedIndex];
        if (filterText.Text != null)
            this.OnFilterChanged();
    }
}

private void OnFilterTextChanged(object sender, TextChangedEventArgs e)
{
    if (e.NewTextValue == null)
        viewModel.FilterText = "";
    else
        viewModel.FilterText = e.NewTextValue;
}

private void OnFilterChanged()
{
    if (dataGrid.View != null)
    {
        this.dataGrid.View.Filter = viewModel.FilerRecords;
        this.dataGrid.View.RefreshFilter();
    }
}
{% endhighlight %}
{% endtabs %}

![DataGrid with data filtered based on conditions](SfDataGrid_images/Filtering_Img3.png)

## Clear filtering

The SfDataGrid allows to clear the applied filtering by setting the `SfDataGrid.View.Filter` property to `null`.

To clear the applied filtering, follow the code example:

{% highlight c# %}
// Code-Behind

private void OnFilterChanged()
{
    if (dataGrid.View != null)
    {
        this.dataGrid.View.Filter = null;
        this.dataGrid.View.RefreshFilter();
    }
}
{% endhighlight %}

You can download the filtering demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/FilteringDemo1597365704).
