---
layout: post
title: Syncfusion.Xamarin.Forms TreeMap-Elements
description: treemap elements
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Elements

TreeMap contains various elements such as,

* Legend
* Headers
* Labels

## Legend

You can set the color value of **leaf nodes** using `LegendSettings`. This legend is appropriate only for the **TreeMap** whose leaf nodes are colored using `RangeColorMapping`.

You can set `ShowLegend` property value to **“True”** to enable or disable legend visibility.

### TreeMap Legend

You can decide the size of the legend icons by setting `IconSize` property of the `LegendSettings` property avail in **TreeMap**.

### Label for Legend

You can customize the labels of the **legend item** using `legendLabel` property of `RangeColorMapping`. 

{% highlight c# %}

    LegendSettings legendSettings = new LegendSettings();
    legendSettings.ShowLegend= true;
    legendSettings.IconSize = new Size(15, 15);
    legendSettings.Size = new Size (350, 100);
    legendSettings.LabelStyle.Color = Color.Black;
    treeMap.LegendSettings= legendSettings;

{% endhighlight %}

![TreeMap Legend](Getting-Started_images/Legend.jpg)



## Header

You can set headers for each level by setting the `ShowHeader` property of the each **TreeMap** levels. The `HeaderHeight` property helps to set the height of the header and GroupPath value determines the header value. 

{% highlight c# %}

            TreeMapFlatLevel level = new TreeMapFlatLevel()
            {
                HeaderStyle = new Syncfusion.SfTreeMap.XForms.Style() { Color = Color.Black },
                GroupPath = "Continent",
                HeaderHeight = 20,
                GroupGap = 5,
                ShowHeader = true
            };
            treeMap.Levels.Add(level);     


{% endhighlight %} 


![TreeMap Header](Getting-Started_images/Header.jpg)

## Data Label

The `ShowLabels` property is used to enable or disable the labels in leaf nodes. The `LabelPath` property allows you to set values for labels.

{% tabs %}

{% highlight xaml %}

            <treeMap:SfTreeMap.LeafItemSettings>
                <treeMap:LeafItemSettings  LabelPath="Country" ShowLabels="True">
                </treeMap:LeafItemSettings>
            </treeMap:SfTreeMap.LeafItemSettings>

{% endhighlight %}

{% highlight c# %}

            treeMap.LeafItemSettings.ShowLabels = true;
            treeMap.LeafItemSettings.LabelPath = "Country";
 
{% endhighlight %}
{% endtabs %} 


![Treemap Datalabel](Getting-Started_images/ShowLabel.jpg)

### To avoid overlap in data labels

The `OverflowMode` property aligns the labels within the leaf node bounds by using `Trim`, `Wrap`, and `Hide` options. The default value of the `OverflowMode` property is Trim.

#### Trim
Data labels can be trim inside the leaf node bounds using property OverflowMode `Trim` option.

{% tabs %}

{% highlight xaml %}

            <treeMap:SfTreeMap.LeafItemSettings>
                <treeMap:LeafItemSettings  LabelPath="Country" OverFlowMode="Trim">
                </treeMap:LeafItemSettings>
            </treeMap:SfTreeMap.LeafItemSettings>

{% endhighlight %}

{% highlight c# %}

    treeMap.LeafItemSettings.OverFlowMode = LabelOverflowMode.Trim;
 
{% endhighlight %}
{% endtabs %}

![TreeMap DataLabel Trim](Getting-Started_images/LabelTrim.jpg)

#### Wrap
Data labels can be wrap inside the leaf node bounds using property OverflowMode `Wrap` option.

{% tabs %}

{% highlight xaml %}

            <treeMap:SfTreeMap.LeafItemSettings>
                <treeMap:LeafItemSettings  LabelPath="Country" OverFlowMode="Wrap">
                </treeMap:LeafItemSettings>
            </treeMap:SfTreeMap.LeafItemSettings>

{% endhighlight %}

{% highlight c# %}

    treeMap.LeafItemSettings.OverFlowMode = LabelOverflowMode.Wrap;
 
{% endhighlight %}
{% endtabs %}

![TreeMap DataLabel Wrap](Getting-Started_images/LabelWrap.jpg)

#### Hide
Data labels can be hide inside the leaf node bounds using property OverflowMode `Hide` option. 

{% tabs %}

{% highlight xaml %}

            <treeMap:SfTreeMap.LeafItemSettings>
                <treeMap:LeafItemSettings  LabelPath="Country" OverFlowMode="Hide">
                </treeMap:LeafItemSettings>
            </treeMap:SfTreeMap.LeafItemSettings>

{% endhighlight %}

{% highlight c# %}

    treeMap.LeafItemSettings.OverFlowMode = LabelOverflowMode.Hide;
 
{% endhighlight %}
{% endtabs %}

![TreeMap Datalabel Hide](Getting-Started_images/LabelHide.jpg)

### Customize data labels

The Data Label can be customized by using the `LabelStyle` property in LeafItemSettings. The font color, size, attribute and family can be customized using the `FontSize, FontAttributes, FontFamily and Color` properties.

{% tabs %}

{% highlight xaml %}

            <treeMap:SfTreeMap.LeafItemSettings>
                <treeMap:LeafItemSettings  LabelPath="Country" OverFlowMode="Trim">
                    <treeMap:LeafItemSettings.LabelStyle>
                        <treeMap:Style Color="Blue" FontSize="15" FontAttributes="Bold">
                            <treeMap:Style.FontFamily>
                                <OnPlatform x:TypeArguments="x:String" iOS="Chalkduster" Android="cursive" WinPhone="Chiller" />
                            </treeMap:Style.FontFamily>
                        </treeMap:Style>
                    </treeMap:LeafItemSettings.LabelStyle>
                </treeMap:LeafItemSettings>
            </treeMap:SfTreeMap.LeafItemSettings>

{% endhighlight %}

{% highlight c# %}

            treeMap.LeafItemSettings.LabelStyle.FontSize = 15;
            treeMap.LeafItemSettings.LabelStyle.FontAttributes = FontAttributes.Bold;
            treeMap.LeafItemSettings.LabelStyle.FontFamily = Device.RuntimePlatform == Device.iOS ? "Chalkduster" : Device.RuntimePlatform == Device.Android ? "cursive" : "Chiller";
            treeMap.LeafItemSettings.LabelStyle.Color = Color.Blue;
 
{% endhighlight %}

{% endtabs %}

![TreeMap customized DataLabel](Getting-Started_images/LabelCustomize.jpg)
