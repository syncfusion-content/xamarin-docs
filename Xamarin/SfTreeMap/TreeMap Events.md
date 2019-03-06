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

The `ItemSelected` event occurs when an item is selected. The Selected item's `DataSource` and `IsSelected` boolean property will be passed as arguments to `ItemSelectedEventArgs`. The `IsSelected` boolean property indicates whether the item has been selected.

Set the `HighlightOnSelection` boolean property to true to use the `ItemSelected` event.

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