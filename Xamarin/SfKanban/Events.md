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
