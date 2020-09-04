---
layout: post
title: Filtering in Xamarin.Forms ListView | Syncfusion
description: Describes how to filter the data and its related operations like clear filter, sort the filtered data in the SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Filtering in Xamarin ListView (SfListView)

This section explains how to filter the data and its related operations in the SfListView.

## Programmatic filtering

The [SfListView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) supports to filter the data by setting the [SfListView.DataSource.Filter](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_Filter) property. You have to call the [SfListView.DataSource.RefreshFilter()](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_RefreshFilter) method after assigning the `Filter` property for refreshing the view.

The [FilterChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html) event is raised once filtering is applied to the SfListView.

The `FilterContacts` method filters the data contains the filter text value. Assign `FilterContacts` method to `SfListView.DataSource.Filter` predicate to filter the `ContactName`. To apply filtering in the SfListView, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
 <Grid>
	 <Grid.RowDefinitions>
                <RowDefinition Height="Auto"/>
                <RowDefinition Height="Auto"/>
   </Grid.RowDefinitions>
      <SearchBar x:Name="filterText" HeightRequest="40"
           Placeholder="Search here to filter"
           TextChanged="OnFilterTextChanged" Grid.Row="0"/>
      <syncfusion:SfListView x:Name="listView" Grid.Row="1" ItemSize="60" ItemsSource="{Binding customerDetails}"/>
  </Grid>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
var grid = new Grid();

var searchBar = new SearchBar() { Placeholder = "Search here to filter" };
searchBar.TextChanged += OnFilterTextChanged;

var listView = new SfListView();
listView.ItemsSource = viewModel.customerDetails;
listView.ItemSize = 60;

grid.Children.Add(searchBar);
grid.Children.Add(listView, 0, 1);

{% endhighlight %}
{% endtabs %}
 
The following code example illustrates code for filtering the data using `FilterContacts` method in the ViewModel:

{% tabs %}
{% highlight c# %}
SearchBar searchBar = null;
private void OnFilterTextChanged(object sender, TextChangedEventArgs e)
{
  searchBar = (sender as SearchBar);
  if (listView.DataSource != null)
  {
    this.listView.DataSource.Filter = FilterContacts;
    this.listView.DataSource.RefreshFilter();
  }
}
 
private bool FilterContacts(object obj)
{
  if (searchBar == null || searchBar.Text == null)
     return true;

  var contacts = obj as Contacts;
  if (contacts.ContactName.ToLower().Contains(searchBar.Text.ToLower())
       || contacts.ContactName.ToLower().Contains(searchBar.Text.ToLower()))
      return true;
  else
      return false;
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Filter-items-in-xamarin.forms-listview)

The following screenshot shows the output rendered when the items are filtered:

![Items filter in listview](SfListView_images/SfListView-Filtering.png)

### Filter based on multiple criteria

The [SfListView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) allows filtering the items based on multiple criteria. To filter the data using multiple properties, follow the code example:

{% tabs %}
{% highlight c# %}
private bool FilterContacts(object obj)
{
  if (searchBar == null || searchBar.Text == null)
     return true;

  var contacts = obj as Contacts;
  if (contacts.ContactName.ToLower().Contains(searchBar.Text.ToLower())
      || contacts.ContactNumber.ToLower().Contains(searchBar.Text.ToLower()))
      return true;
  else
      return false;
}
{% endhighlight %}
{% endtabs %}

## Getting the filtered data

You can get filtered items from the view and modify it in the [SfListView.DataSource.FilterChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html) event. When filter is applied, the filtered items are available in the [SfListView.DataSource.DisplayItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_DisplayItems).

{% tabs %}
{% highlight c# %}
listView.DataSource.FilterChanged += DataSource_FilterChanged;
...
private void DataSource_FilterChanged(object sender, NotifyCollectionChangedEventArgs e)
{
  //Contacts is model class 
  ObservableCollection<Contacts> contacts = new ObservableCollection<Contacts>();
  // Get the filtered items
  var items = (sender as DataSource).DisplayItems;
  foreach (var item in items)
      contacts.Add(item as Contacts);
}
{% endhighlight %}
{% endtabs %}

## Clear filtering

The SfListView allows clearing the filters by setting the [DataSource.Filter](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_Filter) to null, and call the [DataSource.RefreshFilter](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_RefreshFilter) method.

{% tabs %}
{% highlight c# %}
listView.DataSource.Filter = null;
listView.DataSource.RefreshFilter();
{% endhighlight %}
{% endtabs %}

## Sort the filtered items

The order of the filtered items can be rearranged in the [FilterChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html) event by adding [SortDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html). To sort the filtered items, follow the code example:

{% tabs %}
{% highlight c# %}
private void DataSource_FilterChanged(object sender, NotifyCollectionChangedEventArgs e)
{
  listView.DataSource.SortDescriptors.Add(new SortDescriptor { PropertyName = "ContactName", 
                                                               Direction = ListSortDirection.Ascending });
  listView.RefreshView();
}
{% endhighlight %}
{% endtabs %}

## See also

[How to filter Xamarin.Forms ListView (SfListView) using MVVM](https://www.syncfusion.com/kb/11478/)