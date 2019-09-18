---
layout: post
title: Customization of Syncfusion EffectsView
description: How to customize effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Customization of EffectsView

The Effects View control provides support to customize corner radius, animation duration, color and more. This section explains how to customize the effectsview control.

## RippleAnimationDuration

The [`RippleAnimationDuration`] property of [`SfEffectsView`] is used to customize the duration of ripple animation.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView RippleAnimationDuration="800">  
                    <Image Source="Icon.png" HeightRequest="70" WidthRequest="70"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView()
            {
                RippleAnimationDuration = 800,
                Content = new Image()
                {
                    Source = "Icon.png",
                    HeightRequest = 70,
                    WidthRequest = 70
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## ScaleAnimationDuration

The [`ScaleAnimationDuration`] property of [`SfEffectsView`] is used to customize the duration of scale animation.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView ScaleAnimationDuration="800" LongPressEffects="Scale">  
                    <Image Source="Icon.png" HeightRequest="70" WidthRequest="70"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView()
            {
                ScaleAnimationDuration = 800,
                LongPressEffects = SfEffects.Scale,
                Content = new Image()
                {
                    Source = "Icon.png",
                    HeightRequest = 70,
                    WidthRequest = 70
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## RotationAnimationDuration

The [`RotationAnimationDuration`] property of [`SfEffectsView`] is used to customize the duration of rotation animation.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView RotationAnimationDuration="800" TouchDownEffects="Rotation">  
                    <Image Source="Icon.png" HeightRequest="70" WidthRequest="70"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView()
            {
                RotationAnimationDuration = 800,
                LongPressEffects = SfEffects.Rotation,
                Content = new Image()
                {
                    Source = "Icon.png",
                    HeightRequest = 70,
                    WidthRequest = 70
                }
            };
            this.Content = effectsView;

{% endhighlight %}

{% endtabs %}

## CornerRadius

The [`CornerRadius`] property of [`SfEffectsView`] is used to customize the corner radius of [`SfEffectsView`].

{% tabs %} 

{% highlight xaml %} 

           <sfEffectsView:SfEffectsView CornerRadius="0,25">                                                    
                   <Grid BackgroundColor="#2196F3">
                       
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
                       <Label Text="Laura Steffi" Grid.Column="1" TextColor="White" 
                              FontAttributes="Bold"  Grid.Row="0"  VerticalTextAlignment="Center"
                              Margin="15,0,0,0" Font="17"/>
                       <Label Text="Data Science Analyst" Grid.Column="1" Grid.Row="1" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" FontAttributes="Bold"
                              Margin="15,0,0,0" Font="14"/>
                       <Label Text="laurasteffi@gmail.com" Grid.Column="1" Grid.Row="2" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                       <Label Text="011-253-321" Grid.Column="1" Grid.Row="3" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                   </Grid>
           </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                CornerRadius = new Thickness(0, 25)
            };

            var grid = new Grid
            {
                BackgroundColor = Color.FromHex("#2196F3"),
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
                TextColor = Color.White,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15,0,0,0),
                FontSize = 17
            };

            var designation = new Label
            {
                Text = "Data Science Analyst",
                TextColor = Color.WhiteSmoke,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var email = new Label
            {
                Text = "laurasteffi@gmail.com",
                TextColor = Color.WhiteSmoke,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var phone = new Label
            {
                Text = "011-253-321",
                TextColor = Color.WhiteSmoke,
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

## InitialRippleFactor

The [`InitialRippleFactor`] property of [`SfEffectsView`] is used to customize the initial radius of ripple.

{% tabs %} 

{% highlight xaml %} 

           <sfEffectsView:SfEffectsView InitialRippleFactor="0.1">                                                    
                   <Grid BackgroundColor="#2196F3">
                       
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
                       <Label Text="Laura Steffi" Grid.Column="1" TextColor="White" 
                              FontAttributes="Bold"  Grid.Row="0"  VerticalTextAlignment="Center"
                              Margin="15,0,0,0" Font="17"/>
                       <Label Text="Data Science Analyst" Grid.Column="1" Grid.Row="1" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" FontAttributes="Bold"
                              Margin="15,0,0,0" Font="14"/>
                       <Label Text="laurasteffi@gmail.com" Grid.Column="1" Grid.Row="2" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                       <Label Text="011-253-321" Grid.Column="1" Grid.Row="3" TextColor="WhiteSmoke" 
                              VerticalTextAlignment="Center" Margin="15,0,0,0" Font="14"/>
                   </Grid>
           </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                InitialRippleFactor = 0.1
            };

            var grid = new Grid
            {
                BackgroundColor = Color.FromHex("#2196F3"),
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
                TextColor = Color.White,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15,0,0,0),
                FontSize = 17
            };

            var designation = new Label
            {
                Text = "Data Science Analyst",
                TextColor = Color.WhiteSmoke,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var email = new Label
            {
                Text = "laurasteffi@gmail.com",
                TextColor = Color.WhiteSmoke,
                FontAttributes = FontAttributes.Bold,
                VerticalTextAlignment = TextAlignment.Center,
                Margin = new Thickness(15, 0, 0, 0),
                FontSize = 14
            };

            var phone = new Label
            {
                Text = "011-253-321",
                TextColor = Color.WhiteSmoke,
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

## ScaleFactor

The [`ScaleFactor`] property of [`SfEffectsView`] is used to customize the scale down factor.

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

## HighlightColor

The [`HighlightColor`] property of [`SfEffectsView`] is used to customize the color of highlight effect.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView TouchDownEffects="Highlight" HighlightColor="#2196F3">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                HighlightColor = Color.FromHex("#2196F3"),
                TouchDownEffects = SfEffects.Highlight,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

## RippleColor

The [`RippleColor`] property of [`SfEffectsView`] is used to customize the color of ripple.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView RippleColor="#2196F3">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                RippleColor = Color.FromHex("#2196F3"),
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

## SelectionColor

The [`SelectionColor`] property of [`SfEffectsView`] is used to customize the color of selection effect.

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

## Angle

The [`Angle`] property of [`SfEffectsView`] is used to customize the rotation angle.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView Angle="180" TouchDownEffects="Rotation">
                <Image Source="Biscuits.png" Aspect="Fill"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                Angle = 180,
                TouchDownEffects = SfEffects.Rotation,
                Content = new Image()
                {
                    Source = "Biscuits.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

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