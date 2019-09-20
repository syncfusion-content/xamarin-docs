---
layout: post
title: Customization of Syncfusion EffectsView
description: How to customize effectsview
platform: xamarin
control: SfEffectsView
documentation: ug
---

# Customization of SfEffectsView

The [`SfEffectsView`] control provides support to customize the corner radius, animation duration, color, and more. This section explains how to customize the effects view control.

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

![InitialRippleFactor customization](Customization_images/InitialRippleFactor.gif)

## ScaleFactor

The [`ScaleFactor`] property of [`SfEffectsView`] is used to customize the scale of the view.

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

![ScaleFactor customization](Customization_images/ScaleFactor.gif)

## HighlightColor

The [`HighlightColor`] property of [`SfEffectsView`] is used to customize the color of highlight effect.

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

![Highlight Color customization](Customization_images/HighlightColor.png)

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

![Ripple Color customization](Customization_images/RippleColor.png)

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

![Selection Color customization](Customization_images/SelectionColor.png)

## CornerRadius

The [`CornerRadius`] property of [`SfEffectsView`] is used to customize the corner radius of the [`SfEffectsView`] control.

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

![EffectsView CornerRadius customization](Customization_images/CornerRadius.png)

## Angle

The [`Angle`] property of [`SfEffectsView`] is used to customize the rotation angle.

{% tabs %} 

{% highlight xaml %} 

            <sfEffectsView:SfEffectsView Angle="180" TouchDownEffects="Ripple,Rotation">
                <Image Source="Arrow.png" HeightRequest="70" WidthRequest="70"/>
            </sfEffectsView:SfEffectsView>

{% endhighlight %}

{% highlight C# %} 

            var effectsView = new SfEffectsView
            {
                Angle = 180,
                TouchDownEffects = SfEffects.Ripple | SfEffects.Rotation,
                Content = new Image()
                {
                    Source = "Arrow.png",
                    Aspect = Aspect.Fill
                }
            };
            this.Content = effectsView;
{% endhighlight %}

{% endtabs %}

![Rotation Angle customization](Customization_images/Angle.gif)
