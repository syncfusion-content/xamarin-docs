---
layout: post
title: Customization of Syncfusion EffectsView
description: How to customize effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Customization of SfEffectsView

The [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides support to customize the corner radius, animation duration, color, and more. This section explains how to customize the effects view control.

## RippleAnimationDuration

The [`RippleAnimationDuration`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~RippleAnimationDuration.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of ripple animation.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView RippleAnimationDuration="800">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    RippleAnimationDuration = 800
};

{% endhighlight %}

{% endtabs %}

## ScaleAnimationDuration

The [`ScaleAnimationDuration`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ScaleAnimationDuration.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of scale animation.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    LongPressEffects="Scale"
    ScaleAnimationDuration="800">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    LongPressEffects = SfEffects.Scale,
    ScaleAnimationDuration = 800
};

{% endhighlight %}

{% endtabs %}

## RotationAnimationDuration

The [`RotationAnimationDuration`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~RotationAnimationDuration.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the duration of rotation animation.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    RotationAnimationDuration="800"
    TouchDownEffects="Rotation">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView()
{
    RotationAnimationDuration = 800,
    LongPressEffects = SfEffects.Rotation
};

{% endhighlight %}

{% endtabs %}

## InitialRippleFactor

The [`InitialRippleFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~InitialRippleFactor.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the initial radius of ripple.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView InitialRippleFactor="0.1">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    InitialRippleFactor = 0.1
};

{% endhighlight %}

{% endtabs %}

![InitialRippleFactor customization](Customization_images/InitialRippleFactor.gif)

## ScaleFactor

The [`ScaleFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ScaleFactor.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the scale of the view.

{% tabs %} 

{% highlight xaml %} 

 <sync:SfEffectsView
     ScaleFactor="0.85"
     LongPressEffects="Scale"
     TouchDownEffects="None"
     TouchUpEffects="None">
     ...
 </sync:SfEffectsView>

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

![ScaleFactor customization](Customization_images/ScaleFactor.gif)

## HighlightColor

The [`HighlightColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~HighlightColor.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of highlight effect.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
     HighlightColor="#2196F3"
     TouchDownEffects="Highlight">
     ...
 </sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    HighlightColor = Color.FromHex("#2196F3"),
    TouchDownEffects = SfEffects.Highlight
};

{% endhighlight %}

{% endtabs %}

![Highlight Color customization](Customization_images/HighlightColor.png)

## RippleColor

The [`RippleColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~RippleColor.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of ripple.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView RippleColor="#2196F3">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    RippleColor = Color.FromHex("#2196F3")
};
            
{% endhighlight %}

{% endtabs %}

![Ripple Color customization](Customization_images/RippleColor.png)

## SelectionColor

The [`SelectionColor`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~SelectionColor.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the color of selection effect.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    LongPressEffects="Selection"
    SelectionColor="#2196F3">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Selection,
    SelectionColor = Color.FromHex("#2196F3")
};

{% endhighlight %}

{% endtabs %}

![Selection Color customization](Customization_images/SelectionColor.png)

## CornerRadius

The [`CornerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~CornerRadius.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the corner radius of the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView CornerRadius="0,25">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    CornerRadius = new Thickness(0, 25)
};

{% endhighlight %}

{% endtabs %}

![EffectsView CornerRadius customization](Customization_images/CornerRadius.png)

## Angle

The [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~Angle.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to customize the rotation angle.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    Angle="180"
    TouchDownEffects="Ripple,Rotation">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    Angle = 180,
    TouchDownEffects = SfEffects.Ripple | SfEffects.Rotation
};
            
{% endhighlight %}

{% endtabs %}

![Rotation Angle customization](Customization_images/Angle.gif)
