---
layout: post
title: Interaction in Xamarin Effects View Control | Syncfusion
description: Explore interaction support in the Syncfusion Xamarin Effects View (SfEffectsView) control, including different interaction effects.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Interaction in Xamarin Effects View (SfEffectsView)

The SfEffectsView control allows you to set effects based on different types of interactions. This section explains how to configure effects for various interactions within the effects view.

## TouchDownEffects

The [`TouchDownEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_TouchDownEffects) property of `SfEffectsView` is used to render effects during a touch-down interaction.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView TouchDownEffects="Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}

## LongPressEffects

The [`LongPressEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_LongPressEffects) property of `SfEffectsView` is used to render effects during a long-press interaction.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView LongPressEffects="Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}

## TouchUpEffects

The [`TouchUpEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_TouchUpEffects) property of `SfEffectsView` is used to render effects during a touch-up interaction.

{% tabs %} 

{% highlight xaml %} 

<syncEffectsView:SfEffectsView TouchUpEffects="Ripple">
    ...
</syncEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchUpEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}
