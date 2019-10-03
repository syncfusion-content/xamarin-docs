---
layout: post
title: Features in Syncfusion EffectsView
description: How to use the additional features in effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Features in SfEffectsView

The [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) control provides the following additional features to enhance the effects.

## FadeOutRipple

By enabling the [`FadeOutRipple`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~FadeOutRipple.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html), the growable circle will lose its opacity to 0.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    FadeOutRipple="True"
    RippleAnimationDuration="1000">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    FadeOutRipple = true,
    RippleAnimationDuration = 1000
};
            
{% endhighlight %}

{% endtabs %}

![FadeOutRipple](Features_images/FadeOutRipple.gif)

## IsSelected

Enabling the [`IsSelected`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~IsSelected.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) sets the view state as selected.

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView
    IsSelected="true"
    LongPressEffects="Selection">
    ...
</sync:SfEffectsView>

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

Enabling the [`ShouldIgnoreTouches`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView~ShouldIgnoreTouches.html) property of [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html) cancels the direct interaction of the [`SfEffectsView`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.EffectsView.SfEffectsView.html).

{% tabs %} 

{% highlight xaml %} 

<sync:SfEffectsView ShouldIgnoreTouches="true">
    ...
</sync:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

var effectsView = new SfEffectsView
{
    ShouldIgnoreTouches = true
};

{% endhighlight %}

{% endtabs %}
