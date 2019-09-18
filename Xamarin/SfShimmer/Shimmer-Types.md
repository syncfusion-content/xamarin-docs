---
layout: post
title: Syncfusion.Xamarin.Forms Shimmer types
description: Different Shimmer types available in Essential Xamarin.forms Shimmer.
platform: xamarin
control: SfShimmer
documentation: ug
---

# Shimmer Types

## Built-in types

The following different built-in shimmer types are available in Shimmer:

* [`Persona`]()
* [`Profile`]()
* [`Article`]()
* [`Video`]()
* [`Feed`]()
* [`Shopping`]()

You can use the built-in shimmer types by setting the [`Type`] of [`SfShimmer`].

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" Type="Profile">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                Type = ShimmerTypes.Profile,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

![The built-in shimmer types for Xamarin.Forms](Shimmer-Types_images/ShimmerTypes.gif)

## Custom view

You can customize the shimmer using your own view using the [`CustomView`] property of [`SfShimmer`].

{% tabs %} 

{% highlight xaml %} 

            <shimmer:SfShimmer.CustomView>
                <Grid
                    x:Name="customView"
                    Padding="10" ColumnSpacing="15" RowSpacing="15"
                    HorizontalOptions="FillAndExpand"
                    VerticalOptions="Center">
                    <Grid.ColumnDefinitions>
                        <ColumnDefinition Width="Auto" />
                        <ColumnDefinition Width="*" />
                    </Grid.ColumnDefinitions>
                    
                     <Grid.RowDefinitions>
                        <RowDefinition Height="*" />
                        <RowDefinition Height="*" />
                    </Grid.RowDefinitions>

                    <border:SfBorder Grid.RowSpan="2"
                        BackgroundColor="{Binding Color,Source={x:Reference shimmer}}"
                        BorderColor="Transparent"
                        CornerRadius="40"
                        HeightRequest="70"
                        VerticalOptions="Center"
                        WidthRequest="70">
                    </border:SfBorder>

                    <border:SfBorder Grid.Row="0" Grid.Column="1"
                         BackgroundColor="{Binding Color,Source={x:Reference shimmer}}"
                         BorderColor="Transparent"
                         HeightRequest="30"
                         VerticalOptions="Center" />
                     <border:SfBorder Grid.Row="1" Grid.Column="1"
                         BackgroundColor="{Binding Color,Source={x:Reference shimmer}}"
                         BorderColor="Transparent"
                         HeightRequest="30"
                         VerticalOptions="Center" />
                </Grid>
            </shimmer:SfShimmer.CustomView>

{% endhighlight %}

{% highlight C# %} 

            var grid = new Grid
            {
                Padding = 10,
                ColumnSpacing = 15,
                RowSpacing = 15,
                HorizontalOptions = LayoutOptions.FillAndExpand,
                VerticalOptions = LayoutOptions.Center,
                ColumnDefinitions = new ColumnDefinitionCollection()
                {
                    new ColumnDefinition { Width = GridLength.Auto },
                    new ColumnDefinition { Width = GridLength.Star }
                },
                RowDefinitions = new RowDefinitionCollection()
                {
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto }
                }
            };

            var imageBorder = new SfBorder
            {
                BorderColor = Color.Transparent,
                CornerRadius = 40,
                HeightRequest = 70,
                WidthRequest = 70,
                VerticalOptions = LayoutOptions.Center
            };
            imageBorder.SetBinding(SfBorder.BackgroundColorProperty, new Binding { Source = shimmer, Path = "Color" });

            var nameBorder = new SfBorder
            {
                BorderColor = Color.Transparent,
                HeightRequest = 30,
                VerticalOptions = LayoutOptions.Center
            };
            nameBorder.SetBinding(SfBorder.BackgroundColorProperty, new Binding { Source = shimmer, Path = "Color" });

            var description = new SfBorder
            {
                BorderColor = Color.Transparent,
                HeightRequest = 30,
                VerticalOptions = LayoutOptions.Center
            };
            description.SetBinding(SfBorder.BackgroundColorProperty, new Binding { Source = shimmer, Path = "Color" });

            
            grid.Children.Add(imageBorder, 0, 0);
            Grid.SetRowSpan(imageBorder, 2);
            grid.Children.Add(nameBorder, 1, 0);
            grid.Children.Add(description, 1, 1);

            shimmer.CustomView = grid; 

{% endhighlight %}

{% endtabs %}

![Shimmer Custom View for Xamarin.Forms](Shimmer-Types_images/CustomView.gif)

N> Currently, [`CustomView`] will support only in Android.
