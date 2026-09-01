---
layout: post
title: Customization in Xamarin Effects View Control | Syncfusion
description: Discover how to customize the Syncfusion Xamarin Effects View (SfEffectsView) control, including corner radius, animation duration, colors, and more.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Customization in Xamarin Effects View (SfEffectsView)

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control offers customization options for corner radius, animation duration, colors, and more. This section provides guidance on customizing the Effects View control.


## CornerRadius

The [`CornerRadius`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_CornerRadius) property allows you to customize the corner radius of the `SfEffectsView`.

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

Customize the duration of ripple animation using the [`RippleAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleAnimationDuration) property.
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

The [`ScaleAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleAnimationDuration) property allows customization of the scale animation duration.

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

Customize the rotation animation duration using the [`RotationAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RotationAnimationDuration) property.
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

Use the [`InitialRippleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_InitialRippleFactor) property to customize the initial ripple radius when the animation starts.

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

Customize the scale of the view using the [`ScaleFactor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ScaleFactor) property.
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

Use the [`HighlightColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_HighlightColor) property to customize the highlight effect color.

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

Customize the ripple color using the [`RippleColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleColor) property.
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

The [`SelectionColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_SelectionColor) property is used to customize the selection effect color.

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

Customize the rotation angle using the [`Angle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_Angle) property.
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

## HighlightColorOpacity

Adjust the opacity of the [`HighlightColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_HighlightColor) using the [`HighlightColorOpacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_HighlightColorOpacity) property. The default value is 0.04, ranging from 0 to 1.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    TouchDownEffects="Highlight"
    HighlightColorOpacity="0.5">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Highlight,
    HighlightColorOpacity = 0.5
};

{% endhighlight %}

{% endtabs %}

![Highlight color opacity customization](Customization_images/EffectsView_HighlightColorOpacity.png)

## RippleColorOpacity

Customize the opacity of the [`RippleColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleColor) using the [`RippleColorOpacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_RippleColorOpacity) property. The default value is 0.12, ranging from 0 to 1.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    TouchDownEffects="Ripple"
    RippleColorOpacity="0.5">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Ripple,
    RippleColorOpacity = 0.5
};

{% endhighlight %}

{% endtabs %}

## SelectionColorOpacity

Adjust the opacity of the [`SelectionColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_SelectionColor) using the [`SelectionColorOpacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_SelectionColorOpacity) property. The default value is 0.12, ranging from 0 to 1.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    LongPressEffects="Selection"
    SelectionColorOpacity="0.5">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Selection,
    SelectionColorOpacity = 0.5
};

{% endhighlight %}

{% endtabs %}

![Selection color opacity customization](Customization_images/EffectsView_SelectionColorOpacity.png)

## See Also

- [How to get the selected item from ListView while using SfEffectsView within ItemTemplate](https://support.syncfusion.com/kb/article/10193/how-to-get-the-selected-item-from-listview-while-using-effectsview-within-itemtemplate)
- [How to use SfEffectsView in SfListView](https://support.syncfusion.com/kb/article/9569/how-to-use-the-effects-view-in-xamarinforms-listview-sflistview)
