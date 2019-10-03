---
layout: post
title: Interactions in Syncfusion EffectsView
description: How to set effects on different interactions in effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Interaction in SfEffectsView

You can set the effects on different interactions. This section explains how to set effects on different interactions available in effects view.

## TouchDownEffects

The [`TouchDownEffects`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~TouchDownEffects.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in touch-down interaction.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView TouchDownEffects="Ripple">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchDownEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}

## LongPressEffects

The [`LongPressEffects`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~LongPressEffects.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in long-press interaction.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView LongPressEffects="Ripple">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    LongPressEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}

## TouchUpEffects

The [`TouchUpEffects`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~TouchUpEffects.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) is used to render the effects in touch-up interaction.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView TouchUpEffects="Ripple">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    TouchUpEffects = SfEffects.Ripple
};

{% endhighlight %}

{% endtabs %}
