---
layout: post
title: Item Drag and Drop in SfListView
description: Describes the drag and drop behavior and customization in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Drag and Drop

SfListView allows you to reordering items by dragging and dropping them in SfListView. It supports to displaying the customized view in a template while dragging the item. It is enable by setting the `SfListView.DragStartMode` property to `OnHold`. The below listed options for drag and drop,

* None: Disables the drag and drop. This is default value.
* OnHold: Allows you to perform the drag and drop by hold the item.
* OnDragIndicator: Allows you to perform the drag and drop by loading the `DragIndicatorView` within [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html).

N> [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) doesn't have support for drag and drop. 

The following code example shows how to enable drag and drop in SfListView.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
{% endhighlight %}
{% highlight c# %}
listView.DragStartMode = DragStartMode.OnHold; 
{% endhighlight %}
{% endtabs %}

## Dragging scenarios

Perform the drag and drop operation with and without groups.

* Items can be reordered to any position with auto scrolling. 
* Items can be reordered within the same group or into the other groups as well. But no groups can be added inside other groups.
* Groups, Header and Footer are not able to reorder.

N> Reordering changes are made only in view and not in the underlying data. Thus the changes will be reverted when performing sorting, grouping or any other operation that refreshes the view.

## Item Drag and Drop Template

By defining the `SfListView.DragItemTemplate` of the SfListView, displaying the custom user interface(UI) when performing the drag and drop operation. The template can be defined either in code or XAML.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold,OnDragIndicator"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
  <syncfusion:SfListView.DragItemTemplate>
    <DataTemplate>
      <Grid Padding="10">
        <Label x:Name="textLabel" Text="{Binding Name}" FontSize="15" />
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.DragItemTemplate>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
listView.ItemTemplate = new DataTemplate(() => {
  var grid = new Grid();
  var name = new Label { FontSize = 15 };
  name.SetBinding(Label.TextProperty, new Binding("Name"));
  grid.Children.Add(name);
  return grid;
});
{% endhighlight %}
{% endtabs %}

## DragIndicator View

To perform the drag and drop by setting the `DragStartMode` property to `OnDragIndicator`. To display the drag item by defining any custom user interface(UI) in `DragIndicatorView` and it's binding context is drag item.

N> Must set SfListView instance as reference to `ListView` property in `DragIndicatorView`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold,OnDragIndicator"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60">
  <syncfusion:SfListView.DragItemTemplate>
    <DataTemplate>
      <Grid Padding="10">
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*" />
            <ColumnDefinition Width="60" />
          </Grid.ColumnDefinitions>
          <Label x:Name="textLabel" Text="{Binding Name}" Grid.Column="1" FontSize="15" TextColor="#333333" />

          <syncfusion:DragIndicatorView Grid.Column="2" ListView="{x:Reference listView}" 
                    HorizontalOptions="Center" 
                    VerticalOptions="Center">
            <Grid Padding="10, 20, 20, 20">
              <Image Source="DragIndicator.png" />
            </Grid>
          </syncfusion:DragIndicatorView>
        </Grid>
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.DragItemTemplate>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
listView.ItemTemplate = new DataTemplate(() =>
{
  var grid = new Grid();
  var name = new Label
  {
    FontSize = 15,
    VerticalOptions = LayoutOptions.Center
  };
  name.SetBinding(Label.TextProperty, new Binding("Name"));

  var indicatorGrid = new Grid()
  {
    Padding = new Thickness(10, 20, 20, 20),
    HorizontalOptions = LayoutOptions.End,
    VerticalOptions = LayoutOptions.Center
  };
  var dragIndicatorView = new DragIndicatorView() { ListView = this.listView };
  var indicator = new Image() { Source = "DragIndicator.png" };

  indicatorGrid.Children.Add(indicator);
  dragIndicatorView.Content = indicatorGrid;

  grid.Children.Add(name);
  grid.Children.Add(dragIndicatorView, 1, 0);
  return grid;
});
{% endhighlight %}
{% endtabs %}

## Item drag and drop event

`ItemDragging` event is raised when perform dragging and dropping the item in [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html). `ItemDraggingEventArgs` has the following members which provides the information for `ItemDragging` event.

* Action: Returns the drag action such as Start, Dragging and Drop. Its a enum type.
* Bounds: Returns bounds of the drag item when perform dragging and dropping it.
* Handled: When perform dragging, can handle the dragging item if its set to true. And it's only applicable if `Action` is `Dragging`.
* ItemData: Returns the underlying data of the drag item. 
* NewIndex: Returns the item index of underlying collection where the dragging item going to be dropped.
* OldIndex: Returns the item index of underlying collection where the dragging item started. The OldIndex and NewIndex will be same if `Action` is `Start`.
* Position: Returns the touch position of drag item from screen coordinates.

## Disable Dragging for particular Item

Dragging can be disabled for a particular item by handling the `ItemDragging` event using conditions based on drag `Action`. Refer following code sample to disable dragging for particular item.

{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Disable the dragging for 4th item.
  if (e.Action == DragAction.Start && e.NewIndex == 3)
    e.Cancel = true;
}
{% endhighlight %}

## Cancel Dropping for Drag Item

Dropping can be canceled for drag item by handling the `ItemDragging` event using conditions based on `Action`. Refer following code sample to cancel dropping of particular item.

{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Cancel the dropping if drop the drag item into out of view.
  var listview = sender as ListView;
  var totalExtent = listview.GetVisualContainer().Bounds.Bottom;
  if (e.Action == DragAction.Drop && (e.Bounds.Y < -30 || e.Bounds.Bottom > totalExtent + 40))
    e.Cancel = true;
}
{% endhighlight %}
