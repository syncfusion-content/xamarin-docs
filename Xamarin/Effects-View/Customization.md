---
layout: post
title: Customization of Syncfusion EffectsView control in Xamarin.Forms
description: This section describes how to provide various customisation of the Syncfusion EffectsView control in Xamarin.Forms. 
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Customization of SfEffectsView

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides support to customize the corner radius, animation duration, color, and more. This section explains how to customize the effects view control.


## CornerRadius

The [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_CornerRadius) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the corner radius of the [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView CornerRadius="0,25">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    CornerRadius = new Thickness(0, 25)
};

{% endhighlight %}

{% endtabs %}

![EffectsView CornerRadius customization](Customization_images/EffectsView_CornerRadius.jpg)

## RippleAnimationDuration

The [`RippleAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleAnimationDuration) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of ripple animation.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView RippleAnimationDuration="800">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    RippleAnimationDuration = 800
};

{% endhighlight %}

{% endtabs %}

## ScaleAnimationDuration

The [`ScaleAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleAnimationDuration) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of scale animation.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    ScaleAnimationDuration="800"
    LongPressEffects="Scale"
    ScaleFactor="0.85">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    ScaleAnimationDuration = 800,
    LongPressEffects = SfEffects.Scale,
    ScaleFactor = 0.85
};

{% endhighlight %}

{% endtabs %}

## RotationAnimationDuration

The [`RotationAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RotationAnimationDuration) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of rotation animation.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    RotationAnimationDuration="800"
    Angle="180"
    TouchDownEffects="Rotation">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    RotationAnimationDuration = 800,
    Angle = 180,
    LongPressEffects = SfEffects.Rotation
};

{% endhighlight %}

{% endtabs %}

## InitialRippleFactor

The [`InitialRippleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_InitialRippleFactor) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the radius of the ripple when ripple animation starts.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView InitialRippleFactor="0.1">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    InitialRippleFactor = 0.1
};

{% endhighlight %}

{% endtabs %}

![InitialRippleFactor customization](Customization_images/EffectsView_InitialRippleFactor.gif)

## ScaleFactor

The [`ScaleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleFactor) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the scale of the view.

{% tabs %} 

{% highlight xaml %} 

 <syncEffectsView:SfEffectsView
     ScaleFactor="0.85"
     LongPressEffects="Scale"
     TouchDownEffects="None"
     TouchUpEffects="None">
     ...
 </syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    ScaleFactor = 0.85,
    LongPressEffects = SfEffects.Scale,
    TouchDownEffects = SfEffects.None,
    TouchUpEffects = SfEffects.None
};

{% endhighlight %}

{% endtabs %}

![ScaleFactor customization](Customization_images/EffectsView_Scale.gif)

## HighlightColor

The [`HighlightColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_HighlightColor) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of highlight effect.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
     HighlightColor="#2196F3"
     TouchDownEffects="Highlight">
     ...
 </syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    HighlightColor = Color.FromHex("#2196F3"),
    TouchDownEffects = SfEffects.Highlight
};

{% endhighlight %}

{% endtabs %}

![Highlight Color customization](Customization_images/EffectsView_Highlight.png)

## RippleColor

The [`RippleColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleColor) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of ripple.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView RippleColor="#2196F3">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    RippleColor = Color.FromHex("#2196F3")
};
            
{% endhighlight %}

{% endtabs %}

![Ripple Color customization](Customization_images/EffectsView_RippleColor.gif)

## SelectionColor

The [`SelectionColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_SelectionColor) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of selection effect.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    LongPressEffects="Selection"
    SelectionColor="#2196F3">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Selection,
    SelectionColor = Color.FromHex("#2196F3")
};

{% endhighlight %}

{% endtabs %}

![Selection Color customization](Customization_images/EffectsView_Selection.png)

## Angle

The [`Angle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Angle) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the rotation angle.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    Angle="180"
    TouchDownEffects="Ripple,Rotation">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    Angle = 180,
    TouchDownEffects = SfEffects.Ripple | SfEffects.Rotation
};
            
{% endhighlight %}

{% endtabs %}

![Rotation Angle customization](Customization_images/EffectsView_Rotation.png)

## See also

[How to get the selected item from ListView while using SfEffectsView within ItemTemplate](https://www.syncfusion.com/kb/11661/how-to-get-the-selected-item-from-listview-while-using-effectsview-within-itemtemplate)

[How to use SfEffectsView in SfListView](https://www.syncfusion.com/kb/11030/how-to-use-effects-view-in-listview-sflistview-xamarin-forms)