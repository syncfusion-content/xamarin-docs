---
layout: post
title: Features in Syncfusion EffectsView
description: Different effects available in EffectsView
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Effects

The Effects View control provides support to ripple effect, highlight effect and more. This section explains about the different effects available in effects view.

## Ripple

[`SfEffects.Ripple`] is a growable circle, which is initially centered on the tapped location and it will grow till the whole layout is filled. [`SfEffects.Ripple`] will render based on [`SfEffectsView.InitialRippleFactor`].

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchDownEffects="Ripple">  
                    <Label Text="Ripple" HeightRequest="40"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView()
            {
                TouchDownEffects = SfEffects.Ripple,
                Content = new Label()
                {
                    Text = "Ripple",
                    HeightRequest = 40
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## Highlight

[`SfEffects.Highlight`] is a smooth transition on the background color of the [`SfEffectsView`]. It will generally appear before the ripple effect when given in combination with [`SfEffects.Ripple`] effect.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchDownEffects="Highlight" HighlightColor="#2196F3">                                                  
                   <Grid BackgroundColor="White">
                       
                       <Grid.ColumnDefinitions>
                           <ColumnDefinition Width="3*"/>
                           <ColumnDefinition Width="7*"/>
                       </Grid.ColumnDefinitions>
   
                       <Grid.RowDefinitions>
                           <RowDefinition />
                           <RowDefinition />
                           <RowDefinition />
                           <RowDefinition />
                       </Grid.RowDefinitions>
   
                       <Image Source="Person.png" Margin="7" 
                              Grid.RowSpan="4"/>
                       <Label Text="Laura Steffi" Grid.Column="1"
                              FontAttributes="Bold"  Grid.Row="0"  VerticalTextAlignment="Center"
                              Margin="15,0,0,0" Font="17"/>
                       <Label Text="Data Science Analyst" Grid.Column="1" Grid.Row="1" 
                              VerticalTextAlignment="Center" FontAttributes="Bold"
                              Margin="15,0,0,0" Font="14"/>
                       <Label Text="laurasteffi@gmail.com" Grid.Column="1" Grid.Row="2"
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                       <Label Text="011-253-321" Grid.Column="1" Grid.Row="3" 
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                   </Grid>
           </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                HighlightColor = Color.FromHex("#2196F3"),
                TouchDownEffects = SfEffects.Highlight,
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

## Selection

[`SfEffects.Selection`] is a smooth color transition to indicate the view state is moved to selected state. It will generally appear after the ripple effect when given in combination with [`SfEffects.Ripple`] effect.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView SelectionColor="#2196F3" LongPressEffects="Selection">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                SelectionColor = Color.FromHex("#2196F3"),
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

## Scale

[`SfEffects.Scale`] is a smooth transition from actual size of the object to the size calculated based on ['SfEffectsView.ScaleFactor'] in pixels.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchDownEffects="None" TouchUpEffects="None"
                                         LongPressEffects="Scale" ScaleFactor="0.85">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                ScaleFactor = 0.85,
                TouchDownEffects = SfEffects.None,
                TouchUpEffects = SfEffects.None,
                LongPressEffects = SfEffects.Scale,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## Rotation

[`SfEffects.Rotation`] provides a circular movement of the [`SfEffectsView`] around the center of the [`SfEffectsView`] based on the specified ['SfEffectsView.Angle']. 

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView Angle="180" TouchDownEffects="Rotation">
                <Image Source="Arrow.png" HeightRequest="70" WidthRequest="70"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                Angle = 180,
                TouchDownEffects = SfEffects.Rotation,
                Content = new Image()
                {
                    Source = "Arrow.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}
