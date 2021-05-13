---
layout: post
title: Interaction in Xamarin Effects View control | Syncfusion
description: Learn here all about Interaction support in Syncfusion Xamarin Effects View (SfEffectsView) control and more.
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Interaction in Xamarin Effects View (SfEffectsView)

You can set the effects on different interactions. This section explains how to set effects on different interactions available in effects view.

## TouchDownEffects

The [`TouchDownEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_TouchDownEffects) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in touch-down interaction.

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

The [`LongPressEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_LongPressEffects) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in long-press interaction.

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

The [`TouchUpEffects`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html#Syncfusion_XForms_EffectsView_SfEffectsView_TouchUpEffects) property of [`SfEffectsView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in touch-up interaction.

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
