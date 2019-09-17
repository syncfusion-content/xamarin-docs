---
layout: post
title: Customization of Syncfusion Shimmer
description: How to customize shimmer.
platform: xamarin
control: SfShimmer
documentation: ug
---

# Customization of Shimmer

The Shimmer control supports options to customize wave color, shimmer color, wave direction, wave animation duration and more. In this section, customizing shimmer control is explained.

## IsLoaded

On enabling the [`IsLoaded`] property of [`SfShimmer`], shimmer content will be loaded.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" IsLoaded ="true">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                IsLoaded = true,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

## WaveDirection

The [`WaveDirection`] property of [`SfShimmer`] is used to change the direction of shimmer wave. The different wave directions available in [`SfShimmer`] are as follows:

* [`Default`]()
* [`LeftToRight`]()
* [`TopToBottom`]()
* [`RightToLeft`]()
* [`BottomToTop`]()

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" WaveDirection="LeftToRight">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                WaveDirection = WaveDirection.LeftToRight,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

## Color

The [`Color`] property of [`SfShimmer`] is used to customize the color of shimmer.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" Color="#F4E2EE">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                Color = Color.FromHex("#F4E2EE"),
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

![Shimmer color customization](Customization_images/ShimmerColor.png)

## WaveColor

The [`WaveColor`] property of [`SfShimmer`] is used to customize the color of wave.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" WaveColor="#B8D4F2">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                WaveColor = Color.FromHex("#B8D4F2"),
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

![Wave color customization](Customization_images/ShimmerColor.png)

## WaveWidth

The [`WaveWidth`] property of [`SfShimmer`] is used to customize the width of wave.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" WaveColor="#B8D4F2" WaveWidth ="150">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                WaveWidth = 150,
                WaveColor = Color.FromHex("#B8D4F2"),
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

## AnimationDuration

You can control the duration of wave animation by using the [`AnimationDuration`] property of [`SfShimmer`]. The default value of [`AnimationDuration`] is 1000ms.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" AnimationDuration ="2000">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                AnimationDuration = 2000,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}