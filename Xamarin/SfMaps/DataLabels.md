---
layout: post
title: DataLabels
description: This section describes about DataLabels.
platform: xamarin
control: SfMaps
documentation: ug
---

# DataLabels

Data labels are used to display the values of the shapes.

## Adding data labels

 [`ShowMapItems`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeFileLayer~ShowMapItems.html) property is a Boolean property that displays or hides the data labels in shapes. You must set the [`ShapeValuePath`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.ShapeSetting~ShapeValuePath.html) property to get the data labels which is bound for each shape.

{% tabs %}

{% highlight xml %}

     <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">
        
        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp" ShowMapItems="True" ItemsSource="{Binding DataSource}" ShapeIDPath="Name" ShapeIDTableField="STATE_NAME">

                <maps:ShapeFileLayer.ShapeSettings>

                    <maps:ShapeSetting   ShapeValuePath="Type"  ShapeFill="LightGray"/>

                </maps:ShapeFileLayer.ShapeSettings>

            </maps:ShapeFileLayer>
            
        </maps:SfMaps.Layers>
        
    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

             SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowMapItems = true;

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            SublayerViewModel sublayerViewModel = new SublayerViewModel();

            layer.ItemsSource = sublayerViewModel.DataSource;

            layer.ShapeIDPath = "Name";

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Type";

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel1.png)

## Customizing data labels

Data labels can be customized using the [`DataLabelSetting`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting.html) property in shape file layer. The font attribute, color, font size and font family can be customized using [`FontAttributes`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~FontAttributes.html), [`TextColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~TextColor.html), [`FontSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~FontSize.html) and [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~FontFamily.html).

{% tabs %}

{% highlight xml %}

      <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">
        
        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp" ShowMapItems="True" ItemsSource="{Binding DataSource}" ShapeIDPath="Name" ShapeIDTableField="STATE_NAME">
               
                <maps:ShapeFileLayer.ShapeSettings>

                    <maps:ShapeSetting   ShapeValuePath="Type"  ShapeFill="LightGray"/>

                </maps:ShapeFileLayer.ShapeSettings>

                <maps:ShapeFileLayer.DataLabelSettings>

                    <maps:DataLabelSetting TextColor="Blue" FontAttributes="Bold" FontFamily="cursive" FontSize="12" />

                </maps:ShapeFileLayer.DataLabelSettings>
                
            </maps:ShapeFileLayer>
            
        </maps:SfMaps.Layers>
        
    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

            SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowMapItems = true;

            SublayerViewModel sublayerViewModel = new SublayerViewModel();

            layer.ItemsSource = sublayerViewModel.DataSource;

            layer.ShapeIDPath = "Name";

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Type";

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.TextColor = Color.Blue;

            dataLabelSetting.FontAttributes = FontAttributes.Bold;

            dataLabelSetting.FontFamily = "cursive";

            dataLabelSetting.FontSize = 12;

            layer.DataLabelSettings = dataLabelSetting;

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel2.png)

## Setting contrast color

Based on the Shape color, contrast color will be applied for the data labels.

{% tabs %}

{% highlight xml %}

     <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">

        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp" ShowMapItems="True" ItemsSource="{Binding DataSource}" ShapeIDPath="Name" ShapeIDTableField="STATE_NAME">

                <maps:ShapeFileLayer.ShapeSettings>
                    
                    <maps:ShapeSetting  ShapeFill="#A9D9F7" ShapeValuePath="Type" ShapeColorValuePath="index" >
                        
                        <maps:ShapeSetting.ColorMappings>
                        
                            <maps:RangeColorMapping To="25" From="0" Color="#FFD84F"/>
                            
                            <maps:RangeColorMapping To="50" From="25" Color="#316DB5"/>
                         
                        </maps:ShapeSetting.ColorMappings>
                        
                    </maps:ShapeSetting>
                    
                </maps:ShapeFileLayer.ShapeSettings>
                
                <maps:ShapeFileLayer.DataLabelSettings>
                    
                    <maps:DataLabelSetting IntersectionAction="None" SmartLabelMode="Trim"/>
                    
                </maps:ShapeFileLayer.DataLabelSettings>

            </maps:ShapeFileLayer>

        </maps:SfMaps.Layers>

    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

             SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowMapItems = true;

            layer.ShapeSettings.ShapeFill = Color.DarkBlue;

            SublayerViewModel sublayerViewModel = new SublayerViewModel();

            layer.ItemsSource = sublayerViewModel.DataSource;

            layer.ShapeIDPath = "Name";

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "Type";

            layer.ShapeSettings.ShapeColorValuePath = "index";

            ObservableCollection<ColorMapping> colorMapping = new ObservableCollection<ColorMapping>();

            RangeColorMapping rangeColorMapping = new RangeColorMapping();

            rangeColorMapping.From = 0;

            rangeColorMapping.To = 25;

            rangeColorMapping.Color = Color.FromHex("#FFD84F");

            colorMapping.Add(rangeColorMapping);

            RangeColorMapping rangeColorMapping1 = new RangeColorMapping();

            rangeColorMapping1.From = 25;

            rangeColorMapping1.To = 50;

            rangeColorMapping1.Color = Color.FromHex("#316DB5");

            colorMapping.Add(rangeColorMapping1);

            layer.ShapeSettings.ColorMappings = colorMapping;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.IntersectionAction = IntersectAction.None;

            dataLabelSetting.SmartLabelMode = IntersectAction.Trim;

            layer.DataLabelSettings = dataLabelSetting;

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel3.png)


## Setting smart label mode

[`SmartLabelMode`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~SmartLabelMode.html) smartly aligns labels within shape boundaries and avoids label overlap. Labels can be customized using the Hide, Trim and None options. First, you should set the [`IntersectionAction`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~IntersectionAction.html) property as None.

{% tabs %}

{% highlight xml %}

    <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">
        
        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp" ShowMapItems="True" ItemsSource="{Binding Data}" ShapeIDPath="State" ShapeIDTableField="STATE_NAME">
               
                <maps:ShapeFileLayer.ShapeSettings>

                    <maps:ShapeSetting   ShapeValuePath="State" ShapeFill="LightGray" />

                </maps:ShapeFileLayer.ShapeSettings>

                <maps:ShapeFileLayer.DataLabelSettings>

                    <maps:DataLabelSetting SmartLabelMode="Trim" IntersectionAction="None"/>

                </maps:ShapeFileLayer.DataLabelSettings>
                
            </maps:ShapeFileLayer>
            
        </maps:SfMaps.Layers>
        
    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

            SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowMapItems = true;

            ViewModel sublayerViewModel = new ViewModel();

            layer.ItemsSource = sublayerViewModel.Data;

            layer.ShapeIDPath = "State";

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "State";

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.SmartLabelMode = IntersectAction.Trim;

            dataLabelSetting.IntersectionAction = IntersectAction.None;

            layer.DataLabelSettings = dataLabelSetting;

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel4.png)

## Setting intersection action

[`IntersectionAction`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~IntersectionAction.html) smartly aligns labels which is overlapped with another label. Labels can be customized using the Hide, Trim and None options. First, you should set the [`SmartLabelMode`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfMaps.XForms~Syncfusion.SfMaps.XForms.DataLabelSetting~SmartLabelMode.html) property as None.

{% tabs %}

{% highlight xml %}

    <maps:SfMaps x:Name="sfmap"  BackgroundColor="White">

        <maps:SfMaps.Layers>

            <maps:ShapeFileLayer Uri="usa_state.shp" ShowMapItems="True" ItemsSource="{Binding Data}" ShapeIDPath="State" ShapeIDTableField="STATE_NAME">

                <maps:ShapeFileLayer.ShapeSettings>

                    <maps:ShapeSetting   ShapeValuePath="State" ShapeFill="LightGray" />

                </maps:ShapeFileLayer.ShapeSettings>

                <maps:ShapeFileLayer.DataLabelSettings>

                    <maps:DataLabelSetting IntersectionAction="Hide" SmartLabelMode="None"/>

                </maps:ShapeFileLayer.DataLabelSettings>

            </maps:ShapeFileLayer>

        </maps:SfMaps.Layers>

    </maps:SfMaps>

{% endhighlight %}

{% highlight c# %}

           SfMaps map = new SfMaps();

            map.BackgroundColor = Color.White;

            ShapeFileLayer layer = new ShapeFileLayer();

            layer.Uri = "usa_state.shp";

            layer.ShowMapItems = true;

            ViewModel sublayerViewModel = new ViewModel();

            layer.ItemsSource = sublayerViewModel.Data;

            layer.ShapeIDPath = "State";

            layer.ShapeIDTableField = "STATE_NAME";

            layer.ShapeSettings.ShapeValuePath = "State";

            layer.ShapeSettings.ShapeFill = Color.LightGray;

            DataLabelSetting dataLabelSetting = new DataLabelSetting();

            dataLabelSetting.IntersectionAction = IntersectAction.Hide;

            dataLabelSetting.SmartLabelMode = IntersectAction.None;

            layer.DataLabelSettings = dataLabelSetting;

            map.Layers.Add(layer);

            this.Content = map;

{% endhighlight %}

{% endtabs %}

![DataLabel Image](Images/DataLabel5.png)





         