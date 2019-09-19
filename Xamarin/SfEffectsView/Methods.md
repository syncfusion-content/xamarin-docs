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
* [`rippleStartPosition`] - [`RippleStartPosition`] can be left, top, right, bottom or default. By default, ripple will start from the center.
* [`rippleStartPoint`] - point at which ripple animation start. The default value is null.
* [`repeat`] - bool value to set whether to repeat the applied effect. The default value is false.

{% highlight xaml %} 

                <Grid>

                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>

                    <Grid.ColumnDefinitions>
                        <ColumnDefinition />
                        <ColumnDefinition />
                    </Grid.ColumnDefinitions>

                    <Grid Grid.ColumnSpan="2">

                        <sfEffectsView:SfEffectsView
                            x:Name="effectsView"
                            RippleAnimationDuration="500"
                            VerticalOptions="Center">
                            <Image Aspect="Fill" Source="Biscuits.png" />
                        </sfEffectsView:SfEffectsView>

                    </Grid>

                    <Button
                        x:Name="ApplyScaleEffectButton"
                        Grid.Row="1"
                        BackgroundColor="Accent"
                        Clicked="ApplyScaleEffectButton_Clicked"
                        HeightRequest="40"
                        HorizontalOptions="CenterAndExpand"
                        Text="Apply Effect"
                        TextColor="White"
                        VerticalOptions="CenterAndExpand"
                        WidthRequest="120" />
                    <Button
                        x:Name="ScaleResetButton"
                        Grid.Row="1"
                        Grid.Column="1"
                        BackgroundColor="Accent"
                        Clicked="ScaleResetButton_Clicked"
                        HeightRequest="40"
                        HorizontalOptions="CenterAndExpand"
                        Text="Reset"
                        TextColor="White"
                        VerticalOptions="Center"
                        WidthRequest="120" />

                </Grid>

{% endhighlight %}

{% highlight C# %} 

            private void ApplyEffectClicked(object sender, EventArgs e)
            {
                effectsView.ApplyEffects(effects: SfEffects.Ripple, repeat: true);
            }

{% endhighlight %}

## Reset

The [`Reset`] method is used to reset the applied effect.

{% highlight xaml %} 

                <Grid>

                    <Grid.RowDefinitions>
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>

                    <Grid.ColumnDefinitions>
                        <ColumnDefinition />
                        <ColumnDefinition />
                    </Grid.ColumnDefinitions>

                    <Grid Grid.ColumnSpan="2">

                        <sfEffectsView:SfEffectsView
                            x:Name="effectsView"
                            RippleAnimationDuration="500"
                            VerticalOptions="Center">
                            <Image Aspect="Fill" Source="Biscuits.png" />
                        </sfEffectsView:SfEffectsView>

                    </Grid>

                    <Button
                        x:Name="ApplyScaleEffectButton"
                        Grid.Row="1"
                        BackgroundColor="Accent"
                        Clicked="ApplyScaleEffectButton_Clicked"
                        HeightRequest="40"
                        HorizontalOptions="CenterAndExpand"
                        Text="Apply Effect"
                        TextColor="White"
                        VerticalOptions="CenterAndExpand"
                        WidthRequest="120" />
                    <Button
                        x:Name="ScaleResetButton"
                        Grid.Row="1"
                        Grid.Column="1"
                        BackgroundColor="Accent"
                        Clicked="ScaleResetButton_Clicked"
                        HeightRequest="40"
                        HorizontalOptions="CenterAndExpand"
                        Text="Reset"
                        TextColor="White"
                        VerticalOptions="Center"
                        WidthRequest="120" />

                </Grid>

{% endhighlight %}

{% highlight C# %} 

            private void ResetEffectClicked(object sender, EventArgs e)
            {
                effectsView.Reset();
            }

{% endhighlight %}

![ApplyEffects and Reset methods](Methods_images/Methods.gif)
