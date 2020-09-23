---
layout: post
title: Syncfusion events in Xamarin.Forms Kanban control
description: Kanban events
platform: xamarin
control: Kanban
documentation: ug
---

# Events

## ItemTapped

[`ItemTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered when you tap on any card. The argument contains the following information.

* [`Column`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanTappedEventArgs.html#Syncfusion_SfKanban_XForms_KanbanTappedEventArgs_Column)          - Used to get the column of the card.
* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanTappedEventArgs.html#Syncfusion_SfKanban_XForms_KanbanTappedEventArgs_Data) 			- Used to get the underlying model of the card.
* [`Index`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanTappedEventArgs.html#Syncfusion_SfKanban_XForms_KanbanTappedEventArgs_Index) 			- Used to get the index of the card in a column.

### Command

The `CardTappedCommand` property is used to associate a command with an instance of SfKanban. This property is most often set with MVVM pattern to bind callbacks back into the ViewModel.

### CommandParameter

The `CardTappedCommandParameter` property is used to set the parameter reference, based on which the event argument is shown.

>**NOTE**
The default value of the `CardTappedCommandParameter` is `null`.

{% tabs %}
{% highlight xaml %}
<kanban:SfKanban  CardTappedCommand="{Binding CardTappedCommand}" CardTappedCommandParameter="1">
           <!--Intialize the column-->
</kanban:SfKanban >
{% endhighlight %}

{% highlight c# %}

    public class ViewModel
    {

        public ViewModel()
        {
            CardTappedCommand = new Command<object>(CardTappedEvent);

            public ICommand CardTappedCommand { get; set; }
        }

        private void CardTappedEvent(object args)
        {
            //  handle event action.
        }
    }
{% endhighlight %}
{% endtabs %}

## DragStart

[`DragStart`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered when you start to drag a card. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragStartEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`KeepItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragStartEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragStartEventArgs_KeepItem)		- Determines whether to keep the dragged card in the source location itself, until it is dropped in a new location. When it is true, the preview of the card will be created for dragging.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.   

## DragEnd  

[`DragEnd`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered whenever the card is dropped or dragging action is canceled. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEndEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.
* [`TargetCategory`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEndEventArgs_TargetCategory) 	- Used to get the category of the column where the card is going to be dropped.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEndEventArgs_TargetColumn)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEndEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEndEventArgs_TargetIndex)		- Used to get the index of the card in target column.

## DragEnter 

[`DragEnter`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered when a card enters into a column while dragging. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEnterEventArgs_Cancel)				- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_Data)				- Used to get the underlying model of the card.
* [`IsAboveMaximumLimit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEnterEventArgs_IsAboveMaximumLimit)	- Used to know whether the total cards count of the target column will be above the maximum limit if you drop the card in target column. You can define the maximum limit of the cards using KanbanColumn.MaximumLimit. 
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceColumn) 		- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceIndex)			- Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEnterEventArgs_TargetColumn)		- Used to get the column upon which the card enters.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEnterEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEnterEventArgs_TargetIndex)			- Used to get the index of the card in target column.

## DragLeave 

[`DragLeave`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered when a card leaves a column while dragging. The argument contains the following information.

* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_Data)                - Used to get the underlying model of the card.
* [`IsBelowMinimumLimit`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragLeaveEventArgs_IsBelowMinimumLimit) - Used to know whether the total cards count of the target column will be below the minimum limit if you remove the card from target column. You can define the minimum limit of the cards using KanbanColumn.MinimumLimit.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceColumn)        - Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceIndex)         - Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragLeaveEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragLeaveEventArgs_TargetColumn)		- Used to get the column from which the card leaves.

## DragOver

[`DragOver`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event is triggered when a card is dragged to a new index within a column. The argument contains the following information.

* [`Cancel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragOverEventArgs_Cancel)			- Used to cancel the drag action.
* [`Data`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_Data)			- Used to get the underlying model of the card.
* [`SourceColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceColumn) 	- Used to get the source column of the card.
* [`SourceIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragEventArgs_SourceIndex)		- Used to get the index of the card in source column.
* [`TargetColumn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragOverEventArgs_TargetColumn)	- Used to get the current column which is the drop target for the card.
* [`TargetIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanDragOverEventArgs.html#Syncfusion_SfKanban_XForms_KanbanDragOverEventArgs_TargetIndex)		- Used to get the new index of the card in target column.

## ColumnsGenerated 

[`ColumnsGenerated`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) event will be fired after the columns are generated automatically. You can access the auto-generated columns using [`SfKanban.ActualColumns`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ActualColumns) property.
