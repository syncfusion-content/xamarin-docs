---
layout: post
title: Scroll to Row Column Index | SfDataGrid | Xamarin | Syncfusion
description: How to scroll programmatically to particular Row and Column in a SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---
## Scroll to Row and Column Index

* You can scroll programmatically to particular Row and Column using `SfDataGrid.ScrollToRowColumnIndex` method by passing row and column index.

{% highlight C# %}

dataGrid.ScrollToRowColumnIndex(int rowIndex, int columnIndex);

{% endhighlight %}

## Scroll to Row Index

* You can scroll programmatically to particular Row `SfDataGrid.ScrollToRowIndex` method by passing row index.

{% highlight C# %}

dataGrid.ScrollToRowIndex(int rowIndex);

{% endhighlight %}

## Scroll to Column Index

* You can scroll programmatically to particular Column `SfDataGrid.ScrollToColumnIndex` method by passing column index.

{% highlight C# %}

dataGrid.ScrollToColumnIndex(int columnIndex);

{% endhighlight %}
