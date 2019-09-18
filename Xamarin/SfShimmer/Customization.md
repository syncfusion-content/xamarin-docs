---
layout: post
title: Customization of Syncfusion Shimmer
description: How to customize shimmer.
platform: xamarin
control: SfShimmer
documentation: ug
---

# Customization of Shimmer

The Shimmer control supports options to customize the wave color, shimmer color, wave direction, wave animation duration, and more. This section explains how to customize the shimmer control.

## WaveDirection

The [`WaveDirection`] property of [`SfShimmer`] is used to change the direction of shimmer wave. The following different wave directions are available in [`SfShimmer`]:

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

![Wave color customization](Customization_images/WaveColor.png)

## WaveWidth

The [`WaveWidth`] property of [`SfShimmer`] is used to customize the width of wave.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" WaveColor="#B8D4F2" WaveWidth ="100">
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
                WaveWidth = 100,
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

![Wave Width customization](Customization_images/WaveWidth.png)

## AnimationDuration

You can control the duration of wave animation using the [`AnimationDuration`] property of [`SfShimmer`]. The default value of [`AnimationDuration`] is 1000 ms.

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