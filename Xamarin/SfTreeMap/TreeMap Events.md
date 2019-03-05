---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: itemselected event
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Events

##ItemSelected

The `ItemSelected` event is fired when an item is selected. Selected item's `DataSource` and `IsSelected` boolean property will be passed as an argument to `ItemSelectedEventArgs`. `IsSelected` boolean property indicates whether an item is selected or not.

You need to set `HighlightOnSelection` boolean property as true to use `ItemSelected` event.

{% tabs %}

{% highlight xaml %}

<Grid>

    <treemap:SfTreeMap x:Name="treemap"  DataSource="{Binding PopulationDetails}" WeightValuePath="Population"
                               ColorValuePath="Growth" ItemSelected="Treemap_ItemSelected" HighlightOnSelection="True">
    </treemap:SfTreeMap>

</Grid>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    treemap.ItemSelected += Treemap_ItemSelected;
    treemap.HighlightOnSelection = true;
}

private void Treemap_ItemSelected(object sender, TreeMapSelectedEventArgs e)
{

}

{% endhighlight %}

{% endtabs %}