---
layout: post
title: Interactions in Syncfusion EffectsView
description: How to set effects on different interactions in effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Interaction in EffectsView

You can set the effects on different interactions. This section explains how to set effects on different interactions available in effectsview.

## TouchDownEffects

The [`TouchDownEffects`] property of [`SfEffectsView`] is used to customize the effect on touch down.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchDownEffects="Ripple">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                TouchDownEffects = SfEffects.Ripple,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

## LongPressEffects

The [`LongPressEffects`] property of [`SfEffectsView`] is used to customize the effect on long press.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView LongPressEffects="Ripple">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                LongPressEffects = SfEffects.Ripple,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

## TouchUpEffects

The [`TouchUpEffects`] property of [`SfEffectsView`] is used to customize the effect on touch up.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchUpEffects="Ripple">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                TouchUpEffects = SfEffects.Ripple,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}
