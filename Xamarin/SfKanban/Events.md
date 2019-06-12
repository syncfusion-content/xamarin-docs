---
layout: post
title: Events in Xamarin.Forms Kanban control
description: Kanban Events
platform: xamarin
control: Kanban
documentation: ug
---

# Events

## ItemTapped

[`ItemTapped`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ItemTapped_EV.html) event is triggered when you tap on any card. The argument contains the following information.

* [`Column`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Column.html)          - Used to get the column of the card.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Data.html) 			- Used to get the underlying model of the card.
* [`Index`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanTappedEventArgs~Index.html) 			- Used to get the index of the card in a column.

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfKanban. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference to which the event  argument will display the properties associated with that reference.

>**NOTE**
The default value of `CardTappedCommandParameter` is `null`.

{% tabs %}
{% highlight xaml %}
<kanban:SfKanban x:Name="kanban" CardTappedCommand="{Binding ItemTappedCommand}" CardTappedCommandParameter="{Binding Source={x:Reference kanban}}" AutoGenerateColumns="False" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" ItemsSource="{Binding Cards}">
    <kanban:SfKanban.BindingContext>
        <local:ViewModel/>
    </kanban:SfKanban.BindingContext>
        <kanban:SfKanban.Columns> 
            <kanban:KanbanColumn x:Name="column1" Title="To Do">
            </kanban:KanbanColumn>
            <kanban:KanbanColumn x:Name="column2" Title="In Progress">
            </kanban:KanbanColumn>
            <kanban:KanbanColumn x:Name="column3" Title="Code Review">
            </kanban:KanbanColumn>
            <kanban:KanbanColumn x:Name="column4" Title="Done">
            </kanban:KanbanColumn>
        </kanban:SfKanban.Columns>
</kanban:SfKanban>
{% endhighlight %}

{% highlight c# %}
 public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();

            column1.Categories = new List<object>() { "Open" };
            column2.Categories = new List<object>() { "In Progress" };
            column3.Categories = new List<object>() { "Code Review" };
            column4.Categories = new List<object>() { "Closed" };
        }
    }
    public class ViewModel
    {
        public ObservableCollection<KanbanModel> Cards { get; set; }
        public ICommand ItemTappedCommand { get; set; }
        public ViewModel()
        {
            Cards = new ObservableCollection<KanbanModel>();
            ItemTappedCommand = new Command<object>(ItemTappedEvent);
            Cards.Add(new KanbanModel()
            {
                ID = 1,
                Title = "iOS - 1002",
                ImageURL = "Image1.png",
                Category = "Open",
                Description = "Analyze customer requirements",
                ColorKey = "Red",
                Tags = new string[] { "Incident", "Customer" }
            });
            Cards.Add(new KanbanModel()
            {
                ID = 6,
                Title = "Xamarin - 4576",
                ImageURL = "Image2.png",
                Category = "Open",
                Description = "Show the retrieved data from the server in grid control",
                ColorKey = "Green",
                Tags = new string[] { "Story", "Customer" }
            });
            Cards.Add(new KanbanModel()
            {
                ID = 13,
                Title = "UWP - 13",
                ImageURL = "Image4.png",
                Category = "In Progress",
                Description = "Add responsive support to application",
                ColorKey = "Brown",
                Tags = new string[] { "Story", "Customer" }
            });
            Cards.Add(new KanbanModel()
            {
                ID = 2543,
                Title = "Xamarin_iOS - 2543",
                Category = "Code Review",
                ImageURL = "Image3.png",
                Description = "Check login page validation",
                ColorKey = "Brown",
                Tags = new string[] { "Story", "Customer" }
            });
        }

        private void ItemTappedEvent(object args)
        {
            KanbanTappedEventArgs paramerter = args as KanbanTappedEventArgs;
            var column = paramerter.Column;
            var index = paramerter.Index;
            KanbanModel model = paramerter.Data as KanbanModel;
            model.Title = "Sync";
            model.ID = 555;
        }
    }
{% endhighlight %}
{% endtabs %}

## DragStart

[`DragStart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragStart_EV.html) event is triggered when you start to drag a card. The argument contains the following information.

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs~Cancel.html)			- Used to cancel the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the underlying model of the card.
* [`KeepItem`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs~KeepItem.html)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the source column of card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the card in source column.   

## DragEnd  

[`DragEnd`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragEnd_EV.html) event is triggered whenever the card is dropped or dragging action is canceled. The argument contains the following information.

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~Cancel.html)			- Used to cancel the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the underlying model of the card.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the source column of the card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the card in source column.
* [`TargetCategory`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetCategory.html) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetColumn.html)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs~TargetIndex.html)		- Used to get the index of the card in target column.

## DragEnter 

[`DragEnter`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragEnter_EV.html) event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~Cancel.html)				- Used to cancel the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)				- Used to get the underlying model of the card.
* [`IsAboveMaximumLimit`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~IsAboveMaximumLimit.html)	- Used to know whether the total cards count of the target column will be above the maximum limit if you drop the card in target column. You can define the maximum limit of the cards using KanbanColumn.MaximumLimit. 
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 		- Used to get the source column of the card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)			- Used to get the index of the card in source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~TargetColumn.html)		- Used to get the column upon which the card enters.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs~TargetIndex.html)			- Used to get the index of the card in target column.

## DragLeave 

[`DragLeave`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragLeave_EV.html) event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)                - Used to get the underlying model of the card.
* [`IsBelowMinimumLimit`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs~IsBelowMinimumLimit.html) - Used to know whether the total cards count of the target column will be below the minimum limit if you remove the card from target column. You can define the minimum limit of the cards using KanbanColumn.MinimumLimit.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html)        - Used to get the source column of the card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)         - Used to get the index of the card in source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs~TargetColumn.html)		- Used to get the column from which the card leaves.

## DragOver

[`DragOver`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~DragOver_EV.html) event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~Cancel.html)			- Used to cancel the drag action.
* [`Data`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~Data.html)			- Used to get the underlying model of the card.
* [`SourceColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceColumn.html) 	- Used to get the source column of the card.
* [`SourceIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragEventArgs~SourceIndex.html)		- Used to get the index of the card in source column.
* [`TargetColumn`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~TargetColumn.html)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs~TargetIndex.html)		- Used to get the new index of the card in target column.

## ColumnsGenerated 

[`ColumnsGenerated`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ColumnsGenerated_EV.html) event will be fired after the columns are generated automatically. You can access the auto-generated columns using [`SfKanban.ActualColumns`](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfKanban.XForms~Syncfusion.SfKanban.XForms.SfKanban~ActualColumns.html) property.
