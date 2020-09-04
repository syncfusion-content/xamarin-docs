---
layout: post
title: Syncfusion.Xamarin.Forms TreeMap-Elements
description: treemap elements
platform: xamarin
control: TreeMap
documentation: ug
---

# TreeMap Elements

The TreeMap contains the following elements:

* Legends
* Headers
* Labels

## Legend

You can set the color value of leaf nodes using the [`LegendSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LegendSettings.html) property. This legend is appropriate only for the tree map whose leaf nodes are colored using [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.RangeColorMapping.html).

The visibility of legend can be enabled by setting the [`ShowLegend`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LegendSettings.html#Syncfusion_SfTreeMap_XForms_LegendSettings_ShowLegend) property to true.

### TreeMap legends

You can set the size of legend icons by setting the [`IconSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LegendSettings.html#Syncfusion_SfTreeMap_XForms_LegendSettings_IconSize) property of `LegendSettings` in TreeMap.

### Labels for legends

You can customize the labels of the legend items using the [`LegendLabel`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.Range.html#Syncfusion_SfTreeMap_XForms_Range_LegendLabel) property of [`RangeColorMapping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.RangeColorMapping.html). 

{% tabs %}

{% highlight xaml %}

  <treemap:SfTreeMap.LegendSettings>
                <treemap:LegendSettings ShowLegend="True"  Size="700,45">
                    <treemap:LegendSettings.LabelStyle>
                        <treemap:Style Color="Black"></treemap:Style>
                    </treemap:LegendSettings.LabelStyle>
                </treemap:LegendSettings>
            </treemap:SfTreeMap.LegendSettings>

{% endhighlight %} 

{% highlight c# %}

        LegendSettings legendSettings = new LegendSettings();
            legendSettings.ShowLegend = true;
            legendSettings.Size = new Size(700, 45);
            legendSettings.LabelStyle = new Syncfusion.SfTreeMap.XForms.Style() { Color = Color.Black };
            treeMap.LegendSettings = legendSettings;

{% endhighlight %}

{% endtabs %} 

![Treemap legend](Getting-Started_images/Legend.png)

## Header

You can set headers for each level by setting the [`ShowHeader`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.TreeMapLevel.html#Syncfusion_SfTreeMap_XForms_TreeMapLevel_ShowHeader) property of each **TreeMap** level. The [`HeaderHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.TreeMapLevel.html#Syncfusion_SfTreeMap_XForms_TreeMapLevel_HeaderHeight) property helps you set the height of header, and the [`GroupPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.TreeMapFlatLevel.html#Syncfusion_SfTreeMap_XForms_TreeMapFlatLevel_GroupPath) value determines the header value. 

{% tabs %}

{% highlight xaml %}

 <treemap:SfTreeMap.Levels>
                <treemap:TreeMapFlatLevel  HeaderHeight="20" GroupPath = "Continent" GroupGap =" 5" ShowHeader = "true">
                    <treemap:TreeMapFlatLevel.HeaderStyle>
                        <treemap:Style Color= "Black"/>
                    </treemap:TreeMapFlatLevel.HeaderStyle>
                </treemap:TreeMapFlatLevel>
            </treemap:SfTreeMap.Levels>

{% endhighlight %} 

{% highlight c# %}

            TreeMapFlatLevel flatLevel = new TreeMapFlatLevel();
            flatLevel.HeaderHeight = 20;
            flatLevel.GroupPath = "Continent";
            flatLevel.GroupGap = 5;
            flatLevel.ShowHeader = true;
            flatLevel.HeaderStyle = new Syncfusion.SfTreeMap.XForms.Style() { Color = Color.Black };
            treeMap.Levels.Add(flatLevel);   


{% endhighlight %} 

{% endtabs %} 

![Treemap header](Getting-Started_images/GettingStarted.png)

## Data labels

The [`ShowLabels`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LeafItemSettings.html#Syncfusion_SfTreeMap_XForms_LeafItemSettings_ShowLabels) property is used to enable or disable the labels in leaf nodes. The [`LabelPath`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LeafItemSettings.html#Syncfusion_SfTreeMap_XForms_LeafItemSettings_LabelPath) property allows you to set values to labels.

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


![Providing Visibility for data labels in Xamarin.Forms TreeMap](Getting-Started_images/ShowLabel.jpg)

### Avoid overlap in data labels

The [`OverflowMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LeafItemSettings.html#Syncfusion_SfTreeMap_XForms_LeafItemSettings_OverflowMode) property aligns data labels within leaf node boundaries using the `Trim`, `Wrap`, and `Hide` options. The default value of the `OverflowMode` property is Trim.

#### Trim

You can trim the data labels inside the leaf node boundaries using the `Trim` option.

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

![Data label trim support in Xamarin.Forms TreeMap](Getting-Started_images/LabelTrim.jpg)

#### Wrap

You can wrap the data labels inside the leaf node boundaries using the `Wrap` option.

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

![Data label wrap support in Xamarin.Forms TreeMap](Getting-Started_images/LabelWrap.jpg)

#### Hide

You can hide the data labels inside the leaf node boundaries using the `Hide` option. 

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

![Data label hide support in Xamarin.Forms TreeMap](Getting-Started_images/LabelHide.jpg)

### Customize data labels

You can customize the data labels using the [`LabelStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfTreeMap.XForms.LeafItemSettings.html#Syncfusion_SfTreeMap_XForms_LeafItemSettings_LabelStyle) property of LeafItemSettings. The font color, font size, font attribute, and font family can be customized using the `Color`, `FontSize`, `FontAttributes`, and `FontFamily` properties.

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

![Customizing the data labels support in Xamain.Forms TreeMap ](Getting-Started_images/LabelCustomize.jpg)

