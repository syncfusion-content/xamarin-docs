---
layout: post
title: Features in Syncfusion EffectsView
description: How to use the additional features in effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Features in SfEffectsView

The [`SfEffectsView`] control provides the following additional features to enhance the effects.

## FadeOutRipple

By enabling the [`FadeOutRipple`] property of [`SfEffectsView`], the growable circle will lose its opacity to 0.

{% tabs %} 

{% highlight xaml %} 

                <sfEffectsView:SfEffectsView FadeOutRipple="True" RippleAnimationDuration="1000">
                    <Grid BackgroundColor="White">

                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="3*" />
                            <ColumnDefinition Width="7*" />
                        </Grid.ColumnDefinitions>

                        <Grid.RowDefinitions>
                            <RowDefinition />
                            <RowDefinition />
                            <RowDefinition />
                            <RowDefinition />
                        </Grid.RowDefinitions>

                        <Image
                            Grid.RowSpan="4"
                            Margin="7"
                            Source="{local:ImageSourceExt SampleBrowser.SfEffectsView.Person.png}" />
                        <Label
                            Grid.Row="0"
                            Grid.Column="1"
                            Margin="15,0,0,0"
                            Font="17"
                            FontAttributes="Bold"
                            Text="Laura Steffi"
                            VerticalTextAlignment="Center" />
                        <Label
                            Grid.Row="1"
                            Grid.Column="1"
                            Margin="15,0,0,0"
                            Font="14"
                            FontAttributes="Bold"
                            Text="Data Science Analyst"
                            VerticalTextAlignment="Center" />
                        <Label
                            Grid.Row="2"
                            Grid.Column="1"
                            Margin="15,0,0,0"
                            Font="14"
                            Text="laurasteffi@gmail.com"
                            VerticalTextAlignment="Center" />
                        <Label
                            Grid.Row="3"
                            Grid.Column="1"
                            Margin="15,0,0,0"
                            Font="14"
                            Text="011-253-321"
                            VerticalTextAlignment="Center" />
                    </Grid>
                </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                FadeOutRipple = true,
                RippleAnimationDuration = 1000
            };

            var grid = new Grid
            {
                BackgroundColor = Color.White,
                ColumnDefinitions = new ColumnDefinitionCollection()
                {
                    new ColumnDefinition{ Width = new GridLength(3, GridUnitType.Star) },
                    new ColumnDefinition{ Width = new GridLength(7, GridUnitType.Star) }
                },
            };

            var image = new Image
            {
                Source = "Person.png",
                Margin = 7
            };

            var name = new Label
            {
                Text = "Laura Steffi",
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15,0,0,0),
                FontSize = 17
            };

            var designation = new Label
            {
                Text = "Data Science Analyst",
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var email = new Label
            {
                Text = "laurasteffi@gmail.com",
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var phone = new Label
            {
                Text = "011-253-321",
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            grid.Children.Add(image, 0, 0);
            Grid.SetRowSpan(image, 4);
            grid.Children.Add(name, 1, 0);
            grid.Children.Add(designation, 1, 1);
            grid.Children.Add(email, 1, 2);
            grid.Children.Add(phone, 1, 3);

            effectsView.Content = grid;
            this.Content = effectsView;
            
{% endhighlight %}

{% endtabs %}

![FadeOutRipple](Features_images/FadeOutRipple.gif)

## IsSelected

Enabling the [`IsSelected`] property of [`SfEffectsView`] sets the view state as selected.

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

Enabling the [`ShouldIgnoreTouches`] property of [`SfEffectsView`] cancels the direct interaction of the [`SfEffectsView`].

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
