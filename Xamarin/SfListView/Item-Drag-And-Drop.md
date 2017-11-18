---
layout: post
title: Item Drag and Drop in SfListView
description: Describes the drag and drop behavior and customization in SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# Item Drag and Drop

SfListView allows you to reordering items by dragging and dropping them in SfListView. It supports to displaying the customized view in a template while dragging the item. It is enable by setting the [SfListView.DragStartMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragStartMode.html) property to `OnHold`. The below listed options for drag and drop,

* None: Disables the drag and drop. This is default value.
* OnHold: Allows you to perform the drag and drop by hold the item.
* OnDragIndicator: Allows you to perform the drag and drop by loading the [DragIndicatorView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragIndicatorView.html) within [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html).

N> [GridLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.GridLayout.html) doesn't have support for drag and drop. 

The following code example shows how to enable drag and drop in SfListView.

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

## Dragging scenarios

Perform the drag and drop operation with and without groups.

* Items can be reordered to any position with auto scrolling. 
* Items can be reordered within the same group or into the other groups as well. But no groups can be added inside other groups.
* Groups, Header and Footer are not able to reorder.

N> Reordering changes are made only in view and not in the underlying data. Thus the changes will be reverted when performing sorting, grouping or any other operation that refreshes the view.

## Item Drag and Drop Template

By defining the [SfListView.DragItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragItemTemplate.html) of the SfListView, displaying the custom user interface(UI) when performing the drag and drop operation. The template can be defined either in code or XAML.

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

## Drag Indicator View

To perform the drag and drop by setting the [SfListView.DragStartMode](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~DragStartMode.html) property to `OnDragIndicator`. To display the drag item by defining any custom user interface(UI) in [DragIndicatorView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragIndicatorView.html) and it's binding context is drag item.

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

## Adjust Drag Item Axis

Adjust the drag item axis by return true from virtual method [CanAdjustDragItemAxis](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragDropController~CanAdjustDragItemAxis.html) of [DragDropController](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.DragDropController.html) being dragging. The default value is false.

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

## Layout Item on Dragging

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

## Item drag and drop event

[ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event is raised when perform dragging and dropping the item in [SfListView](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView.html). [ItemDraggingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs.html) has the following members which provides the information for `ItemDragging` event.

* Action: Returns the drag action such as Start, Dragging and Drop. Its a enum type.
* Bounds: Returns bounds of the drag item when perform dragging and dropping it.
* Handled: When perform dragging, can handle the dragging item if its set to true. And it's only applicable if [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) is `Dragging`.
* ItemData: Returns the underlying data of the drag item. 
* NewIndex: Returns the item index of underlying collection where the dragging item going to be dropped.
* OldIndex: Returns the item index of underlying collection where the dragging item started. The OldIndex and NewIndex will be same if `Action` is `Start`.
* Position: Returns the touch position of drag item from screen coordinates.

## Auto Scroll Options

### Adjust Auto Scroll Margin

Adjust the auto scroll margin to enable the auto scorlling being dragging by setting value to [ScrollMargin](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~ScrollMargin.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html). The default value is 15. The auto scrolling will be enabled being dragging when reach `ScrollMargin` from view bounds.

Disable the auto scorlling by setting the value to `0` for `ScrollMargin`.

{% highlight c# %}
this.listView.AutoScroller.ScrollMargin = 20;
{% endhighlight %}

### Adjust Auto Scroll Interval

Adjust the auto scrolling interval being dragging by setting [Interval](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~Interval.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html). The default value is 150 milliseconds.

{% highlight c# %}
this.listView.AutoScroller.Interval = new TimeSpan(0, 0, 0, 0, 200);
{% endhighlight %}

### Disable Outside Scroll

Disable the auto scrolling being dragging when drag item moves into outside of SfListView by setting [AllowOutsideScroll](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller~AllowOutsideScroll.html) property of [AutoScroller](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.AutoScroller.html). The default value is true.

{% highlight c# %}
this.listView.AutoScroller.AllowOutsideScroll = false;
{% endhighlight %}

## Disable Dragging for particular Item

Dragging can be disabled for a particular item by handling the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event using conditions based on event argument [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html). The following code example shows to disable dragging for particular item.

{% highlight c# %}
private void ListView_ItemDragging(object sender, ItemDraggingEventArgs e)
{
  // Disable the dragging for 4th item.
  if (e.Action == DragAction.Start && e.NewIndex == 3)
    e.Cancel = true;
}
{% endhighlight %}

## Cancel Dropping for Drag Item

Dropping can be canceled for drag item by handling the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event using conditions based on event argument [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html). The following code example shows to cancel dropping of particular item.

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

Reordering the items directly on the underlying collection by handling [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event. The following code example to make permanent reordering changes.

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

## Delete item when drop in particular view

Delete the drag item when drop into particular view by handling the [ItemDragging](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDragging_EV.html) event using conditions based on event arguments [Action](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemDraggingEventArgs~Action.html) and `Bounds`. The following code example shows to delete drag item when drop into particular view.

The following example shows to delete the drag item from underlying collection when drop into delete icon which is in above SfListView. It will enable and disable whenever drag started and dropped by IsVisible property in ViewModel.

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

The screenshots shows the output of reordering items by drag and drop in SfListView. You can download the entire source code of this demo from [here](http://www.syncfusion.com/downloads/support/directtrac/general/DRAGAN~1-54215034.ZIP)

![](SfListView_images/SfListView-ItemReordering.gif)


