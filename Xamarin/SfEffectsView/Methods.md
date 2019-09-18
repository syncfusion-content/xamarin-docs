---
layout: post
title: Customization of Syncfusion EffectsView
description: How to customize effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Methods

You add or remove effect programmatically by using the [`ApplyEffects`] or [`Reset`] methods

## ApplyEffects

The [`ApplyEffects`] method is used to apply the provided effect with or without repeatation.

{% highlight xaml %} 

            <StackLayout>
                <sfEffectsView:SfEffectsView x:Name="effectsView">
                    <Label Text="Ripple" HeightRequest="40"/>
                </sfEffectsView:SfEffectsView>
         
                <Button Text="Apply Effect" Clicked="ApplyEffectClicked"/>
            </StackLayout>

{% endhighlight %}

{% highlight C# %} 

            private void ApplyEffectClicked(object sender, EventArgs e)
            {
                effectsView.ApplyEffects(SfEffects.Ripple, RippleStartPosition.Right, true);
            }

{% endhighlight %}

## Reset

The [`Reset`] method is used to reset the applied effect.

{% highlight xaml %} 

            <StackLayout>
                <sfEffectsView:SfEffectsView x:Name="effectsView">
                    <Label Text="Ripple" HeightRequest="40"/>
                </sfEffectsView:SfEffectsView>
         
                <Button Text="Reset Effect" Clicked="ResetEffectClicked"/>
            </StackLayout>

{% endhighlight %}

{% highlight C# %} 

            private void ResetEffectClicked(object sender, EventArgs e)
            {
                effectsView.Reset();
            }

{% endhighlight %}
