---
layout: post
title: ItemSelected Event in Syncfusion SfTreeMap control
description: This section describes the ItemSelected event support of SfTreeMap control in Xamarin.Forms platform. 
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Events

## ItemSelected

The [`ItemSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.SfTreeMap.html) event occurs when an item is selected. The selected leaf node underlying data item and IsSelected boolean property will be passed as arguments to ItemSelectedEventArgs. The IsSelected property indicates whether the item has been selected.

Set the [`HighlightOnSelection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.SfTreeMap.html#Syncfusion_SfTreeMap_XForms_SfTreeMap_HighlightOnSelection) property to true to use the `ItemSelected` event.

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

private void Treemap_ItemSelected(object sender, TreeMapItemSelectedEventArgs e)
{
    var selectedItem = e.Item as PopulationDetail;
    bool setSelection = e.IsSelected;
}

{% endhighlight %}

{% endtabs %}

N> We've suggested using DataSource to populate items, when you need Item property value of TreeMapItemSelectedEventArgs.