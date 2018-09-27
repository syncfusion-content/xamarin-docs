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

## Refreshing a particular item or a range of items

ListView allows you to refresh all the items or a particular range or item by calling the [RefreshListViewItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~RefreshListViewItem.html) method by providing the items range. To refresh a particular item, pass the particular item index alone in both the first and last index.

Here, you can refresh the item template by passing the `canReload` boolean parameter as `true`.

{% tabs %}
{% highlight c# %}
listView.RefreshListViewItem(0, 22, false);
{% endhighlight %}
{% endtabs %}

## Refreshing group header item when listview item value is changed

ListView allows you to refresh the group header when changing the [SfListView.GroupHeaderTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~GroupHeaderTemplate.html) content by the listview item value. It can be refreshed with its template by passing the GroupHeader item index in the `RefreshListViewItem` method and `canReload` parameter as true.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
<Grid>
    <Grid.RowDefinitions>
    <RowDefinition Height="50"/>
    <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Button Text="Modify ContactNumber" Clicked="Button_Clicked" />
    <syncfusion:SfListView x:Name="listView" ItemsSource="{Binding Items}">
    <listView:SfListView.GroupHeaderTemplate>
        <DataTemplate>
            <Grid BackgroundColor="#E4E4E4">
                <StackLayout Orientation="Horizontal" HorizontalOptions="Start"
                                VerticalOptions="Center" Padding="10,0,0,0">
                    <Label Text="{Binding Items, Converter={StaticResource Converter},Mode=TwoWay}" />
                </StackLayout>
            </Grid>
        </DataTemplate>
    </listView:SfListView.GroupHeaderTemplate>
  </syncfusion:SfListView>
</Grid>
</ContentPage>
{% endhighlight %}

{% highlight c# %}
listView.GroupHeaderTemplate = new DataTemplate(() =>
{
   var grid = new Grid();

   var label1 = new Label();
   Binding binding = new Binding("Items");
   binding.Converter = new Converter();
   label1.SetBinding(Label.TextProperty,binding);

   grid.Children.Add(label1);
   return grid;
 });

private void Button_Clicked(object sender, EventArgs e)
{
     ViewModel.Items[0].ContactNumber = "5555";
     listView.RefreshListViewItem(0, 0,true);
}
{% endhighlight %}
{% endtabs %}