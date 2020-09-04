---
layout: post
title: Appearance
platform: xamarin
control: ProgressBar
documentation: ug
---

# Appearance

## Angle

The appearance of the circular progress bar can be customized to semi-circle, arc, etc. The start and end angles can be customized using the [`StartAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_StartAngle) and [`EndAngle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_EndAngle) properties. 

The following code sample demonstrates how to change the appearance of the circular progress bar to semi-circle.

{% tabs %} 

{% highlight xaml %}

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Progress="75" StartAngle="180" EndAngle="360" />

{% endhighlight %}

{% highlight c# %}

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 75;

circularProgressBar.StartAngle = 180;

circularProgressBar.EndAngle = 360;

{% endhighlight %}

{% endtabs %} 

![](overview_images/angle.png)

## Range colors

You can visualize the multiple ranges with different colors that are mapped to each range to enhance the readability of progress. 

The colors can be mapped to the specific ranges using the [`RangeColors`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_RangeColors) property, which holds a collection of [`RangeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html). 

The following properties in the [`RangeColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html) are used to map the colors to a range:

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html#Syncfusion_XForms_ProgressBar_RangeColor_Color): Represents the color to the specified range.
* [`Start`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html#Syncfusion_XForms_ProgressBar_RangeColor_Start): Represents the start range of the color.
* [`End`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html#Syncfusion_XForms_ProgressBar_RangeColor_End): Represents the end range of the color.
* [`IsGradient`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.RangeColor.html#Syncfusion_XForms_ProgressBar_RangeColor_IsGradient): Represents whether the gradient effect is applied to the color.

The following code sample demonstrates how to map the solid color range in the progress bar.

{% tabs %} 

{% highlight xaml %}

<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar Progress="100">

 <progressBar:SfLinearProgressBar.RangeColors>

   <progressBar:RangeColorCollection>

      <progressBar:RangeColor Color="#00bdaf" Start="0" End="25"/>

      <progressBar:RangeColor Color="#2f7ecc" Start="25" End="50"/>

      <progressBar:RangeColor Color="#e9648e" Start="50" End="75"/>

      <progressBar:RangeColor Color="#fbb78a" Start="75" End="100"/>

    </progressBar:RangeColorCollection>

   </progressBar:SfLinearProgressBar.RangeColors>

</progressBar:SfLinearProgressBar>

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar Progress="100" ProgressColor="#FF90a84e">

 <progressBar:SfCircularProgressBar.RangeColors>

   <progressBar:RangeColorCollection>

      <progressBar:RangeColor Color="#00bdaf" Start="0" End="25"/>

      <progressBar:RangeColor Color="#2f7ecc" Start="25" End="50"/>

      <progressBar:RangeColor Color="#e9648e" Start="50" End="75"/>

      <progressBar:RangeColor Color="#fbb78a" Start="75" End="100"/>

    </progressBar:RangeColorCollection>

   </progressBar:SfCircularProgressBar.RangeColors>

</progressBar:SfCircularProgressBar>

{% endhighlight %}

{% highlight c# %}

// Using linear progress bar.

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

RangeColorCollection rangeColors = new RangeColorCollection();

rangeColors.Add(new RangeColor() { Color = Color.FromHex("00bdaf"), Start = 0, End = 25 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("2f7ecc"), Start = 25, End = 50 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("e9648e"), Start = 50, End = 75 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("fbb78a"), Start = 75, End = 100 });

linearProgressBar.RangeColors = rangeColors;

// Using circular progress bar.

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 100;

circularProgressBar.ProgressColor = Color.FromHex("FF90a84e");

RangeColorCollection rangeColors = new RangeColorCollection();

rangeColors.Add(new RangeColor() { Color = Color.FromHex("00bdaf"), Start = 0, End = 25 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("2f7ecc"), Start = 25, End = 50 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("e9648e"), Start = 50, End = 75 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("fbb78a"), Start = 75, End = 100 });

circularProgressBar.RangeColors = rangeColors;

{% endhighlight %}

{% endtabs %} 

![](overview_images/rangecolors.png)

The following code sample demonstrates how to apply gradient transition effect to the range colors in the linear progress bar.

{% tabs %} 

{% highlight xaml %}

<progressBar:SfLinearProgressBar Progress="100" >

   <progressBar:SfLinearProgressBar.RangeColors>

     <progressBar:RangeColorCollection>

        <progressBar:RangeColor IsGradient="True" Color="#88A0D9EF" Start="0" End="25"/>

        <progressBar:RangeColor IsGradient="True" Color="#AA62C1E5" Start="25" End="50"/>

        <progressBar:RangeColor IsGradient="True" Color="#DD20A7DB" Start="50" End="75"/>

        <progressBar:RangeColor IsGradient="True" Color="#FF1C96C5" Start="75" End="100"/>

   </progressBar:RangeColorCollection>

  </progressBar:SfLinearProgressBar.RangeColors>

</progressBar:SfLinearProgressBar>

<progressBar:SfCircularProgressBar Progress="100" ProgressColor="#FF90a84e">

   <progressBar:SfCircularProgressBar.RangeColors>

     <progressBar:RangeColorCollection>

        <progressBar:RangeColor IsGradient="True" Color="#88A0D9EF" Start="0" End="25"/>

        <progressBar:RangeColor IsGradient="True" Color="#AA62C1E5" Start="25" End="50"/>

        <progressBar:RangeColor IsGradient="True" Color="#DD20A7DB" Start="50" End="75"/>

        <progressBar:RangeColor IsGradient="True" Color="#FF1C96C5" Start="75" End="100"/>

   </progressBar:RangeColorCollection>

  </progressBar:SfCircularProgressBar.RangeColors>

</progressBar:SfCircularProgressBar>

{% endhighlight %}

{% highlight c# %}

// Using linear progress bar.

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

RangeColorCollection rangeColors = new RangeColorCollection();

rangeColors.Add(new RangeColor() { Color = Color.FromHex("88A0D9EF"), IsGradient = true, Start = 0 , End = 25 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("AA62C1E5"), IsGradient = true, Start = 25, End = 50 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("DD20A7DB"), IsGradient = true, Start = 50, End = 75 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("FF1C96C5"), IsGradient = true, Start = 75, End = 100 });

linearProgressBar.RangeColors = rangeColors;

// Using circular progress bar.

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 100;

circularProgressBar.ProgressColor = Color.FromHex("FF90a84e");

RangeColorCollection rangeColors = new RangeColorCollection();

rangeColors.Add(new RangeColor() { Color = Color.FromHex("88A0D9EF"), IsGradient = true, Start = 0 , End = 25 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("AA62C1E5"), IsGradient = true, Start = 25, End = 50 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("DD20A7DB"), IsGradient = true, Start = 50, End = 75 });

rangeColors.Add(new RangeColor() { Color = Color.FromHex("FF1C96C5"), IsGradient = true, Start = 75, End = 100 });

circularProgressBar.RangeColors = rangeColors;

{% endhighlight %}

{% endtabs %} 

![](overview_images/gradient.png)

## Thickness

### Linear progress bar

In the linear progress bar, the height of the track and padding of the progress indicator can be customized using the [`TrackHeight`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_TrackHeight) and [`Padding`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_Padding) properties, respectively.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar Progress="100" TrackHeight="10" Padding="2">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.TrackHeight = 10;

linearProgressBar.Padding = 2;

{% endhighlight %}

{% endtabs %} 

![](overview_images/thickness_linear.png)

### Circular progress bar

The following properties are used to customize the appearance of the circular progress bar:

* [`IndicatorOuterRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_IndicatorOuterRadius): Defines the outer radius of the progress indicator.
* [`IndicatorInnerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_IndicatorInnerRadius): Defines the inner radius of the progress indicator.
* [`TrackOuterRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_TrackOuterRadius): Defines the outer radius of the track indicator.
* [`TrackInnerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfCircularProgressBar.html#Syncfusion_XForms_ProgressBar_SfCircularProgressBar_TrackInnerRadius): Defines the inner radius of the track indicator.

The following code sample demonstrates how to customize the appearance of circular progress bar.

{% tabs %} 

{% highlight xaml %}

<!--Circular progress bar with radius customization -->

<progressBar:SfCircularProgressBar x:Name="TrackOutsideProgressBar" Grid.Column="0" Grid.Row="0"
                                   Progress="75" Margin="0,10,0,0" IndicatorOuterRadius="0.7" 
                                   IndicatorInnerRadius="0.65" ShowProgressValue="False">
</progressBar:SfCircularProgressBar>       

{% endhighlight %}

{% highlight c# %}
SfCircularProgressBar trackOutsideProgressBar = new SfCircularProgressBar();

trackOutsideProgressBar.Progress = 75;

trackOutsideProgressBar.IndicatorOuterRadius = 0.7;

trackOutsideProgressBar.IndicatorInnerRadius = 0.65;

trackOutsideProgressBar.ShowProgressValue = false;

{% endhighlight %}

{% endtabs %} 

![](overview_images/appearance.png)

## Corner radius

The [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_CornerRadius) property is used to customize the rounded edges in the linear progress bar as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar Progress="50" TrackHeight="10" CornerRadius="10">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 50;

linearProgressBar.CornerRadius = 10;

{% endhighlight %}

{% endtabs %} 

![](overview_images/cornerradius.png)

## Color customization

The following properties are used to customize the color in the progress bar:

* [`ProgressColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_ProgressColor): Represents the color of the progress indicator.
* [`TrackColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_TrackColor): Represents the color of the track indicator.

The following code sample demonstrates the color customization in progress and track indicator.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar Progress="75" TrackColor="#3351483a" ProgressColor="#FF51483a">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 75;

linearProgressBar.ProgressColor = Color.FromHex("FF51483a");

linearProgressBar.TrackColor = Color.FromHex("3351483a");

{% endhighlight %}

{% endtabs %} 

![](overview_images/color1.png)

The linear progress bar provides support to customize the color for the secondary progress bar using the [`SecondaryProgressColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_SecondaryProgressColor) property as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar Progress="25" SecondaryProgress="75" SecondaryProgressColor="CornflowerBlue"></progressBar:SfLinearProgressBar>
{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 25;

linearProgressBar.SecondaryProgress = 75;

linearProgressBar.SecondaryProgressColor = Color.CornflowerBlue;

{% endhighlight %}

{% endtabs %} 

![](overview_images/color2.png)

