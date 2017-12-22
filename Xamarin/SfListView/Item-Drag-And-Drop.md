---
layout: post
title: Item Drag and Drop in SfListView
description: Describes the drag and drop behavior and customization in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Drag And Drop

SfListView allows reordering by dragging and dropping items. It supports to display the customized view in a template while dragging the item. It can be enabled by setting the [SfListView.DragStartMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragStartMode.html) property to `OnHold`. The drag and drop options are listed as follows:

* None: Disables drag and drop. This is the default value.
* OnHold: Allows to perform drag and drop by holding the item.
* OnDragIndicator: Allows to perform drag and drop by loading the [DragIndicatorView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragIndicatorView.html) within [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html).

N> [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) does not support drag and drop. 

The drag and drop scenarios are as follows:

* Items can be reordered to any position by auto-scrolling.
* Items can be reordered in same group or in other groups. But no groups can be added to other groups.
* Groups, Header, and Footer are not able to reorder.

To enable drag and drop using 'OnHold', follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.DragStartMode = DragStartMode.OnHold; 
{% endhighlight %}
{% endtabs %}

To enable drag and drop using both 'OnHold' and 'OnDragIndicator', follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold, OnDragIndicator"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
{% endhighlight %}
{% highlight c# %}
listView.DragStartMode = DragStartMode.OnHold | DragStartMode.OnDragIndicator; 
{% endhighlight %}
{% endtabs %}

N> Reordering changes are made only in view and not in the underlying data. Thus the changes will be reverted when performing sorting, grouping, or any other operations that refresh the view.

## Drag indicator view

To perform drag and drop items by [DragIndicatorView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragIndicatorView.html), set the [SfListView.DragStartMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragStartMode.html) property to `OnDragIndicator`. To display drag item, define any custom user interface(UI) in `DragIndicatorView`.

N> You must set SfListView instance as reference to `ListView` property in `DragIndicatorView`.

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

The screenshot shows the output of reordering items by drag and drop. You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ITEMDR~1-296035285.ZIP).

![](SfListView_images/SfListView-ItemReordering.gif)

## Item drag and drop event

[ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event is raised while dragging and dropping the item in [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html). [ItemDraggingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs.html) has the following members which provide the information for `ItemDragging` event:

* Action: Returns drag [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) such as Start, Dragging, and Drop.
* Bounds: Return bounds of drag item when perform dragging and dropping.
* Handled: If this member is set to true, dragging can be handled while dragging the item. It is applicable only if `Action` is `Dragging`.
* ItemData: Returns underlying data of dragging item. 
* NewIndex: Returns item index of underlying collection where dragging item is going to be dropped.
* OldIndex: Returns item index of underlying collection where dragging item started. The OldIndex and NewIndex will be same if `Action` is `Start`.
* Position: Returns touch position of drag item from screen coordinates.

## Drag item template

By defining the [SfListView.DragItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragItemTemplate.html) of SfListView, displays the custom user interface(UI) when performing drag and drop operations. The template can be defined either in code or XAML.

N> If `BackgroundColor` is set to `DragItemTemplate` or [DragIndicatorView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragIndicatorView.html), set `InputTransparent` to true. Since dragging does not happen when perform by `DragIndicatorView` in UWP.

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

## Auto scroll options

### Adjust auto scroll margin

To adjust auto scroll margin, set a value to [ScrollMargin](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~ScrollMargin.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html) to enable auto-scrolling while dragging. The default value is 15. Auto-scrolling will be enabled when reaching `ScrollMargin` from view bounds while dragging.

To disable auto-scrolling, set the value to `0` for `ScrollMargin`.

{% highlight c# %}
this.listView.AutoScroller.ScrollMargin = 20;
{% endhighlight %}

### Adjust auto scroll interval

To adjust auto-scrolling interval while dragging, set [Interval](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~Interval.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html). The default value is 150 milliseconds.

{% highlight c# %}
this.listView.AutoScroller.Interval = new TimeSpan(0, 0, 0, 0, 200);
{% endhighlight %}

### Disable outside scroll

To disable auto-scrolling when drag item moves outside SfListView while dragging, set [AllowOutsideScroll](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~AllowOutsideScroll.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html). The default value is true.

{% highlight c# %}
this.listView.AutoScroller.AllowOutsideScroll = false;
{% endhighlight %}

## Disable dragging for a particular item

To disable dragging for a particular item, handle the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) event argument. To disable dragging for a particular item, follow the code example:

{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Disable the dragging for 4th item.
  if (e.Action == DragAction.Start && e.NewIndex == 3)
    e.Cancel = true;
}
{% endhighlight %}

## Cancel dropping for the dragged item

To cancel dropping for the dragged item, handle the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) event argument. To cancel dropping, follow the code example:

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

## Reorder the underlying collection 

The underlying collection can be reordered directly by handling [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event. To make permanent reordering changes, follow the code example:

{% highlight c# %}
private async void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Reorder the item in underlying collection.
  if (e.Action == DragAction.Drop)
  {
    await Task.Delay(100);
    var collection = listView.BindingContext as ViewModel;
    collection.ToDoList.Move(e.OldIndex, e.NewIndex);
  }
}
{% endhighlight %}

## Delete item when dropping in a particular view

To delete the dragged item when dropping into a particular view, handle the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) and `Bounds` event arguments. To delete the dragged item when dropping in particular view, follow the code example:

To delete the dragged item from underlying collection when dropping into delete icon, follow the code example. It will enable or disable whenever drag started and dropped by IsVisible property in ViewModel.

{% highlight xaml %}
<Grid>
  <Grid.RowDefinitions>
    <RowDefinition Height="Auto" />
    <RowDefinition Height="*" />
  </Grid.RowDefinitions>

  <Grid BackgroundColor="#2196F3">
    <Label Text="To Do Items" x:Name="headerLabel"  TextColor="White" FontAttributes="Bold" VerticalOptions="Center" HorizontalOptions="Center" />
    <StackLayout x:Name="stackLayout" IsVisible="{Binding IsVisible}" Orientation="Horizontal" VerticalOptions="Center" HorizontalOptions="Center">
      <Image Source="Delete.png" HeightRequest="30" WidthRequest="30" />
      <Label x:Name="deleteLabel" Text="Delete Item" FontAttributes="Bold" TextColor="White" />
    </StackLayout>
  </Grid>

  <syncfusion:SfListView x:Name="listView" Grid.Row="1"
                   ItemsSource="{Binding ToDoList}"
                   DragStartMode="OnHold"
                   BackgroundColor="#FFE8E8EC"
                   ItemSize="60" />
</Grid>
{% endhighlight %}

{% highlight c# %}
private async void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  var viewModel = this.listView.BindingContext as ViewModel;

  if (e.Action == DragAction.Start)
  {
    viewModel.IsVisible = true;
    this.stackLayout.Opacity = 0.25;
  }

  if(e.Action == DragAction.Dragging)
  {
    var position = new Point(e.Position.X - this.listView.Bounds.X, e.Position.Y - this.listView.Bounds.Y);
    if (this.stackLayout.Bounds.Contains(position))
      this.deleteLabel.TextColor = Color.Red;
    else
      this.deleteLabel.TextColor = Color.White;
  }

  if(e.Action == DragAction.Drop)
  {
    var position = new Point(e.Position.X - this.listView.Bounds.X, e.Position.Y - this.listView.Bounds.Y);
    if (this.stackLayout.Bounds.Contains(position))
    {
      await Task.Delay(100);
      viewModel.ToDoList.Remove(e.ItemData as ToDoItem);
    }
    viewModel.IsVisible = false;
    this.deleteLabel.TextColor = Color.White;
    this.headerLabel.IsVisible = true;
  }
}
{% endhighlight %}

The screenshot shows the output of delete the dragged item when drop into particular view. You can download the sample for above source code from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ITEMDR~1499947492.ZIP).

![](SfListView_images/SfListView-ItemReordering1.gif)

## Skip dragging item into another group

To skip dragging from one group to another group, handle the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event based on the conditions of [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) and `Bounds` event arguments.

N> While auto-scrolling, dragging item cannot be skipped.

Skip the dragging item by bounds of dragging item and bounds of current and next group item. To skip the dragging from one group to another group, follow the code example:

{% highlight c# %}
private async void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  if (e.Action == DragAction.Dragging)
  {
    var currentGroup = this.GetGroup(e.ItemData);
    var container = this.listView.GetVisualContainer();
    var groupIndex = this.listView.DataSource.Groups.IndexOf(currentGroup);
    var nextGroup = (groupIndex + 1 < this.listView.DataSource.Groups.Count) ? this.listView.DataSource.Groups[groupIndex + 1] : null;
    ListViewItem groupItem = null;
    ListViewItem nextGroupItem = null;

    foreach (ListViewItem item in container.Children)
    {
      if (item.BindingContext.Equals(currentGroup))
        groupItem = item;

      if (nextGroup != null && item.BindingContext.Equals(nextGroup))
        nextGroupItem = item;
    }

    if (e.Bounds.Y <= groupItem.Y + groupItem.Height || nextGroupItem != null && (e.Bounds.Y + e.Bounds.Height >= nextGroupItem.Y))
      e.Handled = true;
  }
}

private GroupResult GetGroup(object itemData)
{
  GroupResult itemGroup = null;

  foreach (var item in this.listView.DataSource.DisplayItems)
  {
    if (item is GroupResult)
      itemGroup = item as GroupResult;

    if (item == itemData)
      break;
  }
  return itemGroup;
}
{% endhighlight %}

Download the sample for above source code from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ITEMDR~1-1162681143.ZIP).

## Drag and drop customization

### Adjust drag item axis

To adjust drag item coordinates (X and Y) while dragging, return true from virtual method [CanAdjustDragItemAxis](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragDropController~CanAdjustDragItemAxis.html) of [DragDropController](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragDropController.html). By default, Y coordinates can be adjusted if [SfListView.Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html) is `Vertical` and X coordinates can be adjusted if `Orientation` is `Horizontal`.

{% highlight c# %}
this.listView.DragDropController = new DragDropControllerExt(this.listView);

public class DragDropControllerExt : DragDropController
{
  public DragDropControllerExt(SfListView listView) : base(listView)
  {

  }

  protected override bool CanAdjustDragItemAxis()
  {
    return true;
  }
}
{% endhighlight %}

### Layout item on dragging

In SfListView, layout the [ListViewItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ListViewItem.html) with different animation and time on dragging by virtual method [OnLayoutItem](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragDropController~OnLayoutItem.html).

{% highlight c# %}
this.listView.DragDropController = new DragDropControllerExt(this.listView);

public class DragDropControllerExt : DragDropController
{
  public DragDropControllerExt(SfListView listView) : base(listView)
  {

  }

  protected override Task<bool> OnLayoutItem(View element, Rectangle rect)
  {
    return element.LayoutTo(rect, 250, Easing.BounceIn);
  }
}
{% endhighlight %}