---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: This section explains the ItemSelected event support in TreeMap. 
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Events

## ItemSelected

The `ItemSelected` event occurs when an item is selected. The selected Leaf node underlying  data item and IsSelected boolean property will be passed as arguments to ItemSelectedEventArgs. The IsSelected indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfTreeMap.XForms~Syncfusion.SfTreeMap.XForms.SfTreeMap~HighlightOnSelection.html) to true to use the `ItemSelected` event.

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
    var selectedItem = (e.Item as PopulationViewModel);
    bool setSelection = e.IsSelected;
}

{% endhighlight %}

{% endtabs %}