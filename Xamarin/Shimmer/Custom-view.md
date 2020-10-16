---
layout: post
title: Syncfusion.Xamarin.Forms Custom view
description: This section describes how to add custom view support using different views and ShimmerView in Essential Xamarin.Forms Shimmer control.
platform: xamarin
control: SfShimmer
documentation: ug
---

## Custom view

You can customize the shimmer using your own view using the [`CustomView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_CustomView) property of [`SfShimmer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html). The below code demonstrate how to customize the shimmer view using Xamarin.Forms framework elements by [`CustomView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_CustomView).

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer>
            <shimmer:SfShimmer.CustomView>
                <Grid
                    Padding="10"
                    ColumnSpacing="15"
                    RowSpacing="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="10" />
                        <RowDefinition Height="10" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>
                    
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="0"
                             Grid.ColumnSpan="2"
                             HorizontalOptions="Start"
                             WidthRequest="300" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="1"
                             Grid.ColumnSpan="2"
                             HorizontalOptions="Start"
                             WidthRequest="250" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="2"
                             Grid.ColumnSpan="2"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="280" />
                    
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="3"
                             Grid.ColumnSpan="2"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="260" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="5"
                             Grid.RowSpan="8" />
                    
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="5"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="180" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="6"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="190" />
                    
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="7"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="170" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="8"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="180" />

                    <BoxView BackgroundColor="Gray"
                             Grid.Row="9"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="150" />
                        
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="10"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="160" />
                        
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="11"
                             Grid.Column="1"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="175" />
                        
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="13"
                             Grid.RowSpan="3"
                             Grid.Column="1"
                             Margin="0,5,0,0" />
                    
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="13"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="150" />
                        
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="14"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="160" />
                        
                    <BoxView BackgroundColor="Gray"
                             Grid.Row="15"
                             HeightRequest="10"
                             HorizontalOptions="Start"
                             VerticalOptions="Start"
                             WidthRequest="175" />
                </Grid>
            </shimmer:SfShimmer.CustomView>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            var shimmer = new SfShimmer();
            var grid = new Grid
            {
                Padding = 10,
                ColumnSpacing = 15,
                RowSpacing = 10,
                VerticalOptions = LayoutOptions.FillAndExpand,
                RowDefinitions = new RowDefinitionCollection()
                {
                    new RowDefinition { Height = 10 },
                    new RowDefinition { Height = 10 },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto }
                }
            };

            var boxView1 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                WidthRequest = 300
            };

            var boxView2 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                WidthRequest = 250
            };

            var boxView3 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 280
            };

            var boxView4 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                WidthRequest = 260,
                HeightRequest = 10,
            };

            var boxView5 = new BoxView
            {
                BackgroundColor = Color.Gray
            };

            var boxView6 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                BackgroundColor = Color.Gray,
                VerticalOptions = LayoutOptions.Start,
                WidthRequest = 180
            };

            var boxView7 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 190
            };
            var boxView8 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                BackgroundColor = Color.Gray,
                WidthRequest = 170
            };
            
            var boxView9 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 180
            };
            
            var boxView10 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 150
            };

            var boxView11 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 160
            };
            
            var boxView12 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 175
            };
            
            var boxView3 = new BoxView
            {
                BackgroundColor = Color.Gray,
                Margin = new Thickness(0, 5, 0, 0)
            };
            
            var boxView14 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 150
            };
            
            var boxView15 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 160
            };
            
            var boxView16 = new BoxView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                BackgroundColor = Color.Gray,
                HeightRequest = 10,
                WidthRequest = 175
            };

            grid.Children.Add(boxView1, 0, 0);
            Grid.SetColumnSpan(boxView1, 2);

            grid.Children.Add(boxView2, 0, 1);
            Grid.SetColumnSpan(boxView2, 2);

            grid.Children.Add(boxView3, 0, 2);
            Grid.SetColumnSpan(boxView3, 2);

            grid.Children.Add(boxView4, 0, 3);
            Grid.SetColumnSpan(boxView4, 2);

            grid.Children.Add(boxView5, 0, 5);
            Grid.SetRowSpan(boxView5, 8);

            grid.Children.Add(boxView6, 1, 5);

            grid.Children.Add(boxView7, 1, 6);

            grid.Children.Add(boxView8, 1, 7);

            grid.Children.Add(boxView9, 1, 8);

            grid.Children.Add(boxView10, 1, 9);

            grid.Children.Add(boxView11, 1, 10);

            grid.Children.Add(boxView12, 1, 11);

            grid.Children.Add(boxView13, 1, 13);
            Grid.SetRowSpan(boxView13, 3);

            grid.Children.Add(boxView14, 0, 13);

            grid.Children.Add(boxView5, 0, 14);

            grid.Children.Add(boxView16, 0, 15);
  
            shimmer.CustomView = grid;
            this.Content = shimmer;
        }
{% endhighlight %}

{% endtabs %}

N> The custom view of shimmer will support any kind of views in Android and iOS but UWP will only support `ShimmerView`.

For using [`CustomView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_CustomView) in iOS, set [`WaveColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_WaveColor) as the [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html) of Shimmer.

## Shimmer view

You can also customize the shimmer using `ShimmerView` using the [`CustomView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_CustomView) property of [`SfShimmer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html) in all the three platforms on Xamarin.Forms (Android, iOS and UWP).

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer>
            <shimmer:SfShimmer.CustomView>
                <Grid Padding="10"
                      ColumnSpacing="15"
                      RowSpacing="10">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="10" />
                        <RowDefinition Height="10" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                        <RowDefinition Height="Auto" />
                    </Grid.RowDefinitions>

                    <shimmer:ShimmerView Grid.Row="0"
                                         Grid.ColumnSpan="2"
                                         HorizontalOptions="Start"
                                         WidthRequest="300" />

                    <shimmer:ShimmerView Grid.Row="1"
                                         Grid.ColumnSpan="2"
                                         HorizontalOptions="Start"
                                         WidthRequest="250" />

                    <shimmer:ShimmerView Grid.Row="2"
                                         Grid.ColumnSpan="2"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="280" />

                    <shimmer:ShimmerView Grid.Row="3"
                                         Grid.ColumnSpan="2"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="260" />

                    <shimmer:ShimmerView Grid.Row="5"
                                         Grid.RowSpan="8" />

                    <shimmer:ShimmerView Grid.Row="5"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="180" />

                    <shimmer:ShimmerView Grid.Row="6"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="190" />

                    <shimmer:ShimmerView Grid.Row="7"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="170" />

                    <shimmer:ShimmerView Grid.Row="8"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="180" />

                    <shimmer:ShimmerView Grid.Row="9"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="150" />

                    <shimmer:ShimmerView Grid.Row="10"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="160" />

                    <shimmer:ShimmerView Grid.Row="11"
                                         Grid.Column="1"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="175" />

                    <shimmer:ShimmerView Grid.Row="13"
                                         Grid.RowSpan="3"
                                         Grid.Column="1"
                                         Margin="0,5,0,0" />

                    <shimmer:ShimmerView Grid.Row="13"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="150" />

                    <shimmer:ShimmerView Grid.Row="14"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="160" />

                    <shimmer:ShimmerView Grid.Row="15"
                                         HeightRequest="10"
                                         HorizontalOptions="Start"
                                         VerticalOptions="Start"
                                         WidthRequest="175" />
                </Grid>
            </shimmer:SfShimmer.CustomView>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

          var shimmer = new SfShimmer();
            var grid = new Grid
            {
                Padding = 10,
                ColumnSpacing = 15,
                RowSpacing = 10,
                VerticalOptions = LayoutOptions.FillAndExpand,

                RowDefinitions = new RowDefinitionCollection()
                {
                    new RowDefinition { Height = 10 },
                    new RowDefinition { Height = 10 },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto },
                    new RowDefinition { Height = GridLength.Auto }
                }
              
            };

            var shimmerView1 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                WidthRequest = 300
            };

            var shimmerView2 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                WidthRequest = 250
            };

            var shimmerView3 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 280
            };

            var shimmerView4 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                WidthRequest = 260,
                HeightRequest = 10,
            };

            var shimmerView5 = new ShimmerView();

            var shimmerView6 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                VerticalOptions = LayoutOptions.Start,
                WidthRequest = 180
            };

            var shimmerView7 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 190
            };
            
            var shimmerView8 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 170
            };
            
            var shimmerView9 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 180
            };
            
            var shimmerView10 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 150
            };

            var shimmerView11 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 160
            };
            
            var shimmerView12 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 175
            };
            
            var shimmerView13 = new ShimmerView
            {
                Margin = new Thickness(0, 5, 0, 0)
            };
            
            var shimmerView14 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 150
            };
            
            var shimmerView15 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 160
            };

            var shimmerView16 = new ShimmerView
            {
                HorizontalOptions = LayoutOptions.Start,
                VerticalOptions = LayoutOptions.Start,
                HeightRequest = 10,
                WidthRequest = 175
            };

            grid.Children.Add(shimmerView1, 0, 0);
            Grid.SetColumnSpan(shimmerView1, 2);

            grid.Children.Add(shimmerView2, 0, 1);
            Grid.SetColumnSpan(shimmerView2, 2);

            grid.Children.Add(shimmerView3, 0, 2);
            Grid.SetColumnSpan(shimmerView3, 2);

            grid.Children.Add(shimmerView4, 0, 3);
            Grid.SetColumnSpan(shimmerView4, 2);

            grid.Children.Add(shimmerView5, 0, 5);
            Grid.SetRowSpan(shimmerView5, 8);

            grid.Children.Add(shimmerView6, 1, 5);

            grid.Children.Add(shimmerView7, 1, 6);

            grid.Children.Add(shimmerView8, 1, 7);

            grid.Children.Add(shimmerView9, 1, 8);

            grid.Children.Add(shimmerView10, 1, 9);

            grid.Children.Add(shimmerView11, 1, 10);

            grid.Children.Add(shimmerView12, 1, 11);

            grid.Children.Add(shimmerView13, 1, 13);
            Grid.SetRowSpan(shimmerView13, 3);

            grid.Children.Add(shimmerView14, 0, 13);

            grid.Children.Add(shimmerView15, 0, 14);

            grid.Children.Add(shimmerView16, 0, 15);
  
            shimmer.CustomView = grid;
            this.Content = shimmer;
        }

{% endhighlight %}

{% endtabs %}

![Custom View](CustomView_images/customview.gif)

## See also

[How to set the custom view in SfShimmer using style](https://www.syncfusion.com/kb/11851/how-to-set-the-custom-view-in-xamarin-forms-shimmer-using-style)
