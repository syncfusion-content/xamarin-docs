---
layout: post
title: Filtering - Forms | SfDataGrid | Xamarin | Syncfusion
description: Filtering - Forms
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Filtering in Forms 

**SfDataGrid** provides support to filter the records in view by setting the **SfDataGrid.View.Filter** property. You have to call the **SfDataGrid.View.RefreshFilter()** method after assigning the Filter property for refreshing the view.
 
The following code example illustrates how to apply filtering in **SfDataGrid**. FilterRecords method filters the data that contains the filterText value. Assign FilterRecords method to **SfDataGrid.View.Filter** predicate to filter the CustomerID column.

{% highlight xaml %}
//Filtering.xaml

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local ="clr-namespace:DataGridSample;assembly=DataGridSample"
             x:Class="DataGridSample.Sample">

    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>

    <Grid>
        <Grid.RowDefinitions>
            <RowDefinition Height="50" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>

        <SearchBar Placeholder="Search CustomerID" 
                   TextChanged="searchBar_TextChanged" />

        <syncfusion:SfDataGrid x:Name="dataGrid"
                               Grid.Row="1"
                               ItemsSource="{Binding OrdersInfo}" />
    </Grid>
</ContentPage> 
{% endhighlight %}

{% highlight c# %}
//Filtering.xaml.cs

viewModel.FilterTextChanged = OnFilterChanged; 
 
private void searchBar_TextChanged(object sender, TextChangedEventArgs e)
{
    if (e.NewTextValue == null)
        viewModel.FilterText = "";
    else
        viewModel.FilterText = e.NewTextValue;
}

private void OnFilterChanged()
{
    if (dataGrid.View != null) {
        this.dataGrid.View.Filter = viewModel.FilerRecords;
        this.dataGrid.View.RefreshFilter ();
    }
} 
{% endhighlight %}

The following code example illustrates the code for filtering the data using FilterRecords method in the ViewModel.

{% highlight c# %}
//ViewModel.cs
internal delegate void FilterChanged();

internal FilterChanged FilterTextChanged;

private string filterText = "";

public string FilterText {
    get { return filterText; }
    set {
        filterText = value;
        OnFilterTextChanged ();
        RaisePropertyChanged ("FilterText");
    }
}

private void OnFilterTextChanged()
{
    if (FilterTextChanged != null)
    FilterTextChanged ();
}

public bool FilerRecords(object order)
{
    var item = order as OrderInfo;
    if (item != null && FilterText.Equals ("") && !string.IsNullOrEmpty (FilterText))
        return true;
    else if (item != null) {
        var exactValue = item.CustomerID.ToLower ();
        string text = FilterText.ToLower ();
        return exactValue.Contains (text);
    }
    return false;
}
{% endhighlight %}
