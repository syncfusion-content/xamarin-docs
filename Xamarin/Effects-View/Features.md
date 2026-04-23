---
layout: post
title: Features in Xamarin Effects View Control | Syncfusion
description: Explore the features supported by the Syncfusion Xamarin Effects View (SfEffectsView) control, including FadeOutRipple, IsSelected, and ShouldIgnoreTouches.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Features in Xamarin Effects View (SfEffectsView)

The [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides several additional features to enhance its effects capabilities.

## FadeOutRipple

Enable the [`FadeOutRipple`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_FadeOutRipple) property to make the ripple effect's opacity diminish to zero as it grows.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    FadeOutRipple="True"
    RippleAnimationDuration="1000">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    FadeOutRipple = true,
    RippleAnimationDuration = 1000
};
            
{% endhighlight %}

{% endtabs %}

![FadeOutRipple](Features_images/EffectsView_Fadeout_Ripple.gif)

## IsSelected

The [`IsSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_IsSelected) property sets the view's state to selected when enabled.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView
    IsSelected="true"
    LongPressEffects="Selection">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    IsSelected = true,
    LongPressEffects = SfEffects.Selection
};

{% endhighlight %}

{% endtabs %}

## ShouldIgnoreTouches

Set the [`ShouldIgnoreTouches`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ShouldIgnoreTouches) property to true to cancel direct interactions with the `SfEffectsView`.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView ShouldIgnoreTouches="true">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    ShouldIgnoreTouches = true
};

{% endhighlight %}

{% endtabs %}

N> On enabling [`ShouldIgnoreTouches`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_ShouldIgnoreTouches) property in iOS, the child view will not get interaction.
