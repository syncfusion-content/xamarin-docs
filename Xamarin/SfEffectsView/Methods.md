---
layout: post
title: Customization of Syncfusion EffectsView
description: How to customize effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Methods

You can add or remove effect programmatically using the [`ApplyEffects`] or [`Reset`] method.

## ApplyEffects

The [`ApplyEffects`] method is used to apply the provided effect with or without repetition. The following are the optional parameters to be passed.

* [`effects`] - [`SfEffects`] to be applied. By default, [`SfEffects.Ripple`] will apply.
* [`rippleStartPosition`] - [`RippleStartPosition`] which can be left, top, right, bottom and default. By default, [`RippleStartPosition`] is center.
* [`rippleStartPoint`] - a point at which ripple animation start. The default value is null.
* [`repeat`] - a bool value to set whether to repeate the applied effect. The default value is false.

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

![ApplyEffects and Reset methods](Methods_images/Methods.gif)