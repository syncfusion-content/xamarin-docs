---
layout: post
title: RealTimeUpdates in SfListView
description: Describes about the grouping and its functionalities in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Real Time Updates

This section explains how to update the items at runtime.

## Add items to DataSource at runtime

ListView allows you to add the data to `DataSource` by adding the items to the collection, which is set as the source for the data source.

{% tabs %}
{% highlight c# %}
dataSource = new DataSource(); 
dataSource.Source = contactList = new ContactsList(); 
listView.ItemsSource = dataSource.DisplayItems; 
private void AddButton_Clicked(object sender, EventArgs e) 
{ 
    contactList.Add(new Contacts("Abraham")); 
}
{% endhighlight %}
{% endtabs %}

## Remove items from DataSource at runtime

ListView allows you to remove the data from `DataSource` by removing the items from the collection.

{% tabs %}
{% highlight c# %}
dataSource = new DataSource(); 
dataSource.Source = contactList = new ContactsList(); 
listView.ItemsSource = dataSource.DisplayItems; 
private void DeleteButton_Clicked(object sender, EventArgs e) 
{ 
    contactList.Remove(contactList[0] as Contacts); 
} 
{% endhighlight %}
{% endtabs %}
