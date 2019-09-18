---
layout: post
title: Features in Syncfusion EffectsView
description: How to use the additional features in effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Features in EffectsView

The Effects View control also provides following additional additional features to enhance the effects.

## FadeOutRipple

On enabling [`FadeOutRipple`] property of [`SfEffectsView`], fades out the background color as the ripple progresses.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView FadeOutRipple="true" TouchDownEffects="Ripple">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                FadeOutRipple = true,
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

## IsSelected

Enabling [`IsSelected`] property of [`SfEffectsView`], sets the view state as selected.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView IsSelected="true" LongPressEffects="Selection">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                IsSelected = true,
                LongPressEffects = SfEffects.Selection,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## ShouldIgnoreTouches

Enabling [`ShouldIgnoreTouches`] property of [`SfEffectsView`], cancels the touch in EffectsView.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView ShouldIgnoreTouches="true">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                ShouldIgnoreTouches = true,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}
