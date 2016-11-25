---
layout: post
title: Filtering | SfListView | Xamarin | Syncfusion
description: How to filter the data in a SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

## Programmatic Filtering
SfListView provides support to filter the data by setting the [SfListView.DataSource.Filter](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~Filter.html) property. You have to call the [SfListView.DataSource.RefreshFilter()](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~RefreshFilter.html) method after assigning the `Filter` property for refreshing the view.
 
The following code example illustrates how to apply filtering in SfListView. `FilterContacts` method filters the data that contains the filter text value. Assign `FilterContacts` method to `SfListView.DataSource.Filter` predicate to filter the `ContactName`.

{% highlight c# %}
var grid = new Grid();

var searchbar = new SearchBar() { Placeholder = "Search here to filter" };
searchbar.TextChanged += OnFilterTextChanged;

var listView = new SfListView();
listView.ItemsSource = viewmodel.customerDetails;
listView.ItemSize = 60;

grid.Children.Add(searchbar);
grid.Children.Add(listView, 0, 1);

{% endhighlight %}

The following code example illustrates the code for filtering the data using `FilterContacts` method in the ViewModel.

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

## Events

### FilterChanged event

[FilterChanged](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~FilterChanged_EV.html) event is raised after filter is applied. You can use this event to get filtered data.

{% highlight c# %}
listView.DataSource.FilterChanged += DataSource_FilterChanged;

private void DataSource_FilterChanged(object sender, NotifyCollectionChangedEventArgs e)
{
}
{% endhighlight %}

## Getting the filtered data

You can get the filtered items from the view and modify it in [SfListView.DataSource.FilterChanged](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~FilterChanged_EV.html) event. When filter is applied, the filtered items are available in [SfListView.DataSource.DisplayItems](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~DisplayItems.html).

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

## Clear the filtered data

You can remove the filtered items from the `ViewModel`. The following example illustrates that how to remove the filtered items from the `ViewModel`.

{% highlight c# %}
listView.DataSource.FilterChanged += DataSource_FilterChanged;
...
private void DataSource_FilterChanged(object sender, NotifyCollectionChangedEventArgs e)
{
  var items = (sender as DataSource).DisplayItems;
  foreach (var item in items)
  {
     var contact = item as Contacts;
     if (viewmodel.customerDetails[0] == contact)
        viewmodel.customerDetails.Remove(contact);
  }
}
{% endhighlight %}

## Filter by using multiple properties

SfListView allows you to filter the items on applying the different criteria by custom logic. The following example illustrates how to filter the data using multiple properties.

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

## Sort the filtered items

You can rearrange the order of the filtered items in [FilterChanged](https://help.syncfusion.com/cr/cref_files/xamarin/datasource/Syncfusion.DataSource.Portable~Syncfusion.DataSource.DataSource~FilterChanged_EV.html) event. The following example illustrates how to sort the filtered items.

{% highlight c# %}
private void DataSource_FilterChanged(object sender, NotifyCollectionChangedEventArgs e)
{
  listView.DataSource.SortDescriptors.Add(new SortDescriptor { PropertyName = "ContactName", 
                                                               Direction = ListSortDirection.Ascending });
  listView.RefreshView();
}
{% endhighlight %}