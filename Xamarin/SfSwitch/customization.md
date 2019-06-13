---
layout: post
title: Customization with visual states in SfSwitch Xamarin.Forms.
description: Explaining about customization based on visual states in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

## Customization with Visual States

The Switch control provides options to customize the color based on the states. The below code example illustrates this customization.

### Solid Colors

The following properties are used to apply solid colors in the thumb, track, border and busy indicator respectively.

* ThumbColor – Represents the color for the thumb.
* ThumbBorderColor – Represents the border color for thumb.
* TrackBorderColor – Represents the color for the border of the switch.
* TrackColor – Represents the color for the slider.
* BusyIndicatorColor – Represents the color for the busy indicator which is displayed inside the thumb.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch VisualType="Custom" IsBusy="True" >

<VisualStateManager.VisualStateGroups>

<VisualStateGroup  x:Name="CommonStates">

<VisualState x:Name="On">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OnState" 

ThumbBorderColor="DarkCyan" ThumbColor="Aqua" TrackBorderColor="Green" TrackColor="GreenYellow" BusyIndicatorColor="Coral" />

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

<VisualState x:Name="Off">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OffState" 

ThumbBorderColor="DarkCyan" ThumbColor="Aqua" TrackBorderColor="Green" TrackColor="GreenYellow"/>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

<VisualState x:Name="Indeterminate">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:IndeterminateState" 

ThumbBorderColor="DarkCyan" TrackBorderColor="Green" ThumbColor="Aqua" TrackColor="GreenYellow"/>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

</VisualStateGroup>

</VisualStateManager.VisualStateGroups>

</syncfusion:SfSwitch>

{% endhighlight %}

{% endtabs %}

### Gradient Colors

You can also specify the range of colors in thumb and track using ThumbGradientColor and TrackGradientColor as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<syncfusion:DefaultSwitchSettings.ThumbGradientColor>

<graphics:SfLinearGradientBrush>

<graphics:SfLinearGradientBrush.GradientStops>

<graphics:GradientStopCollection>

<graphics:SfGradientStop Color="White" Offset="0"></graphics:SfGradientStop>

<graphics:SfGradientStop Color="LightSkyBlue" Offset="0.5"></graphics:SfGradientStop>

<graphics:SfGradientStop Color="White" Offset="1"></graphics:SfGradientStop>

</graphics:GradientStopCollection>

</graphics:SfLinearGradientBrush.GradientStops>

</graphics:SfLinearGradientBrush>

</syncfusion:DefaultSwitchSettings.ThumbGradientColor>

<syncfusion:DefaultSwitchSettings.TrackGradientColor>

<graphics:SfLinearGradientBrush>

<graphics:SfLinearGradientBrush.GradientStops>

<graphics:GradientStopCollection>

<graphics:SfGradientStop Color="White" Offset="0"></graphics:SfGradientStop>

<graphics:SfGradientStop Color="LightCoral" Offset="0.25"></graphics:SfGradientStop>

<graphics:SfGradientStop Color="Red" Offset="0.5"></graphics:SfGradientStop>

<graphics:SfGradientStop Color="LightSalmon" Offset="0.75"></graphics:SfGradientStop>

</graphics:GradientStopCollection>

</graphics:SfLinearGradientBrush.GradientStops>

</graphics:SfLinearGradientBrush>

</syncfusion:DefaultSwitchSettings.TrackGradientColor>

{% endhighlight %}

{% endtabs %}

### Sizing

In switch the sizing of the thumb and the track can be controlled using the following properties.

* TrackCornerradius – Represents a double value to create curved corner.
* TrackBorderWidth - Represents a double value for defining the track border width.
* TrackWidthRequest - Represents a double value for defining the track width.
* TrackHeightRequest - Represents double value for defining the track height.
* ThumbBorderWidth - Represents a double value for defining the thumb border width.
* ThumbCornerRadius - Represents a double value to create curved corner.
* ThumbHeightRequest - Represents double value for defining the thumb height.
* ThumbWidthRequest - Represents double value for defining the thumb width.

The following example shows the customization of the size in the track and thumb.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch  VisualType="Custom" >

<VisualStateManager.VisualStateGroups>

<VisualStateGroup  x:Name="CommonStates">

<VisualState x:Name="On">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings  x:TypeArguments="syncfusion:OnState" 

ThumbBorderWidth="2" TrackBorderWidth="2"  

TrackHeightRequest="25" TrackWidthRequest="75" TrackCornerRadius="4"

ThumbCornerRadius="4" ThumbHeightRequest="10" ThumbWidthRequest="10">

</syncfusion:DefaultSwitchSettings>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

<VisualState x:Name="Off">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OffState" 

ThumbBorderWidth="2" TrackBorderWidth="2"  

TrackHeightRequest="25" TrackWidthRequest="75" TrackCornerRadius="4"

ThumbCornerRadius="4" ThumbHeightRequest="10" ThumbWidthRequest="10"/>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

</VisualStateGroup>

</VisualStateManager.VisualStateGroups>

</syncfusion:SfSwitch>


{% endhighlight %}

{% endtabs %}

### Images

Images can also be added to enhance the visual appearance. The following properties are used to add the images.

* TrackImageSource – Represents the image source for the track.
* ThumbImageSource – Represents the image source for thumb.

The following code example illustrates the image customization.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch IsOn="False" HorizontalOptions="Center" VisualType="Custom">

<VisualStateManager.VisualStateGroups>

<VisualStateGroup x:Name="CommonStates">

<VisualState x:Name="On">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OnState"

TrackImageSource="switchbg2.png"

ThumbImageSource="switchmoon.png"/>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

<VisualState x:Name="Off">

<VisualState.Setters>

<Setter Property="SwitchSettings">

<Setter.Value>

<syncfusion:DefaultSwitchSettings x:TypeArguments="syncfusion:OffState"

TrackImageSource="switchbg.png"

ThumbImageSource="switchsun.png"/>

</Setter.Value>

</Setter>

</VisualState.Setters>

</VisualState>

</VisualStateGroup>

</VisualStateManager.VisualStateGroups>

</syncfusion:SfSwitch>

{% endhighlight %}

{% endtabs %}
